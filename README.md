Appium Mobile Automation Framework
Framework for Mobile test automation (Native app and Browser) on Android and IOS devices 📱


🚀 Quick Start - Appium set up on Windows (Android):

Install Java JDK8
and IntelliJ IDEA

Install NodeJS

Install Android studio

Install Appium Server using npm (CLI) command npm install -g appium. Appium server version 1.22.1


Command to check the installed appium version: `appium --version`



Add below Android SDK path in the environment variable


    - ANDROID_HOME = <path to Sdk folder>
    - %ANDROID_HOME%\tools
    - %ANDROID_HOME%\tools\bin
    - %ANDROID_HOME%\platform-tools



Install Appium desktop

Install Appium Inspector



🚀 Quick Start - Appium set up on MAC (Android):

Install Homebrew
Install NodeJS

Install Java JDK8
and IntelliJ IDEA

Install Appium server using npm (CLI) or Appium desktop client
Install Android studio

Install Appium Inspector

Set JAVA_HOME and ANDROID_HOME environment variables


📌 Appium Doctor to verify the installations

Install appium-doctor using command npm install -g appium-doctor

To view the list of available options appium-doctor --help



To check Android set up `appium-doctor --android`
To check ios set up `appium-doctor --ios`



📌 Creating Android Virtual Device (Emulator) from Android Studio:

Open Android Studio.
Click on Tools -> AVD Manager -> Create Virtual Device -> Select the device and OS version -> Finish.
Once Virtual device is created, click on Launch this AVD in the emulator.
Command to view the list of devices attached adb devices



📌 Android Real Device Set up:

Connect Android real device to the machine(Desktop/Laptop)
Turn on the developer options in android mobile
Enable USB debugging
Run command adb devices in cmd prompt to check whether the device is recognised


📌 Mirror android/ios device to your desktop

Download Vysor



📌 Start Android Emulator from Command line

Open command prompt, go to <sdk emulator path>



Command to stard AVD: `emulator -avd <avd_name>`
Command to stop/kill AVD: `adb -e emu kill`



📌 Pushing the App (.apk file) to Android Emulator:

Copy the .apk file and paste it in the path - <path to sdk platform-tools>

Open the cmd terminal from the directory where APK file is placed and enter command adb install <apk filename>



📌 Android - Finding appPackage and appActivity:
If the app is already installed on your device then we can make use of appPackage and appActivity to launch the app
 Option 1 : 

Open the app on the device, for which appPackage and appActivity is required.
Open powershell and enter command adb shell dumpsys window | grep -E 'mCurrentFocus|mFocusedApp'
NOTE: This command may not work for newer Android OS (10 or 11). In that case, use command:
adb shell "dumpsys activity activities | grep mResumedActivity"


 Option 2 : 
Install  APK info  app to retrieve appPackage and appActivity for the app installed in your device

📌 Inspecting Elements

uiautomatorviewer

Go to the path - <path to sdk folder>\tools\bin\

click on uiautomatorviewer

On the UI Automator Viewer, click on Device Screenshot (uiautomator dump). Ui automator will capture the screenshot
of current open screen in the device.



Appium Inspector

Start the Appium Server and connect with Real device/Emulator.
Open Appium Inspector app and provide the appium server details and Desired Capabilities.



Click on Start session which will start the appium inspector with layout shown below.



📌 Inspecting Element for mobile web browser

Type url `chrome://inspect/#devices` in the desktop chrome browser and start inspecting element




📌 Launching Android Emulator Automatically
Add below lines in the Desired capabilities

capability.setCapability(AndroidMobileCapabilityType.AVD, "Pixel_3a");
capability.setCapability(AndroidMobileCapabilityType.AVD_LAUNCH_TIMEOUT, "180000");



📌 Auto Discovery of compatible ChromeDriver
Start appium server using command appium --allow-insecure chromedriver_autodownload

📌 Auto download of compatible ChromeDriver programmatically
Add below line in the AppiumServiceBuilder

AppiumServiceBuilder builder = new AppiumServiceBuilder();
builder.withArgument(GeneralServerFlag.ALLOW_INSECURE, "chromedriver_autodownload");



📌 Start Appium server programmatically
Use AppiumServiceBuilder and AppiumDriverLocalService to start the server programmatically Set environment
variable APPIUM_HOME = <path to npm folder>\node_modules\appium\build\lib where main.js file is present

📌 Key Features
👉 Supports Android and iOS Real Devices and Emulators.
👉 Ability to start and stop the appium server on run-time. Configurable through config.properties
👉 Supports capturing appium server logs on run-time.
👉 Page object model design.
👉 Supports parallel and sequential execution of tests.
👉 Ability to capture screen(video) recording of tests on Android and iOS. Configurable
through config.properties
👉 Supports capturing screenshots for passed/failed/skipped steps which is configurable
through config.properties
👉 Ability to retry failed tests which is configurable through config.properties
👉 Customised exception handling to provide the exceptions in a meaningful way.
👉 Custom framework annotation to provide author name and category for each test.
👉 Supports utilities to read test data from excel workbook and provides data to each test based on the test
name.

📌 Running tests through Maven
👉 Run test using command mvn test -Dsurefire.suiteXmlFiles=<provide the testng xml to execute>

📌 Running tests through testng xml
👉 Create or Select the required testng xml -> Right click and select Run

📌 Custom Configurations in config.properties


📌 Report (Extent reports)

