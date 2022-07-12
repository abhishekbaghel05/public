# Creating DAISY files using Google Cloud TTS

## Installing and Setting up Daisy Pipeline 2
1. Dowload latest version of [DAISY Pipeline 2](https://daisy.github.io/pipeline/Download.html).
2. The DAISY Pipeline 2 desktop application require a Java runtime environment. The minimum required version of Java is 11. At the time of installation in Windows, installer will promt to install Java. Click on yes. 
3. Install the DAISY Pipeline 2 Software. For more information visit the [installation page](https://daisy.github.io/pipeline/Get-Help/User-Guide/Installation/#system-requirements)
4. Open the Program Files in your C drive. Open the folder location `C:\Program Files (x86)\DAISY Pipeline 2\daisy-pipeline\jdk-11.0.2+9-jre\lib` . Download and add the file [content-types.properties](https://github.com/AdoptOpenJDK/openjdk-jdk11/blob/master/src/java.base/windows/classes/sun/net/www/content-types.properties) to this location.

## Setting Up Google Cloud TTS
1. Visit cloud.google.com and create a new accout if it is not existing
2. Create a new project and give a name to it
3. Create a new Billing account by adding your credit card details
4. Enable Google Cloud TTS API Service. Pricing and other details are available  
5. For sending the conversion requsts to google cloud generate an API Key by going to API & Credentials --> Credentials
6. Copy the API key
7. Open 

## Converting an EPUB file to DAISY Audio
1. Open DAISY Pipeline 2 sotware from the start menu
2. Click on `File` and click on `New job`
3. Select `EPUB to DAISY` option
4. 
