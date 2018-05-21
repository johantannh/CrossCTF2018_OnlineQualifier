# CrossCTF2018 Online Qualifier Writeups
## Team J2K
[Jun Hao](https://github.com/xephersteel) and [Kelvin Chu](https://github.com/x3sphiorx)
## Challenges
<h3 align="center">WEB</h3>

---

### Contents
1. QuirkyScript 1
2. QuirkyScript 2
3. QuirkyScript 3
4. QuirkyScript 4
5. QuirkyScript 5
6. BabyWeb

#### 1. QuirkyScript 1
##### Problem
```javascript
var flag=require("./flag.js");
var express=require('express')
var app=express()
app.get('/flag',function(req,res){
  if(req.query.first){
    if(req.query.first.length==8&&req.query.first==",,,,,,,"){
        res.send(flag.flag);
        return;
    }
  }
  res.send("Try to solve this.");
});
app.listen(31337)
```
##### Solution
We first try to find out what is this script all about. A quick google search will allow you to find out that it is ExpressJS. From there we read the API under https://expressjs.com/en/api.html to find out how it works.

After analysis of the code, we learn that we are required to trigger the condition to get the flag. 

For this case we have to find out how to get length 8 with only 7 commas???

Team J2K
