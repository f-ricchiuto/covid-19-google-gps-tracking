# Covid-19 Coronavirus - Google GPS Tracking
The intent of this project, is to reuse the GPS tracking data, already acquired on phones where Google Maps is installed.

# Important
This project is not privacy "aggressive", as it uses data **already stored** on Google servers*. 

## How it works
When a user installs the Google Maps App on his device, then his movements are tracked day by day**.
The intent of this service is to get user's tracking data, and compare it with movements of other registered users. reported as infected by the virus, plus, if possible, link each infection case to the one which is coming from. 

## How to get Google tracking history (client-side) 
As you can read in [this StackOverflow thread](https://stackoverflow.com/a/17626982/5871709), it's easy to get each user's history. Just call the url after having the user authenticated with Google Services.

## Project Requirements
Not every user is registered with Google, anyway probably there are other alternatives out there, meeting the users plethora.
Google has a large diffusion rate among world population and can be used to build a first proof of concept version.

## User requirements 
In order to work, and respect the final user privacy:
  1) Each user must download the app, and explicitly accept to share his/her personal GPS tracking data with the platform, that will be used in the scope defined in the previous points.
  2) When a user manifests symptoms, attributable to a possible/confirmed Coronavirus infection, then he can: 
    + Report himself as infected (confirmed by official test)
    + Report himself as probably infected (waiting for test result) 
  3) An user will never be identified by direct reference, it will just be reported as an "infected user" or "not infected user", but nobody in the platform will be ever able to identify another person by its name and medical status.
    
## How an Infection Report is processed
As long as an infection report has been sent by any suspicious/confirmed user, the platform:
  1) Takes in account N days of incubation period, since the date when the user reported that the first symptoms appeared.
  2) Takes the GPS tracking points/movements,  of the infected user in the date interval verified at point #1, and saves each one of them as "potential infection points/movements".
  3) Emits an *infection alert* which is received by each device on which the app is installed, not owned by the infected person. The alert contains an "infection id".
  4) Each device where the app is installed receives the infection alert, identified with an *infection id*.
  5) The first check is done around the **country** where the infection alert is coming from. If the country is the same as where the current user is, then the verification process continues.
  6) Same thing is done for region / province, until the area of interest is restricted as much as possible. 
  7) If in any case, the *infection tracking data* matches the *current user movements* in the *date period* linked to the *infection report (id)*, then he/she is informed about a possible contact with an infected person, so it's better if he/she stays in quarantine, until symptoms appear or not***. 
  8) The alerted user, is prompted with another question, asking if he has already noticed some symptoms. In case he/she replies *yes*, he/she is tracked as possible infection spread from the previous case (just to track infection spreading path).
  9) Regarding the previous point, the *notification chain* can continue to send alerts to users who have been in contact with the one who replied "yes" to the question "do you have any symptoms?". As long as it encounters an infected ratio underneath the 10% value, the chain can continue to spread alarms, just to inform people. 
This is useful to locate the current infection "borders". 
  
## If the infected person is not able to use the app, due to severe condition
In order to allow the spreading of an alert in the case when the infected user is not able to use the app, an option may be to use the mobile phone number to identify the user, and send the alert from another device.
This because the infected user may have configured a password to access his/her phone, making his device not usable by another person. 

There will be likely an unlocked version of this app, intended to be used only by Health Care professionals. This figures are able to report an infection on the infected person behalf, by inserting his/her mobile phone number.

Healt Care professionals must get an unlock code released by authorities in order to use this functionality. Otherwhise unauthorized/unprepared people would be able to send incorrect warnings.

## If the person has downloaded the app, but he/she has not registered or logged in:
In this case, the app can only receive live alerts, informing that there's an infected subject nearby. Nothing else can be done until the person does the login, in order to understand if all the permissions are ok for position tracking & matching. 

### Footnotes
* *For example, an Android user usually accepts to share his tracking data with Google, during the first boot of the phone (Google account pairing).*
** *Only if the user has given consent to Google to track his position!*
*** *If that behavior is not possible, at least the user can give more attention to virus containement measures, as he/she has an higher chance of being infected*
