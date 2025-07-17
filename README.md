Wipro Training Tracker
A simple, interactive, and personalized calendar to track your progress throughout the Wipro training program. This tool helps you stay organized by allowing you to mark off completed days, add daily notes, and visualize your entire training timeline from July 14th to August 30th.

✨ Features
Interactive Calendar: Visually track your training period across July and August.

Progress Tracking: Automatically calculates and displays completed and remaining training days.

Mark Completion: Simply click on a day to mark it as complete. A checkmark (✔) will appear.

Daily Notes: Click on any training day to add, edit, or view personal notes for that day. A red dot indicates a day with notes.

Wipro ID Storage: Save your Wipro ID for quick reference.

Motivational Sundays: Sundays are marked as vacation days. Clicking on one reveals a unique, encouraging message for the week ahead.

Cloud Synced: All your data (completed days, notes, and Wipro ID) is saved automatically and securely online using Firebase Firestore. Access your tracker from any device!

Responsive Design: Looks and works great on desktop, tablets, and mobile phones.

🛠️ Setup for Deployment
To deploy this tracker on your own GitHub Pages, follow these steps:

Create a GitHub Repository:

Go to GitHub and create a new public repository. Let's call it wipro-training-tracker.

Add Files to the Repository:

Create a file named index.html and paste the code from the provided index.html file.

Create a file named README.md and paste the content from this file into it.

Commit and push these files to your new repository.

Enable GitHub Pages:

In your repository's main page, go to Settings.

In the left sidebar, click on Pages.

Under the "Build and deployment" section, select the source as Deploy from a branch.

Choose the main (or master) branch and the /(root) folder. Click Save.

Firebase Setup (Crucial Step):

This application requires Firebase to save your data. Go to the Firebase Console.

Create a new project.

Create a new Web App within the project.

Firebase will give you a firebaseConfig object. You must replace the placeholder config in the index.html file with your own.

In the Firebase Console, go to Build > Firestore Database. Create a database in Production mode.

Go to the Rules tab in Firestore and use the following rules to ensure users can only access their own data:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Allow users to read and write only their own data
    match /artifacts/{appId}/users/{userId}/{document=**} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}

Go to Build > Authentication. Enable the Anonymous sign-in method.

Access Your Site:

After a few minutes, your site will be live at https://<your-github-username>.github.io/wipro-training-tracker/.

💻 Tech Stack
HTML5

Tailwind CSS for styling.

JavaScript (ES6 Modules) for application logic.

Firebase Firestore for real-time database and data persistence.

Firebase Authentication for user management.
