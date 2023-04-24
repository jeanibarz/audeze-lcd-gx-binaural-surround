# audeze-lcd-gx-binaural-surround
EqualizerAPO configuration to listen 7.1 surround setup using Audeze LCD-GX planar headphones.

# Setup

If you have a soundcard that does not support 7.1 channels, you need to install a virtual soundcard to make your computer believe you possess such card, allowing EqualizerAPO to apply binaural effects on all the 8 channels before mixing the output into stereo channels to feed you left/right headphone speakers. Go to next subsection "Install 7.1 virtual soundcard"

## Install 7.1 virtual soundcard

There exists some virtual audio loopback available on the net, but the only one that works quite well for me is the ones provided in VB-Audio softwares.
There are 4 available software that can do the job:
. Virtual Audio Cable (most basic software)
. Voicemeter (included Virtual Audio Cable and provide some additional functionalities)
. Banana (same as Voicemeter, but with additional functionalities, such as the ability to record the audio in live).
. Potato (I didn't try this one)

In this tutorial, I will explain how to install and configure the soundcard using Banana.

Steps:
1. Install the software.
2. Reboot.
3. Open "Virtual IO Control Panel".


Now you are ready to skip to next step: install EqualizerAPO, the software that will be in charge of applying the binaural effects on the 8 virtual channels.

## Configuration 7.1 soundcard

### Virtual soundcard:
1. Open the "Sound configuration panel" of windows, "playback" tab, right-click on "VoiceMeeter Input" and "configure the speakers".
2. Select "Surround 7.1", click next.
3. Tick all the checkboxes to ensure the channels are not highpass filtered, click next.
4. Tick all the checkboxes again for the same reason, click next, and eventually click finish.
5. Right click on "VoiceMeeter Input" again, and now click "properties", then "advanced statistics", and select "24bits, 48000hz (studio quality)".

/!\ BEWARE: it's very important that the sampling frequency is set to 48khz, because the binaural processing done with EqualizerAPO relies on 48khz .wav files. If the sampling frequency is incorrect, the audio processing will be wrong AND the sound will have an enormous gain, which may damage your speakers or your ears. If you are not experienced with EqualizerAPO and the audio processing stuff, unplug your headphones during the setup until your are sure that everything is fine /!\.

### Physical soundcard

Follow the same steps, but using your soundcard instead of "VoiceMeeter Input".

## Install EqualizerAPO

1. Download the software from here: https://equalizerapo.com/
2. Install the software.
3. During the setup, you will be asked to install the DSP effects on the soundcard of your choice. This step is mandatory each time you change your soundcard. If you don't use a virtual soundcard, the device on which APO will apply the effects is your physical soundcard, hence select it. If you use a virtual soundcard, the device on which APO will apply the effects is your virtual soundcard, hence select this card (for Banana in this tutorial, tick the "Output A1/A2/A3 connectors of the "Voicemeeter" device)

If you skipped the step during the setup or you need to do some troubleshooting, you can select the devices on which APO is to be installed by running the application "Configurator" which should be found automatically by windows.

## Configure EqualizerAPO

1. Unpack the files found in the github repository (<url of the repository>) here: "C:\Program Files\EqualizerAPO\config".
2. Launch the "Configuration Editor" application, which should be found automatically by windows. It is the GUI of EqualizerAPO that allows you to edit the configuration used.
3. Thing to know: the configuration file used by EqualizerAPO is ALWAYS located in "C:\Program Files\EqualizerAPO\config\config.txt".
4. Clear the configuration by removing all the effects, then add an effect "Control/Include (include configuration file).
5. Select the latest configuration file you want to use. For example "C:\Program Files\EqualizerAPO\config\audeze-lcd-gx-binaural-surround\eqapo_config\audeze_lcdgx_71_room_blocked_ear_48khz_14.txt".
5. After setup, you should see something similar to this in the analyzer panel of EqualizerAPO:
![image](https://user-images.githubusercontent.com/3049704/172075314-cf988b17-1aa8-4c38-872c-10510535a18a.png)

If you see a lot of red in the analyzer panel, it's either because the sampling rate is not set correctly, or because the soundcard used is not set to "Surround 7.1". Check the settings, exit configuration editor, and start it again.

Now enjoy ! You can listen to 7.1 immersive sound !

PS: I made the "clear.txt" config file to do (fast) comparisons between binaural and original sound (i.e. the headphones without any effects other than an attenuation). Ideally, the gain should be set so that the perceived sound level between the 2 settings (with binaural / without binaural) is the same. If the gain I set is not appropriate for you, feel free to adjust it.

Don't hesitate to contact me at `ibarz.jean@gmail.com` or to post an issue in this repository if you run into some problems or have any suggestions, feedbacks, questions...