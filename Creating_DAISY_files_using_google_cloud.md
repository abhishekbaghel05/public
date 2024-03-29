# Converting EPUB files to DAISY files with audio using Google Cloud TTS on Windows 10/11

Perform the follwing steps in order

## Installing and Setting up Daisy Pipeline 2
1. Dowload latest version of [DAISY Pipeline 2](https://daisy.github.io/pipeline/Download.html).
2. The DAISY Pipeline 2 desktop application require a Java runtime environment. The minimum required version of Java is 11. At the time of installation in Windows, installer will promt to install Java. Click on yes. 
3. Install the DAISY Pipeline 2 Software. For more information visit the [installation page](https://daisy.github.io/pipeline/Get-Help/User-Guide/Installation/#system-requirements).
4. Download [LAME MP3 Encoder](https://lame.sourceforge.io/download.php). Extact the folder. Save it in a safe place on your system.
5. Add the path to 'lame' to the environment variables so that DAISY pipeline can find its location.

## Setting Up Google Cloud TTS
1. Visit cloud.google.com and create a new accout if it is not existing.
2. Open Google Cloud console and create a new project and give a name to it.
3. Create a new Billing account by adding your credit card details by going to `Google Cloud Console > Navigation Menu > Billing > Create`
4. Enable Google Cloud TTS API Service. Pricing details are available on the [tts pricing page](https://cloud.google.com/text-to-speech/pricing)
5. For sending the conversion requsts to google cloud generate an API Key by going to `APIs & Services > Credentials > Create Credential > API Key`
6. Copy the API key.
7. Open `pipeline.properties` file in any ascii editor from the location `C:\Program Files (x86)\DAISY Pipeline 2\daisy-pipeline\etc` 
8. Create a new file `config.xml` the follwing contents and save it to the computer.
```html
  <config>  
    <property key="org.daisy.pipeline.tts.google.apikey" value="Your_API_Key"/>
    <property key="org.daisy.pipeline.tts.log" value="true"/>
    <voice engine="google" name="en-US-Standard-A" gender="MALE" priority="100" lang="en-US"/>
    <property key="org.daisy.pipeline.tts.google.samplerate" value="24000"/>
  </config>
 ```
9. Uncomment the the lines as given below and enter the 'Path to config.xml' and the API Key at the place `Your_API_Key`
```
## File to load TTS configuration properties from at start-up
org.daisy.pipeline.tts.config= Path to config.xml

## Allow dynamically setting of TTS properties (default "true")
org.daisy.pipeline.tts.host.protection=true

## Temporary directory used during audio synthesis (default "/var/folders/mr/f6s9zqtn03d8rgzxb96_2bh00000gn/T/")
org.daisy.pipeline.tts.audio.tmpdir=/tmp

# Google Cloud TTS settings
org.daisy.pipeline.tts.google.apikey=Your_API_Key
org.daisy.pipeline.tts.google.samplerate=22050
org.daisy.pipeline.tts.google.priority=15

```

The configuration properties can be changed as per the requirments. You can refer to the [list of voices and languages](https://cloud.google.com/text-to-speech/docs/voices) supported by Google Cloud TTS. To know more about tts configuration file refer to [TTS user guide](http://daisy.github.io/pipeline/Get-Help/User-Guide/Text-To-Speech/) of DAISY Pipeline 2. <br>


## Converting an EPUB file to DAISY Audio
1. Open DAISY Pipeline 2 sotware from the start menu
2. Click on `File` and click on `New job`
3. Select `EPUB to DAISY` option
4. Enter the path of the EPUB file
5. Enter the path for storing the temporary files which will be generated during the conversion
6. Enter the path for storing the intermediate files which will be generated during the conversion
7. Enter the path for storing the coverted DAISY 2.02 file
8. Enter the path for storing the coverted DAISY 3.0 file
9. Enter the path for the TTS config file 'config.xml' which was created earlier
10. Change 'Perform text to speech:' seeting to `true` from `default`
11. Press 'Run'
12. Open the and play the DAISY files with the help of [AMIS](https://daisy.org/info-help/document-archive/archived-projects/amis/) software.

If you face problems during any of the steps, Please report the issue or mail to abhishekbaghel05@gmail.com 
