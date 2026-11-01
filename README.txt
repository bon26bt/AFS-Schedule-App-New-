AFS SCHEDULE — ANDROID PROJECT

This is the Android Studio project for wrapping the supplied AFS Schedule web app as an Android app. It uses the Firebase config already supplied in index.html.

IMPORTANT: This package is Android source code, not a compiled APK. This environment does not have Android SDK/build tools installed, so an APK could not be built or tested here.

BUILD APK (Android Studio on a computer):
1. Install Android Studio and a JDK 17.
2. Open this folder (AFS-Schedule project) in Android Studio.
3. Allow Gradle sync and install Android SDK Platform 35 if prompted.
4. Select Build > Build Bundle(s) / APK(s) > Build APK(s).
5. The debug APK will usually be at app/build/outputs/apk/debug/app-debug.apk.
6. Transfer that APK to the Android phone and install it. For a public release, create a signed release build.

FIREBASE CHECKLIST:
- Firebase Authentication > Sign-in method: enable Email/Password.
- Firestore document users/{AUTH_UID} must contain username="admin", role="admin", active=true (boolean). The document ID MUST exactly equal the UID shown for admin@afs-jimma.app in Firebase Authentication.
- Firestore rules must be published. The supplied rules allow signed-in active users to read schedule data and admins to write it.
- Create Firestore database documents afs/schedule and afs/finfine; the app can seed initial values on first admin login if those documents are absent.
- The app uses usernames and appends @afs-jimma.app for Firebase email/password sign-in. Admin username is admin, which maps to admin@afs-jimma.app.
- Do not share passwords in chat. Firebase web API keys are normally public app identifiers; security must come from Authentication and Firestore rules.

SECURITY NOTE:
The current admin user-creation feature uses a secondary Firebase client app. Test it with a non-production account first. For a production app, a trusted server/Cloud Function using Firebase Admin SDK is safer for provisioning users and managing roles. Never allow users to write their own role or active fields.

APP FEATURES PRESENT IN THE INCLUDED HTML:
- AFS Schedule title and schedule view
- Username/password login, no OTP
- User accounts and admin panel
- Schedule and Finfine shift editing
- Firestore sync and local cached copy

NETWORK:
The web app loads Firebase's compat SDK from Google's CDN, so internet access is required for login and cloud synchronization. A cached schedule may be visible offline after it has been loaded once.
