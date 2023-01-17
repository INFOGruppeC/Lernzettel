 1. Oben rechts auf den `#` Knopf drücken
 2. Workspaces
 3. Add a GItHub workspace
 4. Dann Github repo link auf `https://github.com/INFOGruppeC/Lernzettel` setzen und branch auf `main`
 5. Dann die checkbox private aktivieren und WARTEN!!
 6. Auf dieser Seite die Browser Konsole öffnen und den code unten einfügen und enter drücken
 7. Dann auf weiter
 8. und neben der info organisation auf Grant drücken
 9. Bestätigen
 10. Und tada 



Code:
```js
window.XMLHttpRequest =  class MyXMLHttpRequest extends window.XMLHttpRequest {
  open(...args){
    if(args[1].startsWith("https://api.github.com/user?access_token=")) {
      // apply fix as described by github
      // https://developer.github.com/changes/2020-02-10-deprecating-auth-through-query-param/#changes-to-make
  
      const segments = args[1].split("?");
      args[1] = segments[0]; // remove query params from url
      const token = segments[1].split("=")[1]; // save the token
      
      const ret = super.open(...args);
      
      this.setRequestHeader("Authorization", `token ${token}`); // set required header
      
      return ret;
    }
    else {
      return super.open(...args);
    }
  }
}
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbNjU0ODY0MDk4XX0=
-->