# Rock-Stone-Paper-Springboot-problem
The problem is asked as part of Vocera Hiring challenge in HackerEarth. 

**About the problem :**
We are expected to create a Spring boot REST application for the stone,paper,scissor game between 2 users(Webserver/Actual User) using any Relation database.

We're expected to create three rest endpoint
1) /api/start
2) /api/v1/{token}/{userinput} 
3) /api/v2/{token}/{userinput} (This is for SERVER win scenario, No matter what's the user input SERVER has to WIN the game)

**My submitted Solution**
<br/>
**Api Documentation :**
<br/>
url : /api/start
<br/>
Method : GET
<br/>
Response : 
{
"status" : "READY",
"token" : {Random number}
}
<br/>
**API Detail**
When user hit /api/start endpoint, we're expected to send a random number as a token for the user, to start the game. We store the token in the in-memory H2 Database.

<br/>
url : /api/v1/{token}/{userinput}
<br/>
Method : GET
<br/>
PathVariable:
<br/>
  i) token -> Random generated value from START api.
  <br/>
  ii) userinput -> The user choice/move among stone,paper,scissor for happy path scenario else any valid string.
<br/>
Response :
<br/>
{
<br/>
"serverMove" : {SERVER MOVE},
<br/>
"totalScore" : 0
<br/>
}
<br/>
In the response, we have 2 fields serverMove and totalScore.
<br/>
serverMove field in the above response payload represent the server move/choice among stone,paper,scissor for the user input move and totalScore field in the above response payload represent the total server score
<br/>
<br/>

**API Detail**
<br/>
url : /api/v12/{token}/{userinput}
<br/>
Method : GET
<br/>
PathVariable:
<br/>
  i) token -> Random generated value from START api.
  <br/>
  ii) userinput -> The user choice/move among stone,paper,scissor for happy path scenario else any valid string.
<br/>
Response : 
<br/>
{
<br/>
"serverMove" : "scissor",
<br/>
"totalScore" : 0
<br/>
}
<br/>
In the response, we have 2 fields serverMove and totalScore.
<br/>

