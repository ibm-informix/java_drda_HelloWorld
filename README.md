#Java DRDA Hello World Sample Application

##Structure

###Relevant files:

####src/com/ibm/informix/java_drda_HelloWorld.java

This file contains sample data interacting with a database.

####manifest.yml

This file gives details to Bluemix about the application.

####src/main/webapp/index.jsp

This file is the homepage.

####WebContent/WEB-INF/web.xml

This file contains the details about deploying to the web.

####build.gradle

This file gathers dependencies and builds the .war file needed to deploy to Bluemix.

##Deploy application to Bluemix

###Option 1: Deploying to Bluemix from a local machine

####Requirements:

Git - you use to download the application. <Link to download Git>

CloudFoundry CLI -  you use to push the application to Bluemix. <Link to download CLI>

Gradle -  you use to get dependencies and build the application. <Link to download Gradle>

####Procedure:

Clone repository to local machine
	
	git clone <url>
	git submodule init
	git submodule update

or 

	git clone --recursive <url>

	
Download the corresponding driver to the project you wish to run.

DRDA -> <link>

SQLI -> <link>

Mongo -> <compile gradle>

Set to include in the WebContent/WEB-INF/lib/ directory. You may need to create a 'lib' folder

Navigate to the root directory of the project you wish to run, it should contain a build.gradle file.

Run gradle
	
	gradle build
	
This should create a .war file.
	
Connect to Bluemix
	
	cf api https://api.ng.bluemix.net
	
Log into Bluemix
	
	cf login
	
Enter user and pass
	
	jondoe@ibm.com
	password
	
Push application
	
	cf push <YourAppName>

###Option 2: Deploy from JazzHub

I don't know how to do this yet, but dataworks docs says

See the JazzHub documentation for full information, but the steps are as follows:

Open this project in a new browser window.

Click EDIT CODE, and log in to JazzHub if you are not already authenticated.

Click Fork.

Provide a name for your copy of the sample and click Save.

When the project is copied into your repository, click BUILD & DEPLOY.

Click Project Settings.

Select Deploy to Bluemix, keep the other default values, and click Save.

On BUILD & DEPLOY, click ADVANCED, and click add a builder.

Keep the default values in the Add Builder page, and click SAVE.

Click REQUEST BUILD.

When the build has completed and you see a green check mark, click add a stage.

Provide a unique application name and click SAVE.

In the pipeline, drag the Build button to the deployment space to deploy the application to Bluemix. The number of times that the application has been built is displayed in the button.
