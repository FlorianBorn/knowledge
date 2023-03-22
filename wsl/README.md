## installierte WSLs anzeigen
wsl --list --all

## neues WSL von einem bestehenden WSL installieren
wsl --import (distribution) (install location) (file location and filename)  

(1) Ordner erstellen "ubuntu_cloud_guru"
--> in C:\Users\dummy\Desktop\wsl\

(2) WSL distro erstellen
wsl --import ubuntu_cloud_guru C:\Users\dummy\Desktop\wsl\ubuntu_cloud_guru C:\Users\dummy\Desktop\wsl\ubuntu_for_R.backup
