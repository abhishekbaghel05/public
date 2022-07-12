# Converting EPUB files to DAISY files with audio using Google Cloud TTS on Windows 10/11

Perform the follwing steps in order

## Installing and Setting up Daisy Pipeline 2
1. Dowload latest version of [DAISY Pipeline 2](https://daisy.github.io/pipeline/Download.html).
2. The DAISY Pipeline 2 desktop application require a Java runtime environment. The minimum required version of Java is 11. At the time of installation in Windows, installer will promt to install Java. Click on yes. 
3. Install the DAISY Pipeline 2 Software. For more information visit the [installation page](https://daisy.github.io/pipeline/Get-Help/User-Guide/Installation/#system-requirements).
4. Open the Program Files in your C drive. Open the folder location `C:\Program Files (x86)\DAISY Pipeline 2\daisy-pipeline\jdk-11.0.2+9-jre\lib` . Download and add the file [content-types.properties](https://github.com/AdoptOpenJDK/openjdk-jdk11/blob/master/src/java.base/windows/classes/sun/net/www/content-types.properties) to this location.

## Setting Up Google Cloud TTS
1. Visit cloud.google.com and create a new accout if it is not existing.
2. Open Google Cloud console and create a new project and give a name to it.
3. Create a new Billing account by adding your credit card details by going to `Google Cloud Console > Navigation Menu > Billing > Create`
4. Enable Google Cloud TTS API Service. Pricing details are available on the [tts pricing page](https://cloud.google.com/text-to-speech/pricing)
5. For sending the conversion requsts to google cloud generate an API Key by going to `APIs & Services > Credentials > Create Credential > API Key`
6. Copy the API key
7. Open `pipeline.properties` file in any ascii editor from the location `C:\Program Files (x86)\DAISY Pipeline 2\daisy-pipeline\etc` 
8. Uncomment the the line ``
9. Create a new file `config.xml` the follwing contents and save it to the computer. 
  ```html
  <config>
    <property key="org.daisy.pipeline.tts.google.apikey" value="Your API Key"/>
    <property key="org.daisy.pipeline.tts.log" value="true"/>
    <voice engine="google" name="en-US-Standard-A" gender="MALE" priority="100" lang="en-US"/>
    <property key="org.daisy.pipeline.tts.google.samplerate" value="24000"/>  
  </config>
  ```
The configuration properties can be changed as per the requirments. You can refer to the [list of voices and languages](https://cloud.google.com/text-to-speech/docs/voices) supported by Google Cloud TTS. To know more refer to [TTS user guide](http://daisy.github.io/pipeline/Get-Help/User-Guide/Text-To-Speech/) of DAISY Pipeline 2.

10. sss

## Converting an EPUB file to DAISY Audio
1. Open DAISY Pipeline 2 sotware from the start menu
2. Click on `File` and click on `New job`
3. Select `EPUB to DAISY` option
