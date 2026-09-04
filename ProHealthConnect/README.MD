# ProHealthConnect

## Mobile App

**Description -** 

This is for the users who are the patient of the hospitals, where patient and all the staff members are connected with one epic ID for managing their data in that hospital.

### Libraries used -

```JSON
"dependencies": {
	"@notifee/react-native": "^9.1.8",
    "@react-native-community/datetimepicker": "^9.1.0",
    "@react-native-firebase/app": "^26.1.0",
    "@react-native-firebase/messaging": "^26.1.0",
    "@react-native/new-app-screen": "0.86.2",
    "@react-navigation/bottom-tabs": "^7.18.14",
    "@react-navigation/native": "^7.3.14",
    "@react-navigation/stack": "^7.10.17",
    "@reduxjs/toolkit": "^2.12.0",
    "axios": "^1.19.0",
    "formik": "^2.4.9",
    "react": "19.2.3",
    "react-native": "0.86.2",
    "react-native-config": "^1.6.1",
    "react-native-element-dropdown": "^2.12.4",
    "react-native-gesture-handler": "^3.1.0",
    "react-native-mmkv": "^4.3.2",
    "react-native-nitro-modules": "^0.36.5",
    "react-native-reanimated": "^4.5.3",
    "react-native-safe-area-context": "^5.5.2",
    "react-native-screens": "^4.26.2",
    "react-native-svg": "^15.15.5",
    "react-native-webview": "^14.0.1",
    "react-native-worklets": "^0.11.3",
    "react-redux": "^9.3.0",
    "redux": "^5.0.1",
    "yup": "^1.7.1"
}
```



### Basic App Setup -

Create React Native Project
Setup Navigation
Setup Global States
Setup APIs
Planned theme architecture for scalable UI development
Splash Screen
App Logo setup
Firebase setup
Push Notifications Setup and Socket Implemetation
Prototype workflow


### Modules

#### Onboarding

1. App Logo - boot splash screen
2. Animative splash screen - 
3. Onboarding functionality - 
	a. *Version Check* - application version check
	b. *Auto Login* - user authentication status

#### A. Authentication:

1. **Login -** Patients can login through email & password

2. **SignUp -** Patients can create their account using Name*, Email ID*, Phone number*, Date of Birth*, Gender*, Government ID(Optional), Password*, Confirm Password*

3. **Forgot Password -** Patient will enter the registered email ID, where he/she will receive the verificaition code.

4. **OTP Verification -** Verification code will be submitted here for changing the password.

5. **Reset Password -** Here Patient will change their password.

6. **FHIR Epic Login -** Patient can also log in to their epic account their epic account username and password. This will be optional for users to connect as they can login later.


#### B. Book Appointment:

1. **Select Speciality Areas -** Patient will select the doctor's speciality areas for filtering out the doctors that user need.

2. **Doctor Selection -** Patient can select the Doctors as shown in the list or carousel, and can filter the details of them by their speciality, Ratings, Price Range and spoken Language,

Here doctors will be shown with their profile containing details like: Profile Image, Name, Ratings with number of reviews, experience in years, Consultation Fee per session, and their field of speciality.

3. **Selecting the type of consultation -** Consultation can be of two types 1. Initial Consultation, 2. Follow up Consultation
	
	a. **Initial Consultation** - The time of consultation is of 60 minutes and the purpose of this is for when patient is having their first consultation with the patient for their treatment and since the time is more the doctors can charge more for it.

	b. **Follow Up Consultation** - The time of consultation is 30 minutes and the purpose of this is that it the consultation doctor to have a regular check with their patients that they taking their medication properly and the way their health is goingand since the time is only half an less the charge will be less as well.

4. **Time Slot Selection -** Here patient will be shown the available slots of the doctor accordingly to the consultation type they have selected. First they will select the day and then the slots for that day shown to them, from which they can select the time most favorable to them.

5. **Payment -** Here user will show the payment options using stripe, like pay using card details, or via google pay etc(what ever is available in stripe).

#### C. Call Enagagment:

