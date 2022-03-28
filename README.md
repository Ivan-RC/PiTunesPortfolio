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

UML Diagrams
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
</table>

Hardware
--------------------------------
- CanaKit Raspberry Pi 4 Model B
    - 1.5GHz 64-bit quad-core CPU (4GB RAM)
    - Raspberry Pi 4 Case
    - Set of heat sinks
    - System fan
- Mini USB Microphone (Adafruit Industries)
- 3.5 mm jack
- Beats Pill Speaker

Software
--------------------------------
- Raspberry Pi OS (Raspbian)
- PyCharm Community Edition (v2021.2.3)
- Python 3.7
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
        <td align="center"><b>Physical Architecture</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/physicaldiagram.PNG"/></td>
        <td align="center"><b>Logical Architecture</b><br/><img src="https://github.com/Ivan-RC/PiTunesPortfolio/blob/main/images/logicaldiagram.PNG"/></td>
    </tr>
</table>
<!--
    - Capable of running any number of Web Servers, common Web Stacks, Databases, and Tools. Examples include:
        - Web Servers: Nginx and Apache (can be used to host  too)
        - Web Stacks: PHP (7.1 and 7.4), PHP 7.4 Laravel, Java Tomcat (8.5 and 9.0), ASP.NET Core 5.0
        - Databases: MySQL, PostgreSQL, MongoDB
        - Tools: Visual Studio Code, NodeJS Development Server
    - Deploy Web Sites, Java Spring and Spring Boot applications, PHP and PHP Laravel applications, Express, React, Angular applications-->
