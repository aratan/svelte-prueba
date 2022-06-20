// var Gun = require('gun'); // in NodeJS 
// require('gun/sea');
<script>
    var Gun = require('gun'); // in NodeJS 
    var gun = Gun(["http://localhost:8765/gun","https://gunjs.herokuapp.com/gun"]);

</script>

<form id="sign">
    <input id="alias" placeholder="username" />
    <input id="pass" type="password" placeholder="passphrase" />
    <input id="in" type="submit" value="sign in" />
    <input id="up" type="button" value="sign up" />
</form>

<ul />

<form id="said">
    <input id="say" />
    <input id="speak" type="submit" value="speak" />
</form>

