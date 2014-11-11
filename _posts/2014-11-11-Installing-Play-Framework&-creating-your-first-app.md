---
layout: post
title: Installing Play Framework and creating your first app
date: "2014-11-11 21:48:00"
---
In this post, we'll go through the installation of Play Framework in Windows 8 environment.

1. [Introduction to Play Framework](#s1)
2. [Prerequirements](#s2)
3. [Installation](#s3)
4. [Creating your first application](#s4)
5. [Conclusion](#s5)

##<a name="s1"></a>1. Introduction to Play Framework 2
Play Framework, a MVC web framework inspired by Ruby on Rails, is implemented in Java and Scala. The applications developed using Play can use both as well, as both Java and Scala can be compiled in a bytecode that can be run in JVM. Play applications are designed to be run in Netty server, but can be packaged as a .war file and then run in Java application server, such as Tomcat. 

##<a name="s2"></a>2. Prerequirements
- Java JDK is installed (download from [here](http://www.oracle.com/technetwork/java/javase/downloads/index.html))
- JAVA_HOME is set and added to PATH variable

Test your setup: open command prompt and issue command ```javac```. Output should look like this:

    C:\>javac
    Usage: javac <options> <source files>
    where possible options include:
      -g                         Generate all debugging info
      -g:none                    Generate no debugging info
      -g:{lines,vars,source}     Generate only some debugging info
      -nowarn                    Generate no warnings
      -verbose                   Output messages about what the compiler is doing
      -deprecation               Output source locations where deprecated APIs are used
      ...

##<a name="s3"></a>. Installation
You can download two versions of Play. First, there's a minimal installation of Play with Activator. The download size of this package is only about 1M. When activator is run, it provides a easy way to install example appliations via your web browser. Applications are downloaded automatically from GitHub repos, compiled and started. I tested a few of them and seems that there's lot of material to use as an example for your own applications. **Note:** in Chrome I faced an timeout while loading dependencies, in IE there were no problems. 

Another version is the standard offline package. Size is much larger, but it contains all the libraries needed for development. 

1. Download and extract the package of your choice. I went with offline version, as I did not want to wait for each dependency to be downloaded separately.
2. Add the installation directory to your PATH.
3. Issue command ```activator help``` from command line

The output should look like this:

    C:\>activator help

    Usage activator [options] [command]

    Commands:
    ui                 Start the Activator UI
    new [name] [template-id]  Create a new project with [name] using template [template-id]
    list-templates     Print all available template names
    help               Print this message

    Options:
    -jvm-debug [port]  Turn on JVM debugging, open at the given port.  Defaults to 9999 if no port given.

    Environment variables (read from context):
    JAVA_OPTS          Environment variable, if unset uses ""
    SBT_OPTS           Environment variable, if unset uses ""
    ACTIVATOR_OPTS     Environment variable, if unset uses ""

##<a name="s4"></a>4. Creating your first application
Creating basic starter application from template is straightforward. Here I create application called "myapp" from template "play-java", by issuing command ```activator new myapp play-java```

    D:\Dev>activator new myapp play-java
    Fetching the latest list of templates...

    OK, application "myapp" is being created using the "play-java" template.

    To run "myapp" from the command line, "cd myapp" then:
    D:\Dev\myapp/activator run

    To run the test for "myapp" from the command line, "cd myapp" then:
    D:\Dev\myapp/activator test

    To run the Activator UI for "myapp" from the command line, "cd myapp" then:
    D:\Dev\myapp/activator ui

Now to check that your application is working, issue command ```activator run```
    
    ...lots of resolving of dependencies...
    [info] Resolving org.scala-lang.modules#scala-xml_2.11;1.0.2 ...
    [info] Resolving jline#jline;2.11 ...
    [info] Done updating.

    --- (Running the application from SBT, auto-reloading is enabled) ---

    [info] play - Listening for HTTP on /0:0:0:0:0:0:0:0:9000

At this point, I browse to default application address, which is ```http://127.0.0.1:9000```. Console output changes accordingly:

    (Server started, use Ctrl+D to stop and go back to the console...)

    [info] Compiling 4 Scala sources and 2 Java sources to D:\Dev\myapp\target\scala-2.11\classes...
    [info] play - Application started (Dev)
Now the browser should show the default Play start page.

##<a name="s5"></a>5. Conclusion
In this short tutorial we installed Play Framework, set up the required environment variables and created basic web application from template. 
