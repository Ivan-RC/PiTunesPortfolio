<table>
    <tr>
        <td align="center"><h1>PiTunes</h1></td>
    </tr>
    <tr>
        <td align="center" colspan="3"><h3><i>The voice-controlled music player</i></h3></td>
    </tr>
</table>

Introduction
--------------------------------
For the project, the team will be programming a music player using a raspberry pi that can be controlled with the user's voice. It will not have a display or any sort of frontend, making it a "headless" pi. This project is based around music and making it more convenient to listen to. It has always been a struggle for most people to find a convenient way to listen to music, and that is the problem the team wishes to solve. 

High-level solution of the problem
--------------------------------
The user can speak to the Raspberry Pi through a USB mic connected to it. However, before being able to give the device any kind of command, the user must "wake it up" by saying 'Hey Iris'. After that, the user will provide any string of words to the application (on the Raspberry Pi) and it will go and do something depending on the command. The Raspberry Pi will speak back to the User once a valid, or invalid, command have been received through a speaker connected by 3.5 mm jack. The application will process the user's speech, do what the user requested, and let the user know what it did. 

![alt text](https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/highlevelsolution.PNG)

Features
--------------------------------
- Wake up the System
- Play a song
- Play an album/playlist
- Pause/resume
- Change song
- Repeat
- Shuffle
- Control volume
- Seek

Flowcharts
---------------------------------
<table>
    <tr>
        <td align="center"><b>Wake up the System</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/wakeup.PNG"/></td>
        <td align="center"><b>Play Song</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/playsong.PNG"/></td>
    </tr>
    <tr>
        <td align="center"><b>Pause Song</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/pausesong.PNG"/></td>
        <td align="center"><b>Play album/playlist</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/playalbumplaylist.PNG"/></td>
    </tr>
    <tr>
        <td align="center"><b>Next Song</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/next.PNG"/></td>
        <td align="center"><b>Previous Song</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/previous.PNG"/></td>
    </tr>
    <tr>
        <td align="center"><b>Repeat On</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/repeaton.PNG"/></td>
        <td align="center"><b>Repeat Off</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/repeatoff.PNG"/></td>
    </tr>
    <tr>
        <td align="center"><b>Set Volume</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/setvolume.PNG"/></td>
        <td align="center"><b>Seek</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/setposition.PNG"/></td>
    </tr>
    <tr>
        <td align="center"><b>Shuffle On</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/shuffleon.PNG"/></td>
        <td align="center"><b>Shuffle Off</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/shuffleoff.PNG"/></td>
    </tr>
</table>

Hardware
--------------------------------
- CanaKit Raspberry Pi 4 Model B
- 1.5GHz 64-bit quad-core CPU (4GB RAM)
- Raspberry Pi 4 Case
- Set of heat sinks
- System fan
    <br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/RaspberryPi.jpg"/></td><br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/RaspberryPiPorts1.jpg"/></td><br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/RaspberryPorts2.jpg"/></td><br>
- Mini USB Microphone (Adafruit Industries)
    <br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/Microphone.jpg"/></td>
- Aux cord
    <br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/AuxCord.jpg"/></td>
- Beats Pill Speaker
    <br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/Pill.jpg"/></td>
- PiTunes
    <br>
    <img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/PiTunes.jpg"/></td>

Software
--------------------------------
- Raspberry Pi OS (Raspbian)
- PyCharm Community Edition (v2021.2.3)
- Python 3.7
- Python application
    - python-youtube (v0.8.1)
    - omxplayer-wrapper (v0.3.3)
    - yt-dlp (youtube-dl)
    - pyttsx3 (v2.90)
    - YouTube Data API v3
    - Google Cloud’s text to speech API

System Design
---------------------------------
<table>
    <tr>
        <td align="center"><b>Physical Architecture</b><br>
            Below is the physical design of the project, it includes all the physical components that will make it work. The Raspberry Pi 4 Model B will have two peripherals connected to it, a microphone by Adafruit Industries, and a Beats Pill speaker. The microphone is very small, and through a USB interface, it works well with the Raspberry Pi OS. ¬The speaker has two separate connections, one to charge it, and the other to output the audio that will be playing on the device. Through a Wi-Fi connection, the Raspberry Pi will make calls out to the Google Cloud API every time the user speaks to it, and the YouTube Data API whenever the user requests that a song, album, or playlist, be played. 
            <br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/physicaldiagram.PNG"/></td>
        <td align="center"><b>Logical Architecture</b><br>
            Below is a high-level logical solution design, which depicts the APIs, modules, and libraries, and how these will all work together. The TextToSpeech module will communicate directly to the USB mic with the use of the ‘pyttsx3’ library, and Google Cloud’s Text-to-Speech API. The Utility module is where all the communication to the YouTube Data API is done. The communication to the API is done by using a wrapper called ‘python-youtube’. Anytime the user asks something that requires a call to the API, the Utility module will be used. In the same module, the song will be downloaded using the link specific to it which was returned from the call to the API. The library that will be used to do this is ‘yt-dlp (youtube-dl)’. On the other hand, the user can ask something that does not require a call to the API (i.e., changing the volume), in this case, the Utility module will be skipped, and the program will just use the Music module. In the Music module, the library used is ‘omxplayer-wrapper’. 
            <br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/logicaldiagram.PNG"/></td>
    </tr>
</table>

