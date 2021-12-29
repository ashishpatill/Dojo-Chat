# Dojo-Chat
 
## Setup

### A. Xcode

1. Create Project
2. Copy the bundle identifier (com.yourName.projectName)
3. Add Firebase-ios-sdk package using Swift package manager (SPM) (https://github.com/firebase/firebase-ios-sdk)
4. In AppDelegate class do the following:
   - Import Firebase
   - In *didFinishLaunchingWithOptions* method add *FirebaseApp.configure()* before return
5. Create a DatabaseManager class to add all database fetch and update functions
6. *import FirebaseDatabase* in Database Manager class
7. To read from database use:

   ~~~swift
   ref.child("users").observeSingleEvent(of: .value)
   ~~~
8. To create new value use:
	
	~~~swift
	// if database is empty
   	ref.child("users").setValue(allUserDict)
	~~~

9. To update values in database use:

	~~~swift
	//4. if database already contains users
   	ref.child("users").updateChildValues([userID:user1])
	~~~
   

### B. Firebase Console

1. Create a new project
2. Choose location for server nearest to your country
3. Create iOS project
4. Turn on Authentication, Realtime database, Storage
5. Make sure under rules for Realtime database, read and write permissions are set to true
6. Download the *GoogleService-Info.plist* file from settings and add to your xcode project

### C. Helpful links
1. [How to add Firebase to your app](https://firebase.google.com/docs/ios/setup)
2. [Installation and setup for iOS](https://firebase.google.com/docs/database/ios/start)
3. [How to structure your data](https://firebase.google.com/docs/database/ios/structure-data)
4. [How to fetch and save data with firebase](https://firebase.google.com/docs/database/ios/read-and-write)
5. [Choosing location for firebase](https://firebase.google.com/docs/firestore/locations)
