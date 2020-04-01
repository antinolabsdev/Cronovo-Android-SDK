# Cronovo-SDK-Android
[![Android API23+](https://img.shields.io/badge/Android-API_23+-green.svg)]()
[![Java 6+](https://img.shields.io/badge/Java-6+-red.svg)]()
[![License Apache 2.0](https://img.shields.io/badge/license-Apache%20License%202.0-red.svg)]()
## Requirements
- Android Lollipop, 5.1 (API level 23+)
- Android Studio 2.0+
- Java 7+
(SuperBot Works also with pure Java projects)
## Usage:
If you are setting up a new project, you need to install the SDK.
## Setup SuperBot SDK
## Step 1. Add the JitPack repository to your build file
Add it in your root build.gradle at the end of repositories:
allprojects {
repositories {
...
maven { url 'https://jitpack.io' }
}
}
## Step 2. Add the dependency
dependencies {
implementation 'com.github.antinolabsdev:Cronovo-Android-SDK:1.0'
}
## Step 3. Write compileOptions in
android{
compileOptions {
sourceCompatibility JavaVersion.VERSION_1_8
targetCompatibility JavaVersion.VERSION_1_8
}
}
## Step 4. Write these line in our code

### Database:
- We have used SQLite Database to store data.
- Database table has 11 fields (position, signal, hrm, timesec, timems, cadence, steps, vo2,
calories, entrytime, date).
- We are also saving user information in the database like age, weight, height.
- The data to be inserted should be in the form of an array of integers.
- Format of data should be like this [position, signal, hrm, timesec, timems, cadence, steps,
vo2, calorie] and time and date will be calculated in the Framework only.
### Data Insertion:
- There is a public function to allow the user to insert data from the watch into the database
- Here data must be in an array of integers [position, signal, hrm, timesec, timems, cadence, steps, vo2, calorie]
### Read User Data from Database:
```
getUserDetails()
```
- This will return an array for Integers in order [Age,Height,Weight]
### Delete Database:
- This method can be used to delete the database in any case:
```
deleteData()
```
### Methods to calculate app functionalities:
- There are some public methods to calculate the result for the algorithms
### Cardiac Efficiency
- This method can be used to calculate the cardiac efficiency of a person over a given period.
- User can calculate the cardiac efficiency for the following periods:
1. Daily
2. Weekly
3. Monthly
4. All Time
```
cardiacEfficiency(forTime: Duration)
```
- The input will be the duration for the cardiac efficiency (.Daily, .Weekly, .Monthly, .All Time).
- The output will be in a string format.
### Resting Heart Rate
- This will return the average heart rate of 1minute.
```
getRestingHeartRate()
```
- The output will be in a string format.
### Heart Rate Recovery
- This method can be used to calculate the recovery rate of a person over a given period.
- This method can be used to calculate the results over a period of 30sec, 60secs or
120secs.
```
heartRateRecovery(forTime: RecoveryTime)
```
- The input will be the recovery time (.ThirtySec, .SixtySec, .OneTwentySec).
- The output will be in a string format.
### Heart Rate Zone
- This method can be used to get the range of heartbeats for the different zones.
- There are five heart rate zones.
1. Zone1(50-60% of HRR)
2. Zone2(60-70% of HRR)
3. Zone3(70-80% of HRR)
4. Zone4(80-90% of HRR)
5. Zone5(>90% of HRR)
- The Range of heartbeats will vary according to the age of the user.
```
heartRateZone (zone: HeartZone, Age: Int)
```
- The input will be the zone (.Zone1, .Zone2, .Zone3, .Zone4, .Zone5) and age of the user.
- The output will be in a string format (e.g. 120-135 bpm).
### VO2 Max
- This method can be used to calculate the cardiovascular fitness of the user (VO2 Max).
- This method will calculate the VO2 Max for the present date.
```
getVO2Max()
```
- The output will be in a string format.
### Heart Rate Variability
- This method can be used to calculate the heart rate variability of the user (HRV).
- This method will calculate the HRV for the present date.
```
getHRV()
```
- The output will be in a string format.
### RRi
- This method can be used to calculate the RR interval of the user.
```
getRRi()
```
- The output will be in a string format.
### Core Temperature
- This method is used to calculate the Core temperature of the user while performing an exercise.
```
coreTemperature(scale: Scale)
```
- The input will be the scale in which output is required (Celsius or Fahrenheit)
- The output will be in a string format.
### Weekly Training Effect
- This method is used to calculate the credits according to the exercise performed by the user in different zones (Moderate or Intense).
```
trainingEffect(Age: Int, StartTime: Int64, StopTime: Int64)
```
- The input will be the Age of the user, Exercise Start and Stop time.
- The output will be in a Dictionary format.
- User will get the values from the dictionary like this:
1. data = trainingEffect(Age: Int, StartTime: Int64, StopTime: Int64)
2. Moderate Time: data.value(forKey: "modTime") This will be an Integer.
3. Intense Time: data.value(forKey: "intenseTime") This will be an Integer.
4. Result: data.value(forKey: "Result") This will be a String.
## Contributing
- If you **need help** or you'd like to **ask a general question**, contact us
- If you **found a bug**, open a service request.
- If you **have a feature request**, open a service request.
- If you **want to contribute**, submit a pull request.
## Acknowledgements
Made with :heart: by [Antino Labs](https://www.antino.io/)
## License
jitpackjitpack
JitPack | Publish JVM and Android libraries
JitPack makes it easy to release your Java or Android library. Publish straight from GitHub or Bitbucket.
antino.ioantino.io
Antino Labs Private Limited | Android, iOS & Web Apps Development Company
Antino Labs is a leading iOS; Android; web application development company in the world. We deliver the best design and strategy for mobile apps from startups to enterprises.'Our clients see software as a source of growth, as a way to create their next flagship product.' Contact us today: +918436299719 or request a quote
5:05
https://github.com/antinolabsdev/Cronovo-Android-SDK
antinolabsdev/Cronovo-Android-SDK
Last updated
a few seconds ago
<https://github.com/antinolabsdev/Cronovo-Android-SDK|antinolabsdev/Cronovo-Android-SDK>antinolabsdev/Cronovo-Android-SDK | Today at 5:05 PM | Added by GitHub