1. **Upcomming Appointments -** Here patient can see their appointments and start their consultation. On click on Start button, patient will see a check permissions screen, where we will check whether the permissions are their for the consultation or not, if not then patient will not be allowed to go to the video calling screen.

2. **Call Handled via Notification -** Here When the doctor will call as he/she will have the power to start the call, the patient will get the call notification alert in their mobile phone which will open up the application this is where patient can attend their call.

3. **Video Calling -** Here Patient will connect with the doctor using opentok sdk, and will be able to attend to their consultation, also here doctor is only permissable to end call.

4. **Rating -** Here Patient can rate their consultation experience and add a review as well.

#### D. Profile:

1. **Edit Profile -** Here patient can see and edit their profile details.

2. **Change Password -** Here patient can change their password using their current password, then new password and lastly confirm password.

3. **Epic Account -** Here patient can check their status of their connection of the application account with epic account. On click , if user is not connected to the epic account, will be navigated to the Epic Login(as mentioned in Authentication Module).

4. **Logout -** Patient can logout their account from the application.

5. **Delete Account -** Patient can delete their account from the platform.

#### E. Medical History:

1. **Medical History -** Here paitent can see their appointment history, where patient can see their past appointments with the doctors review, medical report, prescription, and doctor's note for them


#### F. Transactions:

1. **Transactions -** Here patient see all the transactions they have made.

2. **Request refund -** Here Patient can request for refund over the selected appointment.
	a. 

### Challenges

1. Handling Video calling via notification when the application is in killed state and active state for both android and ios


### UI prompt:

```text
I want to create a mobile app for patients, for them to be able to book appointment with doctors , and attend them via video calling.
Here doctor is the only person who will be able to start / end the call, the pateint will be able to attend the call via call alert notification, and on click on answer button it will open the application and which take the patient to calling screen with the options like change camera, closed / open camera, closed / open mic, and after the call is ended, they will be navigated to rating and reviewing screen.
Here Select specialities screen is the home screen of the app.
To book a doctor first they will select the select the specialities of the doctor, then they will see a list of doctor with the specialities they selected, they filter this list using parameters like ratings, price range, or language spoken, then after selecting their doctor they will select the type of appointment, Initial, or follow up, after selecting the type they will see the Slot Selecting screen, where they will see a date picker that when selecting the day will load the slots available for that day,after selecting the slot they will see the payment screen, where the amount will be mentioned with the taxes included, and also a promo code input field for discounts, for making payment they will select the payment method, like card payment, or plaatforms like google pay or apple pay etc. what ever is available in stripe. after completing the payment they will see a appointment confirmed screen.
Now they will be able to see their appointment in upcoming appointment section of appointments screen, here they will be able to see the list of upcoming appointment with the details of the appointment like doctor, speciality, their date and time of the appointment, fee charged, duration, type etc.There will be a cancel button on each appointment on which they will see a screen where their will be the suggestions for the reason of cancellation then on confirming the reason they will be back to the appointments screen where they can the appointment list is updated. In past appointment section they will see the list of past appointments with their status like completed, not attended, doctor didn't come, cancelled, the date and time of the appointment, with type of it. Their will a be two buttons on each appointment, one is book again which will navigate them to appointment type screen with that doctor's details, and another one will be view medical recorde, which will navigate them to medical records screen. In medical records screen patient will see the list of medical records, each having a button View Prescription, on clicking it will navigate to view prescription screen.
```

```
Their will also be a profile screen, which will show the profile image, name and email address, then will show the options like edit profile, change password, transactions, fhir epic, logout account and delete options
```

```
	On clicking on edit profile screen, it will navigate to a screen where patient can edit their details first name, last name, email address, phone number, date of birth, gender, and the profile image,

	On clicking on change password, it will navigate to a screen where patient can change their password by entering their current password, new password and confirm password fields.

```

```
In Transactions screen their will be 2 tabs one where the list payments done by patient will be shown, in another one the list of refund requests will be shown with their status(refunded or canceled, in progress).

```

```
On click on FHIR Epic it will check whether the patient has already connected the app with FHIR Epic or not if not then it navigate the patient to FHIR EPIC login screen, else it shows a model with a message Already connected.

```