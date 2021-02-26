*
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

Fix:

if your error says debug/libs.jar, build --debug then --release:

flutter build apk --debug
flutter build apk --release
If your error says profile/libs.jar, build --profile then --release:

flutter build apk --profile
flutter build apk --release

Link: https://stackoverflow.com/questions/62548438/execution-failed-for-task-applintvitalrelease-flutter
