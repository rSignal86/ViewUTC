# ViewUTC - Simple HTML Dashboard for radioamateurs

# About the Project
ViewUTC is a lightweight, local HTML application that displays relevant data from various sources directly in your browser. No installation is required – just double-click the HTML file to start.

# Features
Displays real-time data, including the K-index, solar activity (SFI, A-Index, Sunspot Number), and radio band conditions.
Automatically updates with the latest data from public sources.
Runs entirely locally without the need for external software.
No data is stored or transmitted – the program only fetches information for display.
Supports both day and night modes for radio band conditions.

# How to Use
Download the ViewUTC.html file by clicking this link https://github.com/rSignal86/ViewUTC/blob/main/ViewUTC.html
Place the file on your desktop or in a desired folder.
Double-click the file to open it in your browser.
The magic happens automatically – (Almost)real-time data is loaded and displayed in a simple dashboard while you can the ham licensed wizard in the sky! 

# Future development requirements
All future versions, whether created by the original author LB6QJ or contributors on github or any other platforms, must be contained within a single file. This ensures ease of use for all users when downloading new versions and maintains platform independence across Windows, Mac, and Linux.

# Privacy/security and updates
This program is only available on GitHub and is not distributed elsewhere. It is designed with privacy in mind and complies with the General Data Protection Regulation (GDPR). 
It does not upload personal data from your computer to me or third parties, with one exception: the optional QRZ search feature, where a callsign you enter is sent directly to QRZ.com upon your request. 
The program performs a daily GitHub version check by querying `https://api.github.com/repos/rSignal86/ViewUTC/releases/latest`. This fetches public release info to notify you of new versions without sending any personal data. If a message appears at the bottom of the dashboard indicating a new version, you can manually download the latest `ViewUTC.html` from https://github.com/rSignal86/ViewUTC. There is no automatic update mechanism, and none will be implemented due to privacy concerns. To update, replace the old file (recommended to store it on your desktop for easy access) with the new one.
For full details on how your data is handled, including the QRZ search feature, please refer to our [Privacy Policy](https://github.com/rSignal86/ViewUTC/blob/main/Privacy.md).

# people with disabilities
I am very keen that everyone should benefit from this program, so I try to make it accessible to people with visual and hearing impairments. 
I have included buttons that users can click to have certain values ​​read out to you. There are functions in the browser that allow you to make text to speech work with a synthetic voice, this is done with the "Web Speech API"

# Technical Information
Built with HTML, CSS, and JavaScript (no server required).
Data is fetched from open APIs like NOAA for geophysical and solar conditions.
Requires an internet connection to retrieve updated data.

# License
This project is open and free to use. Contributions and improvements are welcome!

# Version number interpretation
The first number is determined by three numbers the first number is a major version update the second number is say minor update like adding a small function and the last number indicates that it is a bug fixed to the small function. A good example is version 2.5.1 which is a bug fix for version 2.5

73 de LB6QJ 🚀
