---
layout: post
title:  "Get Reports List in Custom Folder"
date:   2022-10-10 22:04:39 +0530
categories: jekyll update
---


```plantuml
@startuml
start
:Download Custom Folder;
:Assign pParameter => [XDRZ,XDOZ,XDMZ];
repeat
:list all files Current pParameter;
repeat
:check pParameter file;
:rename file to zip;
repeat while (more file?) is (yes)
->no;
:list all ZIP files;
if (zip?) then
:unzip;
endif
backward:assign next parameter;
repeat while (pParameter.next ?) is (yes)
->no;
stop
@enduml
```