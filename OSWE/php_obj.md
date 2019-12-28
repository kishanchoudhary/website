# Php DeSerialization / Object Injection

Hello readers, Hope your doing good :) , 
So lets have a look at this vulnerability in php which leads to "Remote Code Execution" 

i will be demonstrating this vulnerability on a online lab /dev/random - pipe from Root-me.org

So what is Php DeSerialization?

PHP Object Injection (Php DeSerialization) is an application level vulnerability that could allow an attacker to perform different kinds of malicious attacks, such as Code Injection, SQL Injection, Path Traversal and Application Denial of Service, depending on the context. The vulnerability occurs when user-supplied input is not properly sanitized before being passed to the unserialize() PHP function. Since PHP allows object serialization, attackers could pass ad-hoc serialized strings to a vulnerable unserialize() call, resulting in an arbitrary PHP object(s) injection into the application scope.

