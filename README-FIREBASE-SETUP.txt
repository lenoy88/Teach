BRIGHTPATH HOSTED ADMIN SETUP

These files keep the student pages on your GitHub Pages site. Firebase provides the shared sign-in and saves the Overview greeting, intro, announcement, and meeting details so changes appear for other visitors. The static demo roster and quiz progress are not yet real shared student records.

1. Create a Firebase project at https://console.firebase.google.com/ .
2. In Project settings, add a Web app. Copy its config into firebase-config.js, replacing each PASTE_ value. This web config is used by browser apps; the database rules below control write access. Never put a service-account key or private server credential in website files.
3. In Authentication, enable Email/Password. Create the teacher user from the Firebase Console; do not enable public account creation. Replace REPLACE_WITH_TEACHER_EMAIL in firebase-config.js and firestore.rules with that same teacher email.
4. Create a Cloud Firestore database. Open Firestore > Rules, paste the contents of firestore.rules after replacing the email, and Publish. The rules allow visitors to read the public portal text, but only the exact teacher email to edit it. All other database paths are denied.
5. In Authentication > Settings > Authorized domains, add lenoy88.github.io if it is not already listed.
6. Upload all six HTML pages, firebase-config.js, and firestore.rules to the root of the Teach GitHub repository. Commit the upload.
7. Open https://lenoy88.github.io/Teach/admin.html, sign in with the teacher account, and update Overview or Portal settings.

If the teacher's Firebase account email changes, update both the config file and Firestore rule to match. Do not put student private information in the public portal/main document.
