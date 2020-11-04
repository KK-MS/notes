

## using vcpkg

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
..


```
