# test-phone-module

this is a test

## Installation

```sh

npm install test-phone-module

```

## Setup

#### Android

- In the AndroidManifest.xml file of your android studio project add:
  ```
    <uses-permission android:name="android.permission.CALL_PHONE" />
  ```
- In the settings.gradle
  ```
    include ':react-native-immediate-phone-call', ':app'
    project(':react-native-immediate-phone-call').projectDir = new 			File(rootProject.projectDir, '../node_modules/react-native-immediate-phone-call/android')
  ```
- In the app/build.gradle
  ```
   implementation project(':react-native-immediate-phone-call')
  ```
- In MainApplication.java
  ```js
    import com.github.wumke.RNImmediatePhoneCall.RNImmediatePhoneCallPackage;
    ...
    @Override
    protected List<ReactPackage> getPackages() {
      return Arrays.<ReactPackage>asList(
        ...
        new RNImmediatePhoneCallPackage(),
        ...
      );
    }
    ...
  ```
- MainActivity.java
  ```js
    import com.github.wumke.RNImmediatePhoneCall.RNImmediatePhoneCallPackage;  // <--- import
    ...
    public class MainActivity extends ReactActivity {
      ...
      @Override
      public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {
          RNImmediatePhoneCallPackage.onRequestPermissionsResult(requestCode, permissions, grantResults); // very important event callback
          super.onRequestPermissionsResult(requestCode, permissions, grantResults);
      }
      ...
    }
  ```

## Usage

```js

import RNImmediatePhoneCall from 'react-native-immediate-phone-call';

...

RNImmediatePhoneCall.immediatePhoneCall('0123456789');

...

```

## Contributing

See the [contributing guide](CONTRIBUTING.md) to learn how to contribute to the repository and the development workflow.

## License

MIT
