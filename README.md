# Audeze LCD-GX Binaural Surround
This guide helps you set up a 7.1 surround audio system using Audeze LCD-GX planar headphones with EqualizerAPO software. It includes instructions for installing a virtual soundcard and configuring EqualizerAPO.

## Setup
If your soundcard does not support 7.1 channels, install a virtual soundcard to enable 7.1 channel support. This allows EqualizerAPO to apply binaural effects on all 8 channels before mixing the output into stereo channels for your left/right headphone speakers. Proceed to the next subsection "Install 7.1 Virtual Soundcard."

## Install 7.1 Virtual Soundcard
Several virtual audio loopback options are available online, but the most reliable one for this purpose is VB-Audio software. Four software options are available:
- Virtual Audio Cable (basic software)
- Voicemeeter (includes Virtual Audio Cable and additional features)
- Banana (similar to Voicemeeter with more features, such as live audio recording)
- Potato (untested)

This tutorial uses Banana. Install the software and reboot your system.

To prevent buffer underflows, follow these steps to increase the buffer size. You may optimize latency later by decreasing the buffer size, but this may introduce audio glitches.

1. Open "Virtual IO Control Panel."
2. Set the maximum delay to a high value (e.g., 32768) **and reboot**.
<img src="https://user-images.githubusercontent.com/3049704/234984863-4fe145af-d087-41d9-afc3-f1d2184a05bb.png" width="50%" height="50%">
3. Set the latency to a high value (e.g., 3x8192).
<img src="https://user-images.githubusercontent.com/3049704/234984932-2996b83d-2c22-403d-baa0-5412287b5b17.png" width="50%" height="50%">
4. Set the internal sampling frequency to 48 kHz.

Start Voicemeeter Banana (each time you boot your computer), and configure the A1 channel to be forwarded to your physical soundcard, like in the following screenshot:
![image](https://user-images.githubusercontent.com/3049704/234979333-c6a7e96f-0b3d-49ba-8e54-d025a118471d.png)

Proceed to the next step: install EqualizerAPO.

## Configure 7.1 Soundcard
1. Open the "Sound configuration panel" in Windows, go to the "Playback" tab, right-click on "VoiceMeeter Input," and select "Configure speakers."
2. Choose "Surround 7.1," click "Next."
3. Tick all checkboxes to disable high-pass filtering, click "Next."
4. Tick all checkboxes again, click "Next," and then click "Finish."
5. Right-click on "VoiceMeeter Input" again, select "Properties," go to "Advanced," and choose "24 bits, 48000 Hz (studio quality)."

**Warning:** Ensure the sampling frequency is set to 48 kHz. The binaural processing

### Physical soundcard
Repeat the same steps for your physical soundcard instead of "VoiceMeeter Input."

## Install EqualizerAPO
1. Download the software from https://equalizerapo.com/.
2. Install the software.
3. During setup, select the appropriate soundcard for DSP effects installation. For a virtual soundcard, select the virtual card (e.g., "Voicemeeter" device for Banana).

If you need to change soundcards later or troubleshoot, run the "Configurator" application to select the devices for EqualizerAPO.

## Configure EqualizerAPO
1. Download the configuration files from https://github.com/jeanibarz/audeze-lcd-gx-binaural-surround to "C:\Program Files\EqualizerAPO\config."
2. Launch the "Configuration Editor" application to edit EqualizerAPO's configuration.
3. Note: EqualizerAPO always uses the configuration file located at "C:\Program Files\EqualizerAPO\config\config.txt."
4. Clear the configuration by removing all effects, then add the "Control/Include (include configuration file)" effect.
5. Select the desired configuration file, such as "C:\Program Files\EqualizerAPO\config\audeze-lcd-gx-binaural-surround\eqapo_config\audeze_lcdgx_71_room_blocked_ear_48khz_14.txt".
6. After setup, the analyzer panel of EqualizerAPO should display something similar to the image in the link:
![image](https://user-images.githubusercontent.com/3049704/172075314-cf988b17-1aa8-4c38-872c-10510535a18a.png)


If you see a lot of red in the analyzer panel, it may be due to an incorrect sampling rate or the soundcard not being set to "Surround 7.1". Check the settings, exit the Configuration Editor, and restart it.

Now enjoy your immersive 7.1 surround sound!

PS: Use the "clear.txt" config file to quickly compare binaural and original sound (i.e., the headphones without effects other than attenuation). Adjust the gain for the same perceived sound level between the two settings (with and without binaural). If the default gain is not suitable, feel free to modify it.

For any issues, suggestions, feedback, or questions, please contact me at ibarz.jean@gmail.com or post an issue in this repository.
