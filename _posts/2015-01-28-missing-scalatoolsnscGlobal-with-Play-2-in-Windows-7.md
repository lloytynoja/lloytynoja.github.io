---
layout: post
title: with Play 2 in Windows 7
date: "2015-11-28 18:00:00"
---
I encountered following error while I was installing a fresh Play development environment in to my work laptop:

    C:\Work\Java\workspace\myapp>activator run
    Getting Scala 2.10.4 (for sbt)...
    :: retrieving :: org.scala-sbt#boot-scala
            confs: [default]
            0 artifacts copied, 5 already retrieved (0kB/31ms)
    Error: Could not retrieve Scala 2.10.4: missing scala.tools.nsc.Global
    
The suggested fix of [this](http://stackoverflow.com/questions/24539576/sbt-scala-2-10-4-missing-scala-tools-nsc-global) SO post helped me out. Advice in the post was for Ubuntu, but in Windows, the .sbt is located in your user/home directory too and removing the .sbt\boot directory got rid of the error message.

     C:\Users\<username>\.sbt\rd /s boot
