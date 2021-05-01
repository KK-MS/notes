*
##

MAC on the virutalbox:

https://github.com/bigboy32/MacOnVirtuablox-TheEasyWay

## Bloc Library: Basics & Beyond - Felix Angelov | Flutter Europe
By BloC author: Speaker: Felix Angelov (https://twitter.com/felangelov​)

https://www.youtube.com/watch?v=knMvKPKBzGE

### Cubit and BLOC

https://www.youtube.com/watch?v=nc55gOsL8lc

By BloC author: Speaker: Felix Angelov

## Online dartpad

https://dartpad.dev/deb03027f153fd9e849c45267e8868b9?

Code online and try PoC.

## Drawing

### CustomPainter

https://blog.codemagic.io/flutter-custom-painter/

We can draw, and with it we can animate

### Canvas with multi touch

https://blog.codemagic.io/multi-touch-canvas-with-flutter/


## Functionality

### Upload a file:
* https://rodolfohernan20.blogspot.com/2019/12/upload-files-to-server-with-flutter-web.html
* https://blogs.ashrithgn.com/a-simple-way-to-upload-a-file-to-server-from-flutter-web-app/


## Widget
### Picker of Number, date, time, range, etc.

https://pub.dev/packages/flutter_picker


### Multiselect dropdown

https://gitlab.com/desiprogrammer/flutter_dropdown


## Integrating C library in a Flutter app using Dart FFI

https://medium.com/flutter-community/integrating-c-library-in-a-flutter-app-using-dart-ffi-38a15e16bc14

## Erros

* What went wrong:
Execution failed for task ':app:lintVitalRelease'.
> Could not resolve all artifacts for configuration ':app:debugRuntimeClasspath'.
   > Failed to transform libs.jar to match attributes {artifactType=processed-jar, org.gradle.libraryelements=jar, org.gradle.usage=java-runtime}.
      > Execution failed for JetifyTransform: C:\prj\flutterapp\sx03\EvalApp\build\app\intermediates\flutter\debug\libs.jar.
         > Transform's input file does not exist: C:\prj\flutterapp\sx03\EvalApp\build\app\intermediates\flutter\debug\libs.jar. 

## Error: SDK location not found.
```
Running Gradle task 'assembleAarRelease'... Done                   30.9s


FAILURE: Build failed with an exception.

* What went wrong:
A problem occurred configuring root project 'permission'.
> SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

```
Fix:

if your error says debug/libs.jar, build --debug then --release:

flutter build apk --debug
flutter build apk --release
If your error says profile/libs.jar, build --profile then --release:

flutter build apk --profile
flutter build apk --release

Link: https://stackoverflow.com/questions/62548438/execution-failed-for-task-applintvitalrelease-flutter

## Creating

Ref: https://stackoverflow.com/questions/49047411/flutter-how-to-create-a-new-project

I think a better way is to create Flutter project by command line

flutter create --org com.yourdomain your_app_name
Swift, Kotlin, and androidx dependencies are the default options

After just open the created project in Android Studio or in VSCode

Parameter

--org com.yourcompany
will form applicationId for Android:

com.yourcompany.yourappname
and iOS PRODUCT_BUNDLE_IDENTIFIER:

com.yourcompany.yourAppName
To explore all possible parameters type

flutter create --help
Share
Edit
Follow
edited Apr 12 '20 at 23:30
answered Feb 9 '19 at 13:39

Andrew
30.5k1010 gold badges129129 silver badges9999 bronze badges
1
It would be great if you can also post a link to where this full command is documented. Couldn't find it anywhere. – kovac Oct 26 '19 at 7:20
4
@swdon just run in the terminal 'flutter create --help' All options are there – Andrew Oct 26 '19 at 16:31
Add a comment

32

Here is in advance! Without android studio, you can create new project with some arguments (Option Migration androidX, Platform languages).

flutter create --androidx -t app --org com.companyname.packagename -a kotlin -i swift myapp
Explore Yourself by Flutter CLI

flutter create --help

--[no-]pub : Whether to run "flutter pub get" after the project has been created. (defaults to on)

--[no-]offline : When "flutter pub get" is run by the create command, this indicates whether to run it in offline mode or not. In offline mode, it will need to have all dependencies already available in the pub cache to succeed.

--[no-]with-driver-test : Also add a flutter_driver dependency and generate a sample 'flutter drive' test.

-t, --template=≶type> : Specify the type of project to create:

 [app]                (default) Generate a Flutter application.
 [package]            Generate a shareable Flutter project containing modular Dart code.
 [plugin]             Generate a shareable Flutter project containing an API in Dart code with a platform-specific
                       implementation for Android, for iOS code, or for both.
-s, --sample=≶id> : Specifies the Flutter code sample to use as the main.dart for an application. Implies --template=app. The value should be the sample ID of the desired sample from the API documentation website (http://docs.flutter.dev). An example can be found at https://master-api.flutter.dev/flutter/widgets/SingleChildScrollView-class.html

--list-samples=≶path> : Specifies a JSON output file for a listing of Flutter code samples that can created with --sample.

--[no-]overwrite : When performing operations, overwrite existing files.

--description The description to use for your new Flutter project. This string ends up in the pubspec.yaml file. (defaults to "A new Flutter project.")

--org : The organization responsible for your new Flutter project, in reverse domain name notation. This string is used in Java package names and as prefix in the iOS bundle identifier. (defaults to "com.example")

--project-name : The project name for this new Flutter project. This must be a valid dart package name.

-i, --ios-language : [objc, swift (default)]
-a, --android-language : [java, kotlin (default)]
--[no-]androidx : Generate a project using the AndroidX support libraries
