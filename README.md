# CroMa - Crowd Management Software
CroMa is an android application that uses a python backend hardware, built on raspberry pi integrated with a firebase real-time database, and flutter framework for efficient crowd management in public transports such as buses & taxies. The hardware is effectively a handheld ticketing machine used for printing tickets, and collecting selective information about passengers. After data processings, the mobile application displays the output to the users. No LogIns required.

The project development started in April 2022 as a group project and has been licensed under the Creative Commons Attribution - Non Commercial - No Derivs License (CC-BY-NC-ND). The passenger data collected, is maintained as per the Privacy Policy. The Pull Requests are maintained by a team of contributors. Learn more about CroMa software here

# SubDirectories and Constraints
### Software Dependencies
• **Mobile App:** Dart, Flutter, Maps SDK, Places SDK, Distance Matrix API, Directions API, Roads API, and Geocoding API
<br>
• **Ticket Machine:** Python 3.7, Firebase (Real-Time Databases), RaspberryPi and ArduinoUNO| Dependencies: Pyrebase

### Files and SubDirectories
• **Mobile Application:** This directory contains the Dart code and afilliated resources for building the flutter application
<br>
• **Ticketing Machine:** This directory contains the Python3 code for designing the hand-held ticketing machine, and DB

All relevant updates, and stable versions are made available in the ~/stableVersion sub-directory. Some subdirectories may be sensitive for the project and may trigger review requests, when pull requests touch these files. Github handles with commit rights made available in the ~/Template Files/CODEOWNERS are responsible for reviewing such changes

# User Installation and Working
CroMa is a firmware solution that provides commuters with real-time information about public transits(such as buses) including real-time tracking, estimated time-of-arrival and the seat occupancy. This solution is an inter-working of two major components: a handheld ticketing machine and a mobile application. CroMa v1.0 offers support for only buses.

The hand-held ticketing machine is a micro-controller-based system used for generating billing tickets and collecting, saving, and generating daily reports and summaries. Our version of the hardware is additionally equipped with a GPS module for tracking the location of the bus. The device is to be used by conductors, and/or clippies for issuing tickets to the passengers. When new passengers board this bus, their details such as their start location, total luggage in the bus, their intended destination, & the total number of passengers is collected for issuing the tickets. These details are collected, processed and transmitted to the FireBase RT database by the hand-held ticketing machine. For passengers using a monthly, or yearly bus pass, a QR code or a unique alphanumerical code may be used to update the software.

The passengers data is maintained in the FireBase Real-Time database for synchronizing this data across devices. This data is structured as a JSON tree with the data points stored as JSON objects. The parent nodes represents the Bus Id (unique to each bus) and the real-time data associated with the bus (including available seats, & current location, etc) are maintained as nested nodes. Whenever a new ticket is issued the database is updated. The algorithm ensures that the database is updated when passengers de-board the bus. The data maintained in this FireBase RT database is then made available to be fetched by the android mobile application, and the relevant machine learning models, and API's.

The android app is the end-user's application that allows the user to compare various transit options, and choose the most ideal option that fits their needs. The users start with opening the application, and making a query, by entering their starting point, intended destination, and the type of bus (fast, SPF, express, deluxe, etc). No LogIn is required for using the android mobile app. The application looks up into the DataBase, and displays the location of buses in real-time within a pre set radius that passes through both their starting point and the destination entered by the user. The bus markers with red colour indicates heavy rush, while the green color indicates light occupancy. On tapping a given bus marker, the application displays more details about that bus to the users including, their estimated time of arrival, seat occupancy & ETA of buses on same route etc. Users can compare multiple options to make an informed decision.

To run the streamlit application on a local computer, open the terminal, install streamlit and then type the command:

To run the ticketing machine's sofware on a local computer, open the terminal, install pyrebase & type the command:
```
python ticketingMachine.py
```

CroMa's development take place on GitHub. Please submit any bugs that you may encounter to the issue tracker with a reproducible example, demonstrating the problem in accordance with the issue template present in contributing files.

```
├── assets
├── android                       // Files required for running the application on an Android
│   └── Images
├── ios                           // The files required for running the application on an iOS
├── macos
├── linux
├── lib                           // Contains main.dart which is the flutter apps entry point
│   ├── screens                      
│   └── main.dart          
├── pubspec.yaml                  // Contans the metadata & configuration specific to the app
├── web
│   └── icons
└── pubspecam.lock                // It contain the version of each dependencies and packages
```

To run the application start debugging by clicking Run > Start Debugging from the main IDE window, or press F5. If you are using VS Code, you should see a set of Flutter specific entries in the status bar, including a Flutter SDK version and a device name (or the message No Devices). The Flutter extension automatically selects the last device connected. However, if you have multiple devices/simulators connected, click device in the status bar to see a pick-list at the top of the screen. Select the device you want to use for running or debugging.


# Contribution Guidelines
To start contributing to the project, clone the repository into your local system subdirectory using the below git code:
```
git clone https://github.com/ashwinraj-in/Kiwi.git
```
Before cloning the repository, make sure to navigate to the working subdirectory of your command line interface and ensure that no folder with same name exists. Other ways to clone the repository includes using a password protected SSH key, or by using Git CLI. The changes may additionally be performed by opening this repo using GitHub Desktop

### Edit the Source Code and Make Desired Changes
To be able to make changes to the source, you may need to install and use a python IDE such as PyCharm, Microsoft VisualStudio and/or any other python interpreter. You will also require a Jupyter notebook  for working with the code snippets. The movies posters are fetched using the [TMDb's API](https://developers.themoviedb.org/3). You may create your own API by logging into TMDb developers API-3. Ensure that you are strictly following the basic coding standards, while making the desired change

### Submitting a Pull Request
Before opening a Pull Request, it is recommended to have a look at the full contributing page to make sure your code complies with all the pull request guidelines. Please ensure that you satisfy the [~/checklist](https://github.com/thisisashwinraj/VerticalX-Recommendation-System/tree/main/Template%20Files/PULL_REQUEST_TEMPLATE) before submitting your PR.

Navigate to this subdirectory & check status of all files that were altered (red) by running the below code in Git Bash:
```
git status
```
Stage all your files that are to be pushed into your pull request. This can be done in two ways - stage all or some files:
```
git add .            // adds every single file that shows up red when running git status
```
```
git add <filename>   // type in the particular file that you would like to add to the PR
```

Commit all the changes that you've made and describe in brief the changes that you have made using this command:
```
git commit -m "<commit_message>"
```
Push all of your updated work into this GitHub repo in the form of a Pull Request by running the following command:
```
git push origin main
```
All pull requests are reviewed on a monthly rolling basis. Your understanding is appreciated during the review process
