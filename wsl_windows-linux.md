## WSL 
Windows Subsystem for Linux

### WSL1 vs WSL2

WSL2 provides complete kernel and much faster. 
Ref: [MS Comparing WSL 1 and WSL 2](https://docs.microsoft.com/en-us/windows/wsl/compare-versions#:~:text=Whereas%20WSL%201%20used%20a,are%20immediately%20ready%20for%20use.)

I verified and upgrade on WSL.

Note: We need to user ** Windows PowerShell**. This shows importance of *power shell*.

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\Krishnakumar.Mayanna> wsl -l -v
  NAME                   STATE           VERSION
* docker-desktop-data    Stopped         2
  Ubuntu-20.04           Running         1
  docker-desktop         Stopped         2
PS C:\Users\Krishnakumar.Mayanna> wsl --set-version Ubuntu-20.04 2
Conversion in progress, this may take a few minutes...
For information on key differences with WSL 2 please visit https://aka.ms/wsl2
Conversion complete.
PS C:\Users\Krishnakumar.Mayanna> wsl -l -v
  NAME                   STATE           VERSION
* docker-desktop-data    Stopped         2
  Ubuntu-20.04           Stopped         2
  docker-desktop         Stopped         2
PS C:\Users\Krishnakumar.Mayanna>
```
