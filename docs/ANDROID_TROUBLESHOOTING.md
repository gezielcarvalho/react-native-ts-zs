# Android Troubleshooting Guide

This guide covers common Android setup issues and their solutions for React Native development on macOS.

## Common Issues

### Issue 1: `adb: command not found`

**Problem:** The Android Debug Bridge (adb) is not in your system PATH.

**Solution:** Add Android SDK to your PATH by adding the following to your `~/.zshrc`:

```bash
# Android SDK for React Native
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
```

After adding these lines, either restart your terminal or run:
```bash
source ~/.zshrc
```

### Issue 2: `Failed to launch emulator. Reason: No emulators found`

**Problem:** React Native cannot find any Android Virtual Devices (AVDs).

**Solution:** 

1. Open Android Studio
2. Go to **Tools > Device Manager** (or **AVD Manager**)
3. Create a new virtual device if none exist
4. Verify emulators are available by running:
   ```bash
   emulator -list-avds
   ```

### Issue 3: `Command failed with EACCES: ./gradlew tasks`

**Problem:** The Gradle wrapper script doesn't have execute permissions.

**Solution:** Make the gradlew script executable:

```bash
chmod +x android/gradlew
```

### Issue 4: ANDROID_HOME not set

**Problem:** The ANDROID_HOME environment variable is not configured.

**Solution:** Add the following to your `~/.zshrc`:

```bash
export ANDROID_HOME=$HOME/Library/Android/sdk
```

Then reload your shell configuration:
```bash
source ~/.zshrc
```

### Issue 5: Unable to locate a Java Runtime

**Problem:** Java JDK is not installed or JAVA_HOME is not configured.

**Solution:** 

1. **Install Homebrew** (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Add Homebrew to PATH**:
   ```bash
   echo 'eval "$(/usr/local/bin/brew shellenv)"' >> ~/.zprofile
   eval "$(/usr/local/bin/brew shellenv)"
   ```

3. **Install Java JDK 17** (recommended for React Native):
   ```bash
   brew install --cask zulu@17
   ```

4. **Configure JAVA_HOME** by adding to your `~/.zshrc`:
   ```bash
   export JAVA_HOME=$(/usr/libexec/java_home -v 17)
   export PATH=$PATH:$JAVA_HOME/bin
   ```

5. **Reload your shell**:
   ```bash
   source ~/.zshrc
   ```

## Verification Steps

After applying the fixes above, verify your setup:

1. **Check ANDROID_HOME:**
   ```bash
   echo $ANDROID_HOME
   # Should output: /Users/yourusername/Library/Android/sdk
   ```

2. **Check JAVA_HOME:**
   ```bash
   echo $JAVA_HOME
   # Should output: /Library/Java/JavaVirtualMachines/zulu-17.jdk/Contents/Home
   ```

3. **Check Java version:**
   ```bash
   java -version
   # Should show OpenJDK version 17.x.x
   ```

4. **Check adb:**
   ```bash
   which adb
   # Should output: /Users/yourusername/Library/Android/sdk/platform-tools/adb
   ```

5. **Check emulator:**
   ```bash
   which emulator
   # Should output: /Users/yourusername/Library/Android/sdk/emulator/emulator
   ```

6. **List available emulators:**
   ```bash
   emulator -list-avds
   # Should list your available Android Virtual Devices
   ```

## Running the App

Once everything is configured:

**Option 1: Let React Native start the emulator automatically**
```bash
npm run android
```

**Option 2: Start emulator manually first**
```bash
# Start the emulator in the background
emulator -avd <YOUR_AVD_NAME> &

# Then run the app
npm run android
```

## Additional Resources

- [React Native Environment Setup](https://reactnative.dev/docs/environment-setup)
- [Android Studio Documentation](https://developer.android.com/studio)
- [React Native Doctor](https://github.com/react-native-community/cli/blob/main/packages/cli-doctor/README.md)
