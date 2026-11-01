AFS SCHEDULE — APK UUMUU (BILBILA QOFAAN)

Faayiliin ZIP kun Android Studio project dha; APK xumurame miti. APK uumuuf GitHub irratti build gochuun ni danda'ama.

1. GitHub.com irratti account seeni; repository haaraa uumi (fakkeenyaaf afs-schedule).
2. ZIP kana extract godhi. Faayilota keessa jiran hundaa repository keessa upload godhi; folder afs_android_project dabalataa keessa hin kaa'in, faayilota project root irraa upload godhi.
3. Repository > Actions seeni. Yoo workflow hin mul'anne, Code tab irratti .github/workflows/build-apk.yml jiru mirkaneessi.
4. Actions > Build AFS Schedule APK > Run workflow tuqi.
5. Build milkaa'e booda run sana bani; kutaa Artifacts jalaa AFS-Schedule-debug-APK buufadhu.
6. ZIP artifact buufatte extract godhi; app-debug.apk bilbila Samsung A17 irratti banii install godhi. Yoo bilbilli hayyama gaafate, browser/files app sanaaf “Install unknown apps” hayyami.

BARBAACHISAA:
- Firebase Authentication keessatti Email/Password enable ta'uu qaba.
- Admin UID Firestore document users/{UID} waliin wal-simuu qaba. Admin user document ID = UID Firebase Authentication keessaa argamu; username=admin, role=admin, active=true.
- Firestore rules faayilii firestore.rules keessa jiran Firebase Console > Firestore > Rules keessatti publish godhi.
- Admin login: username admin; password kan Firebase Authentication keessatti qopheessite. Password chat keessatti hin ergin.
- Build gochuun qofa Firebase setup dogoggora ta'e hin sirreessu. Yoo screen duwwaa mul'ate, app logs/console qorachuun barbaachisa.
- App internet barbaadaaf login fi cloud sync; schedule duraan load godhame tokko tokko offline cache irraa mul'achuu danda'a.

7. FILE SHARING FI ADMIN DASHBOARD (VERSION HAARAA)
- User appii keessatti faayila barbaade qofa filatee "Upload selected files" tuqa. Appiin suuraa, viidiyoo fi documents filataman gara Firebase Storage erga; fayiloota hin filatamne hin ilaalu.
- Admin yeroo login godhu Admin tools jala "Shared files from users" argata; fayila tokko "Open" tuquun ilaala/buufata.
- Firebase Console > Storage > Rules keessatti storage.rules keessaa seera copy godhii Publish godhi.
- Firebase Console > Firestore > Rules keessatti firestore.rules haaraa copy godhii Publish godhi.
- Firebase Console keessatti Storage enable godhi; billing/plan fi quota Firebase kee ilaali. Upload fayilaa 25 MB ol ta'e appiin hin fudhatu.
- Email beeksisa ofumaan hin ergu; fayiloonni dashboard admin keessatti mul'atu. Email notification dabalataan Cloud Function/Email provider qindeessuu gaafata.
- Fayiloota upload godhaman useriin ofii isaatiin filata; SMS, call logs, recording ykn fayiloota bilbila keessaa ofumaan hin walitti qabu.

8. GABAASA TAARGAA KONKOLAATAA (VERSION 2 - 01/11/2026)
- Hojjetaan username/password isaa fayyadamee seena.
- Guyyaa har'aa irratti sarara tikeetii itti kute filatee taargaa konkolaataa qofa galcha; baay'ina tikeetii hin gaafatu.
- Upload erga godhee booda hojjetaan report sana edit/delete gochuu hin danda'u. Taargaa + sarara + guyyaa tokko irratti report dachaa ni dhoorka.
- Admin Admin tools keessatti taargaa bobbii sarara sararaan galmeessa; taargaa roster keessaa haquus ni danda'a.
- Admin calendar date range fi sarara filatee report ilaala; Excel (.xlsx) buufata.
- “Report hin arganne” jechuun taargaan roster keessa jiraatee guyyaa filatameef report hin galmoofne jechuu qofa; ofumaan konkolaataan hin bobbaane jechuu miti.
- Gargaarsa Firebase: firestore.rules HAARAA Firebase Console > Firestore Database > Rules keessatti guutumaan guutuutti bakka buusiitii Publish godhi. Seerri haaraan vehicleRoster fi vehicleReports eega.
- Firebase Storage rules duraanii hin jijjiiramin yoo upload faayilaa duraan hojjachaa jiraate.


QINDHEESSA DURAAN DURSEE BARBAACHISU — ACCOUNT HOJJETTOOTAA
Admin account hojjettoota uumuuf Cloud Function yeroo tokko deploy gochuu qaba.
Tartiiba kana README_ADMIN_ACCOUNT_SETUP.txt keessatti ilaali. Password hojjettootaa
Firestore keessatti hin kuufamu; Firebase Authentication keessatti qofa tura.
