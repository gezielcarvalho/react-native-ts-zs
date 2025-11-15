This is a new [**React Native**](https://reactnative.dev) project, bootstrapped using [`@react-native-community/cli`](https://github.com/react-native-community/cli).

# Getting Started

>**Note**: Make sure you have completed the [React Native - Environment Setup](https://reactnative.dev/docs/environment-setup) instructions till "Creating a new application" step, before proceeding.

## First Time Setup (After Cloning)

### Prerequisites

- **Node.js** (v14 or newer)
- **npm** or **Yarn**
- **Java JDK 17** (for Android development)
- **Android Studio** (for Android development)
- **Xcode** (for iOS development - macOS only)

### Installation Steps

1. **Install dependencies:**
   ```bash
   npm install
   # OR
   yarn install
   ```

2. **For Android Development (macOS):**
   
   a. **Install Homebrew** (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
   
   b. **Install Java JDK 17**:
   ```bash
   brew install --cask zulu@17
   ```
   
   c. **Add environment variables** to your `~/.zshrc`:
   ```bash
   # Java for React Native
   export JAVA_HOME=$(/usr/libexec/java_home -v 17)
   export PATH=$PATH:$JAVA_HOME/bin
   
   # Android SDK for React Native
   export ANDROID_HOME=$HOME/Library/Android/sdk
   export PATH=$PATH:$ANDROID_HOME/emulator
   export PATH=$PATH:$ANDROID_HOME/platform-tools
   export PATH=$PATH:$ANDROID_HOME/tools
   export PATH=$PATH:$ANDROID_HOME/tools/bin
   ```
   
   d. **Reload your shell**:
   ```bash
   source ~/.zshrc
   ```
   
   e. **Make gradlew executable**:
   ```bash
   chmod +x android/gradlew
   ```

3. **For iOS Development (macOS only):**
   ```bash
   cd ios
   pod install
   cd ..
   ```

4. **Create an Android Virtual Device:**
   - Open Android Studio
   - Go to **Tools > Device Manager**
   - Create a new virtual device if you don't have one

For detailed troubleshooting, see [docs/ANDROID_TROUBLESHOOTING.md](docs/ANDROID_TROUBLESHOOTING.md).

## Step 1: Start the Metro Server

First, you will need to start **Metro**, the JavaScript _bundler_ that ships _with_ React Native.

To start Metro, run the following command from the _root_ of your React Native project:

```bash
# using npm
npm start

# OR using Yarn
yarn start
```

## Step 2: Start your Application

Let Metro Bundler run in its _own_ terminal. Open a _new_ terminal from the _root_ of your React Native project. Run the following command to start your _Android_ or _iOS_ app:

### For Android

```bash
# using npm
npm run android

# OR using Yarn
yarn android
```

### For iOS

```bash
# using npm
npm run ios

# OR using Yarn
yarn ios
```

If everything is set up _correctly_, you should see your new app running in your _Android Emulator_ or _iOS Simulator_ shortly provided you have set up your emulator/simulator correctly.

This is one way to run your app — you can also run it directly from within Android Studio and Xcode respectively.

## Step 3: Modifying your App

Now that you have successfully run the app, let's modify it.

1. Open `App.tsx` in your text editor of choice and edit some lines.
2. For **Android**: Press the <kbd>R</kbd> key twice or select **"Reload"** from the **Developer Menu** (<kbd>Ctrl</kbd> + <kbd>M</kbd> (on Window and Linux) or <kbd>Cmd ⌘</kbd> + <kbd>M</kbd> (on macOS)) to see your changes!

   For **iOS**: Hit <kbd>Cmd ⌘</kbd> + <kbd>R</kbd> in your iOS Simulator to reload the app and see your changes!

## Congratulations! :tada:

You've successfully run and modified your React Native App. :partying_face:

### Now what?

- If you want to add this new React Native code to an existing application, check out the [Integration guide](https://reactnative.dev/docs/integration-with-existing-apps).
- If you're curious to learn more about React Native, check out the [Introduction to React Native](https://reactnative.dev/docs/getting-started).

# Troubleshooting

If you can't get this to work, see the following resources:

- **Android Issues:** [docs/ANDROID_TROUBLESHOOTING.md](docs/ANDROID_TROUBLESHOOTING.md)
- **General Issues:** [React Native Troubleshooting](https://reactnative.dev/docs/troubleshooting)

# Learn More

To learn more about React Native, take a look at the following resources:

- [React Native Website](https://reactnative.dev) - learn more about React Native.
- [Getting Started](https://reactnative.dev/docs/environment-setup) - an **overview** of React Native and how setup your environment.
- [Learn the Basics](https://reactnative.dev/docs/getting-started) - a **guided tour** of the React Native **basics**.
- [Blog](https://reactnative.dev/blog) - read the latest official React Native **Blog** posts.
- [`@facebook/react-native`](https://github.com/facebook/react-native) - the Open Source; GitHub **repository** for React Native.
