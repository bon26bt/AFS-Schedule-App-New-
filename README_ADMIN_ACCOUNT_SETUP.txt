AFS SCHEDULE — ADMIN ACCOUNT CREATION UPDATE

This update changes staff-account creation to a secure Firebase callable Cloud Function.
The Admin's signed-in session is not replaced when a staff account is created. The
function checks the caller's Firestore users/{uid} profile and requires role='admin'
and active=true. Passwords are sent directly to Firebase Authentication and are not
written to Firestore.

ONE-TIME CLOUD FUNCTION DEPLOYMENT
1. Open Google Cloud Shell in a browser signed in to the Google account that owns the
   Firebase project (project ID: afs-schedule).
2. Upload this project folder/ZIP to Cloud Shell and extract it.
3. Run:
     npm install --prefix functions
     npx firebase-tools login --no-localhost
     npx firebase-tools use afs-schedule
     npx firebase-tools deploy --only functions:adminCreateStaff
4. In Firebase Console, ensure Authentication > Sign-in method > Email/Password is
   enabled, and the Admin account has a users/{uid} Firestore document with:
     username: admin
     role: admin
     active: true
   The document ID must be the Admin Firebase Authentication UID.

ANDROID APK BUILD
The GitHub Actions workflow at .github/workflows/build-apk.yml builds a debug APK
when code is pushed to main or when workflow_dispatch is run. Download app-debug.apk
from the completed workflow's Artifacts section.

SECURITY NOTES
- Only an authenticated, active Firestore Admin can call adminCreateStaff.
- New staff accounts are created with role='user' and active=true.
- Firestore user documents remain writable only by an Admin under firestore.rules.
- Do not share the Admin password or commit service-account keys to GitHub.
- The app requires internet access for Firebase login and live data.
