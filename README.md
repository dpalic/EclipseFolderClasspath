# EclipseFolderClasspath

This is an Eclipse plugin that allows creating a dynamic Classpath Container that observes a folder and loads all .jar (or .zip etc) files into the classpath. 
This plugin is helpful to use a bunch of jar files in one folder as your classpath, without setting it manually.

## We use this plugin for:
- any project which may not use maven or any other lib/jar dependency management tool
- for IVY projects without the usage (of the buggy) IvyDE plugin, there a ANT or manual build retrieves the jar files into one or multiple folders and all libs in these folders need to be automatically picked up by eclipse
- We started to invest our time into this plugin, since we wanted to get rid of the buggy IvyDE plugin for our IVY dependency management. The recommended way of Ivy is to retrieve - ivy name for downloading and placing into a specific folder - the jars into a specific folder. But here we had the issue, that we had to manually define every lib reference! And on every lib change again.

## What is this plugin not for?
It is not a replacement for maven or Ivy. 

## What is it for?
Is is a addition to any environment in eclipse, there the libs are managed in a set of folders and there the developers do not want to update the eclipse classpath on every file change in these folders.

## How to Install?
The binary in downloads on GitHub just needs to be dropped into the eclipse /plugins/ folder and it will 
then allow adding a "Directory Container" library to the Java Build Path.

You can find the latest verion here:
https://github.com/dpalic/EclipseFolderClasspath/tree/master/SimpleDirectoryContainer_EclipsePlugin/ExportedPlugin

I created this jar by exporting a "Deployable plug-ins and fragments" from Eclipse at the project level.

## INSTALLATION
1. Download the latest jar file (see above)
2. stop your eclipse (ensure it is really stopped in taskmanager)
3. put the downloaded jar file into your eclipse\plugin folder
4. restart your eclipse
5. in Eclipse go to you Java Build Path settings and go to the tab Libraries
6. "Add Library..." will provide you now a new entry "Directory container"

## How to contribute?
Please provide a pull request, we well give our best to review your changes and to incorporate it into the repository.

## History
It is an evolution of original code I got from here:
	https://www.ibm.com/developerworks/opensource/tutorials/os-eclipse-classpath/
Thus it originates from Aaron Tarter (aarontar@us.ibm.com).

The primary modification Ben Christensen made (besides renaming things to no longer say 'example') was making it handle
filenames that had multiple dots (such as com.company.library.name.v2.jar).

After not getting any response on the provided patches, I decided to create a new repository independently of the Ben Christensens changes. Since there are already so much changes, what only some rudimentary parts are original, all other stuff has already been changed.

The improvements I made (Darko Palic) are to allow multiple directory containers in the classpaths and of course therefore in the eclipse launch configurations and any other eclipse runtime/classpath settings.
The previous version had bigger issues about it.

