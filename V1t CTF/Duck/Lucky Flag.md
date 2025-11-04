## Challenge

You don't have to search, it will randomly come to you :>

## Solution

I checked the source code and found this 

```bash
<script>
let randomNumber = Math.floor(Math.random() * 1000);

if (randomNumber === 36) {  
    alert("Damnnn you got lucky :>");
  	alert(atob("djF0e2x1Y2t5X2R1Y2t5fQ=="));
}
</script>
```

Got the flag on decoding the Base64 string
```bash
$ echo djF0e2x1Y2t5X2R1Y2t5fQ== | base64 -d        
v1t{lucky_ducky}
```

Flag: `v1t{lucky_ducky}`



