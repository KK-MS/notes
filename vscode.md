| [Shortcut](#shortcut)| [Variable reference](#variable-reference) | [CPP](#cpp) | [nodejs](#nodejs) | [vcpkg](#vcpkg) |

## Shortcut
* https://superuser.com/questions/1569067/how-to-close-explorer-via-shortcut-in-vs-code
  * ctrl+B (set key for `View: Close Primary Side Bar`, remove shortcut key from VIM )

## Variable reference

https://code.visualstudio.com/docs/editor/variables-reference

**Predefined variables:**

Most used variables are:

* ${workspaceFolder} - _the path of the folder opened in VS Code_
* ${file} - _the current opened file_
* ${fileDirname} - _the current opened file's dirname_
* ${cwd} - _the task runner's current working directory on startup_


**Environment variables**

* ${env:Name} - _Access reference environment variables through the_ ${env:Name} _syntax._
for example, ${env:USERNAME}).

Example:

```console
{
  "type": "node",
  "request": "launch",
  "name": "Launch Program",
  "program": "${workspaceFolder}/app.js",
  "cwd": "${workspaceFolder}",
  "args": ["${env:USERNAME}"]
}
```
## CPP

https://code.visualstudio.com/docs/cpp/config-msvc

|# | .vscode folder file | description| external link |
|---|---|---|---|
|1| [tasks.json](#tasks-json) |build instructions | |
|2| [launch.json](#lanuch-json) |debugger settings | [debugging](https://code.visualstudio.com/docs/editor/debugging#_launchjson-attributes)|
|3| [c_cpp_properties.json](#c_cpp_properties-json) | compiler path and IntelliSense settings| [c_cpp](https://code.visualstudio.com/docs/cpp/config-msvc#_cc-configurations)|

### tasks json

### launch json

### C_CPP_Properties json


https://code.visualstudio.com/docs/editor/debugging#_launchjson-attributes


## nodejs

### node-snippets, chris-noring.node-snippets

The following commands are available:

node-express, creates an express server

node-express-get, creates GET route

node-express-get-params, creates a GET route and shows how to access parameters

node-express-post, creates a POST route

node-express-post-params, creates a POST route and shows how to access the body

node-http-server, creates a simple HTTP server

node-file-read-sync, reads a file synchronously

node-file-read-async, reads a file asynchronously, with a callback

node-event-emitter, creates an event emitter, emit events and shows to subscribe to said event

node-promise-create, creates a Promise

node-supertest-init, adds the initial imports for supertest and the app you are about to test. I assume the app you are about to test looks something like this:
```js
//  app.js
const express = require('express')
const app = express();
// your route definitions
module.exports = app;
```
and that your file structure looks like this:

```
-| app.js    // this is where the web app goes
-| __tests__/
---| app.js  // this where the tests goes
node-supertest-beforeall, configures supertest to use the app instance, this is a needed step to initialize supertest
```

.... more ...


## vcpkg

Ref: https://www.eximiaco.tech/en/2019/07/27/hello-opencv-with-c-using-visual-studio-2017-and-vcpkg/
```console
c:\ins\vcpkg>vcpkg.exe integrate install
Applied user-wide integration for this vcpkg root.

All MSBuild C++ projects can now #include any installed libraries.
Linking will be handled automatically.
Installing new libraries will make them instantly available.

CMake projects should use: "-DCMAKE_TOOLCHAIN_FILE=C:/ins/vcpkg/scripts/buildsystems/vcpkg.cmake"

c:\ins\vcpkg>
```

## VCPKF install opencv using

```

c:\ins\vcpkg>vcpkg.exe install opencv
Your feedback is important to improve Vcpkg! Please take 3 minutes to complete our survey by running: vcpkg contact --survey
Computing installation plan...
The following packages will be built and installed:
  * libjpeg-turbo[core]:x86-windows
  * liblzma[core]:x86-windows
  * libpng[core]:x86-windows
  * libwebp[core,nearlossless,simd,unicode]:x86-windows
    opencv[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows
  * opencv4[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows
  * opengl[core]:x86-windows
  * protobuf[core]:x86-windows
  * tiff[core]:x86-windows
  * zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
Detecting compiler hash for triplet x86-windows...
A suitable version of git was not found (required v2.26.2). Downloading portable git v2.26.2...
Downloading git...
  https://github.com/git-for-windows/git/releases/download/v2.26.2.windows.1/PortableGit-2.26.2-32-bit.7z.exe -> C:\ins\vcpkg\downloads\PortableGit-2.26.2-32-bit.7z.exe
Extracting git...
A suitable version of 7zip was not found (required v18.1.0). Downloading portable 7zip v18.1.0...
Downloading 7zip...
  https://www.nuget.org/api/v2/package/7-Zip.CommandLine/18.1.0 -> C:\ins\vcpkg\downloads\7-zip.commandline.18.1.0.nupkg
Extracting 7zip...
A suitable version of nuget was not found (required v5.5.1). Downloading portable nuget v5.5.1...
Downloading nuget...
  https://dist.nuget.org/win-x86-commandline/v5.5.1/nuget.exe -> C:\ins\vcpkg\downloads\22ea847d-nuget.exe
A suitable version of powershell-core was not found (required v7.0.3). Downloading portable powershell-core v7.0.3...
Downloading powershell-core...
  https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/PowerShell-7.0.3-win-x86.zip -> C:\ins\vcpkg\downloads\PowerShell-7.0.3-win-x86.zip
Extracting powershell-core...
Starting package 1/10: libjpeg-turbo:x86-windows
Building package libjpeg-turbo[core]:x86-windows...
Could not locate cached archive: C:\Users\k.mayannavar\AppData\Local\vcpkg\archives\bb\bbce3f561040ce15c0fc41a0b4f557f6062a7464.zip
-- Downloading https://github.com/libjpeg-turbo/libjpeg-turbo/archive/ae87a958613b69628b92088b313ded0d4f59a716.tar.gz...
-- Extracting source C:/ins/vcpkg/downloads/libjpeg-turbo-libjpeg-turbo-ae87a958613b69628b92088b313ded0d4f59a716.tar.gz
-- Applying patch add-options-for-exes-docs-headers.patch
-- Applying patch workaround_cmake_system_processor.patch
-- Using source at C:/ins/vcpkg/buildtrees/libjpeg-turbo/src/0d4f59a716-5f2e7bc00b.clean
-- Downloading https://www.nasm.us/pub/nasm/releasebuilds/2.14.02/win32/nasm-2.14.02-win32.zip...
-- Configuring x86-windows
-- Building x86-windows-dbg
-- Building x86-windows-rel
... snip
-- Building x86-windows-dbg
-- Building x86-windows-rel
-- Installing: C:/ins/vcpkg/packages/opencv4_x86-windows/share/opencv4/copyright
-- Performing post-build validation
-- Performing post-build validation done
Stored binary cache: C:\Users\k.mayannavar\AppData\Local\vcpkg\archives\d3\d30f5460ac15fe1f3eaa6b8bd4c6e050cbbfb25b.zip
Building package opencv4[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows... done
Installing package opencv4[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows...
Installing package opencv4[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows... done
Elapsed time for package opencv4:x86-windows: 10.23 min
Starting package 10/10: opencv:x86-windows
Building package opencv[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows...
Could not locate cached archive: C:\Users\k.mayannavar\AppData\Local\vcpkg\archives\5a\5a7fed0d096e1dce0470546a5095007b8ba9dbb6.zip
-- Performing post-build validation
-- Performing post-build validation done
Stored binary cache: C:\Users\k.mayannavar\AppData\Local\vcpkg\archives\5a\5a7fed0d096e1dce0470546a5095007b8ba9dbb6.zip
Building package opencv[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows... done
Installing package opencv[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows...
Installing package opencv[core,dnn,jpeg,opengl,png,tiff,webp]:x86-windows... done
Elapsed time for package opencv:x86-windows: 1.929 s

Total elapsed time: 16.74 min


c:\ins\vcpkg>
c:\ins\vcpkg>

```
