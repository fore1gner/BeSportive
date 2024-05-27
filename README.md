# BeSportive

BeSportive is an Android application designed to help people become more physically active and increase social cohesion while doing so.

## Important Notice

We have decided not to deploy the app to production, and as a result, the Firebase client is not live either. To run the app, you'll need to use the Android Studio emulator and have the Firebase emulator running in the background. Without following these steps, the app will not function properly, as it won't be connected to the Firebase client and will be unable to store or retrieve data from the database.

This README file provides instructions on how to access the app:

1. [How to start the Firebase emulator](#how-to-start-the-firebase-emulator)
2. [Troubleshooting when getting the error "port already taken"](#troubleshooting-when-getting-the-error-port-already-taken)
3. [Login details](#login-details)
4. [Troubleshooting when the cloud functions are not working](#troubleshooting-when-the-cloud-functions-are-not-working)

## How to start the Firebase emulator

**Requirements:** Node.js v16

1. Install npm and Node.js: [Node.js Download](https://nodejs.org/en/download/)
2. Open a terminal in the root of the project
3. Install Firebase tools: `npm install -g firebase-tools`
4. Login to Firebase: `firebase login`
5. Build the cloud functions:
    ```sh
    cd functions
    npm i
    npm run build
    cd ../
    ```
6. Start the emulator: `firebase emulators:start --import=./firebase_mock`

### Troubleshooting when getting the error "port already taken"

**Method 1:**

1. Open `cmd.exe` in administrator mode
2. Run the command: `netstat -ano | findstr :<PORT>` (Replace `<PORT>` with the port number that is taken, commonly 8080, but keep the colon)
3. Find the PID and copy it
4. Run the command: `taskkill /PID <PID> /F` (Replace `<PID>` with the PID number copied in step 3)

**Method 2:**

**Requirement:** npm@5.2.0 or higher

1. Run: `npx kill-port <PORT>` (Replace `<PORT>` with the port number that is taken, commonly 8080)

### Login details

When the emulator is started, you can log in with the following email and password:
- **Email:** john.do@gmail.com
- **Password:** Test1234

*Note: This user will be an admin that is currently in a group with other users.*

### Troubleshooting when the cloud functions are not working

1. Open the terminal in the root of the project
2. Run the command: `npm ci`

## User Scenario

John is sitting alone at home watching TV with some pizza as he has done frequently for the last 3 months. He feels quite lonely and notices that his energy levels are low. Luckily, John gets a message from Danny, a friend whom he has not spoken to in quite some time. Danny excitedly tells John about an awesome app called BeSportive. Danny says this app has changed his life for the better, making him feel more energetic and more connected with peers.

Just what John needs, he thinks. To his surprise, he had downloaded the app long before the COVID pandemic. Once in the app, he presses the button that says, "Go to login page!". On the sign-in page, John presses the button to sign in with email. He fills in his email: john.do@gmail.com and clicks "Next". Since he already made an account before, he fills in his password "Test1234" and clicks "Sign in".

He sees two options: "Join group" and "Create group". John feels like he should start taking more initiative to be social and presses "Create group". Here he fills in the name "Awesome group" and presses "Create group". Thereafter, he presses "Done". Now John gets redirected to the Configure Challenges page. Here he sees a few default challenges for inspiration. He decides to add the challenge "100 Pushups" by pressing the green plus next to it. He now has one challenge but wants to start with two.

So, he presses "Add custom challenge" and types "run 10 km" in the textbox, changing the difficulty to "Medium" with the menu. Now he presses "Done" and the challenge is added. Content with his final challenges list, he goes to the next page. On the Invite Members page, he sees a generated code. He sends the code to a few friends right away and presses "Done", ending up on the Feed page. John feels content with himself as he has taken action to turn his life around.
