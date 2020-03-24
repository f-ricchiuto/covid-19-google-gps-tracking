# Covid-19 Coronavirus - Google GPS Tracking
The intent of this project is to reuse the GPS tracking data already acquired on phones where Google Maps is installed.

# Important
This project is not "aggressive" with the user privacy, as it use data **already stored** on Google servers. An Android user usually accepts to share this information with Google, during the first boot of his phone (Google Account pairing).

## How it works
When a user installs the Google Maps App on his personal device, then his movements are tracked day by day (if the user has given consent to track position).
The intent of this service is to get this tracking data, and compare it with the movements of people reported as infected by the virus, plus, if possible, link each infection case to the one which it's coming from. 

## Access Google tracking history
As you can read in (this)[https://stackoverflow.com/a/17626982/5871709] StackOverflow thread, it's easy to get each user's history. 

## Project Requirements
In order to work on this project, it's mandatory to verify if tracking data collected by Google Maps it's accessible by thirdy party apps through usage of Google Maps APIs. You can see this data in your Google Maps -> History.

## User requirements 
In order to work, and respect the final users privacy:
  1) Each user must download the app, and explicitly accept to share his/her personal GPS tracking data with the platform
  2) When a user manifests symptoms, attributable to a possible/confirmed Coronavirus infection, then he can: 
    + Report himself as infected (confirmed by official test)
    + Report himself as probably infected (waiting for test result) 
    
## How an Infection Report is processed
As long as an infection report has been sent by a suspicious/confirmed user, the platform:
  1) Counts N days of incubation period, since when first symptoms appeared and have been reported.
  2) Takes the GPS tracking points of the infected user in the date interval reported in point 1, and saves each of them as "infection points"
  3) Emits an infection alert which is received by each device on which the app is installed, not owned by the infected person. The alert contains an "infection id"
  4) Each device where the app is installed receives the infection alert
  5) The first check is about the **country** of the collected tracking data of the infected person. If the country is the same, the verify continues
  6) Same thing is done for region / province 
  7) If in any case, the infection tracking data matches the final user movements in the date period linked to the infection report, then he/she is informed about a possible contact with an infected person, so he/she needs to stay in quarantine, until symptoms appear or not. 
  8) Is asked to the alerted user if he has already some symptoms of infection. In that case, he/she is tracked as possible infection spread from the previous case (just to track infection spreading path)
  
## If the infected person is not able to use the app, due to severe condition
In order to allow the spreading of an alert in the case when the infected user is not able to use the app, an option may be to use the mobile phone number to identify the user, and send the alert from another device.
This because the infected user may have configured a password to access his/her phone, making his device not usable by another person. 

There will be likely an unlocked version of this app, intended to be used only by Health Care professionals. This figures are able to report an infection on the infected person behalf, by inserting his/her mobile phone number.

Healt Care professionals must get an unlock code released by authorities in order to use this functionality. Otherwhise unauthorized/unprepared people would be able to send incorrect warnings.
