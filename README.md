# Cronovo-Android-SDK

## Requirements

- Android Lollipop, 5.1 (API level 23+)
- Android Studio 2.0+
- Java 7+
(Cronovo Works also with pure Java projects)
## Setup Cronovo SDK

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
            implementation 'com.github.antinolabsdev:Cronovo-Android-SDK:1.2'
    }
  

	
## Step 4. Create an Instance of Cronovo Class call there method. according to need
	
### Data Insertion:
- There is a public function to allow the user to insert data from the watch into the database
```
saveUserDetails(long signal, long hrm, long time_sec, long time_milli_sec, long cadence, long steps, long vo2, long calories, long entry_time, String date, Context context)
```


### Read User Data from Database:
```
getUserDetails(Context context)
```
- This will return an arraylist<UserDetails>[Age,Height,Weight].

### Delete Database:
- This method can be used to delete the database in any case:
```
deleteUserData(Context context)
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
getCardiacEfficiency(Cronovo.TimePeriod.Daily/.Weekly, Context context)
```
- The input will be the duration for the cardiac efficiency (.Daily, .Weekly, .Monthly, .All Time).
- The output will be in a string format.

### Resting Heart Rate
- This will return the average heart rate of 1minute.
```
getRestingHeartRate(Context context)
```
- The output will be in a string format.

### Heart Rate Recovery
- This method can be used to calculate the recovery rate of a person over a given period.
- This method can be used to calculate the results over a period of 30sec, 60secs or
120secs.
```
getHeartRateRecovery(Cronovo.RecoveryTime.THIRTYSEC, Context context)
```
- The input will be the recovery time (.THIRTYSEC, .SIXTYSEC, .ONETWENTYSEC).
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
heartRateZone(Context context, Integer Age, Cronovo.HeartZone.Zone1/Zone2)
```
- The input will be the zone (.Zone1, .Zone2, .Zone3, .Zone4, .Zone5) and age of the user.
- The output will be in a string format (e.g. 120-135 bpm).

### VO2 Max
- This method can be used to calculate the cardiovascular fitness of the user (VO2 Max).
- This method will calculate the VO2 Max for the present date.
```
getVO2MAX(Context context)
```
- The output will be in a string format.

### Heart Rate Variability
- This method can be used to calculate the heart rate variability of the user (HRV).
- This method will calculate the HRV for the present date.
```
 getHRV(Context context)
```
- The output will be in a string format.

### RRi
- This method can be used to calculate the RR interval of the user.
```
 getRRI(Context context)
```
- The output will be in a string format.

### Core Temperature
- This method is used to calculate the Core temperature of the user while performing an exercise.
```
getCoreTemperature(Context context)
```
- The input will be the scale in which output is required (Celsius or Fahrenheit)
- The output will be in a string format.

### Weekly Training Effect
- This method is used to calculate the credits according to the exercise performed by the user in different zones (Moderate or Intense).
```
trainingEffect(Context context, Integer Age, Long StartTime, Long StopTime)
```
- The input will be the Age of the user, Exercise Start and Stop time.
- The output will be in a Dictionary format.
- User will get the values from the dictionary like this:
 
## Contributing

- If you **need help** or you'd like to **ask a general question**, contact us
- If you **found a bug**, open a service request.
- If you **have a feature request**, open a service request.
- If you **want to contribute**, submit a pull request.


## Acknowledgements

Made with ❤️ by [Antino Labs](https://www.antino.io/)


## License
Cronovo is released under the MIT license. [See LICENSE](https://github.com/antinolabsdev/Cronovo-SDK-Android/blob/master/LICENSE) for details.

