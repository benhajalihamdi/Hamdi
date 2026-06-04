---
tags:
  - Dev
  - Sec
  - Ops
aliases:
date/time: 2026-03-29 15:16
Date /Time: "{date} {time}"
title:
draft: true
---
firs introduced in [[DevSecOps]] (developement, secuirity, operation)

previously:
code --> test --> Build (app)
and security comes after the apps or thing is already built 
--> Harder approach and more expensive because the security will only be applied after app already done (5idma bi skotch)

Solution: 
Security get integrated in every stage (code, test, building)
even before development:
--> plugin checks security from the very beginning (called pre-commit) [[Snyk]] (open source)
--> test: [[SAST (Static Application Security Testing)|static analysis]]: analyses the entire code

--> Build: deuxccoeurs, ducore, plugin [[Trivy]] analyses docker image or docker scoute, [[CVU]]? [[penetration testing]]? [[burpsuite]], [[zarp]]  CISI [[CISD]]?
[[api keys]]?

[[mango dv]] ?

check image 
[[DAST (Dynamic Application Security Testing)|dynamic test]] for code 
static analyses 

[[network segmentation]]? [[mfa]]? [[sso]]? [[ip localisation]]?

done with github action for automation 


[[PLP]]: least privelage 
give the least priveleage required for each emplyee/user 
advise use the cloud aws azure....

[[sql injection]], [[user input sanitization]], [[privelege escalation]],[[pivoting]]
even the services musnt have 777 to prevent privelage escalation

defense in depth:
put layers of defense so the hacker cant reach the core 

fail safe soit fail secuire 

fail safe, if firewall or smh fell let everyone in 
if fail secuire , if firewall or smh fell BLOCK FOR EVERYONE 

kiss principal: keep it simple stupid 
sso; single site only 
something you know (password )
something you have (key physique, code sent via mobile)
something you are( localization , biometric data )
(mac address) can be added 

[[separation of duty (SOD)]]
one singular person cannot take an important decision or access important information, (duty is separated to multiple individuals)

put somethings in the background, so that, its not hard for users 

segmentation for back end and front end. Database isnt connected via internet onlut for outbound (when updating )
so the two parts are segmeneted and seperated cannot interact with each other,

soc enviorneme,nt in cloud 
azure  AWS
[[vulnereability management ]]
integratio detection 
[[incident response]] 





