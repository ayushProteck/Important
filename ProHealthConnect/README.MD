# ProHealthConnect

## Mobile App

**Description -** 

This is for the users who are the patient of the hospitals, where patient and all the staff members are connected with one epic ID for managing their data in that hospital

### Modules

#### A. Authentication:

1. **Login -** Patients can login through email & password

2. **SignUp -** Patients can create their account using Name*, Email ID*, Phone number*, Date of Birth*, Gender*, Government ID(Optional), Password*, Confirm Password*

3. **Forgot Password-** // Need to be Discussed

4. **Epic Login -** Patient can also log in to their epic account their epic account username and password. This will be optional for users to connect as they can login later.


#### B. Book Appointment:

1. **Doctor Section -** Patient can select the Doctors as shown in the list or carousel, and can filter the details of them by their speciality, Ratings, Price Range and spoken Language,

Here doctors will be shown with their profile containing details like: Profile Image, Name, Ratings with number of reviews, experience in years, Consultation Fee per session, and their field of speciality.

2. **Selecting the type of consultation -** Consultation can be of two types 1. Initial Consultation, 2. Follow up Consultation
	
	a. Initial Consultation - The time of consultation is of 60 minutes and the purpose of this is for when patient is having their first consultation with the patient for their treatment and since the time is more the doctors can charge more for it.

	b. Follow Up Consultation - The time of consultation is 30 minutes and the purpose of this is that it the consultation doctor to have a regular check with their patients that they taking their medication properly and the way their health is goingand since the time is only half an less the charge will be less as well.

3. **Slot Selection -** Here patient will be shown the available slots of the doctor accordingly to the consultation type they have selected. First they will select the day and then the slots for that day shown to them, from which they can select the time most favorable to them.

4. **Payment -** Here user will show the payment options using stripe, like pay using card details, or via google pay etc(what ever is available in stripe).

#### C. Call Enagagment:

1. **Upcomming Appointments -** Here patient can see their appointments and start their consultation. On click on Start button, patient will see a check permissions screen, where we will check whether the permissions are their for the consultation or not, if not then patient will not be allowed to go to the video calling screen.

2. **Call Handled via Notification -** Here When the doctor will call as he/she will have the power to start the call, the patient will get the call notification alert in their mobile phone which will open up the application this is where patient can attend their call.

3. **Video Calling -** Here Patient will connect with the doctor using opentok sdk, and will be able to attend to their consultation, also here doctor is only permissable to end call.

4. **Rating -** Here Patient can rate their consultation experience and add a review as well.

#### D. Profile:

1. **Edit Profile -** Here patient can see and edit their profile details.

2. **Change Password -** Here patient can change their password using their current password, then new password and lastly confirm password.

3. **Epic Account -** Here patient can check their status of their connection of the application account with epic account. On click , if user is not connected to the epic account, will be navigated to the Epic Login(as mentioned in Authentication Module).

#### E. Medical History:

1. **Medical History -** Here paitent can see their appointment history, where patient can see their past appointments with the doctors review, medical report, prescription, and doctor's note for them


#### F. Transactions:

1. **Transactions -** Here patient see all the transactions they have made.