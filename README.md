# MyTechDoc

## Initial Git configuration on the local machine and upload first file in to git

```git
~/Documents/SaktiGitRepo
$ git config --global user.email "hisakti@gmail.com"

~/Documents/SaktiGitRepo
$ git config --global user.name "saktikanta"

~/Documents/SaktiGitRepo
$ git init
Initialized empty Git repository in C:/Users/saktikanta.senapati/Documents/SaktiGitRepo/.git/

~/Documents/SaktiGitRepo (master)
$ git clone https://github.com/saktikanta/MyTechDoc.git
Cloning into 'MyTechDoc'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.

~/Documents/SaktiGitRepo (master)
$ cd MyTechDoc/

~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git add git_cmd.docx

~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   git_cmd.docx

g
~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git commit -m "git_cmd.docx uploaded"
[master 85aa2cb] git_cmd.docx uploaded
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 git_cmd.docx

~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git push
Username for 'https://github.com': saktikanta
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 467.98 KiB | 7.09 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/saktikanta/MyTechDoc.git
   0340e52..85aa2cb  master -> master

~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git branch
* master

~/Documents/SaktiGitRepo/MyTechDoc (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```


## Fetch  latest 


```git
~/Desktop/GITHUB_FaceID/FaceID (master)
$ git fetch

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/OnscreenChecker/
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/OnscreenChecker/
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/OnscreenChecker/
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git add FaceID.py Binaries/RemoteDesktopLogin/OnscreenChecker/

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop2.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explorer.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yellow.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximize.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder2.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_active.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_inactive.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.PNG
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows.PNG
        modified:   FaceID.py

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Faces/
        Models/


~/Desktop/GITHUB_FaceID/FaceID (master)
$ git commit -m 'updated faceid and added login assist'
[master e0208f4] updated faceid and added login assist
 16 files changed, 85 insertions(+), 6 deletions(-)
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop2.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explorer.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yellow.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximize.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder2.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_active.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_inactive.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.PNG
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows.PNG

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git push
Username for 'https://github.com': xames3
Counting objects: 22, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (21/21), done.
Writing objects: 100% (22/22), 13.90 KiB | 490.00 KiB/s, done.
Total 22 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/xames3/FaceID.git
   ef3fd2c..e0208f4  master -> master

~/Desktop/GITHUB_FaceID/FaceID (master)
$
```


## Fetch / reset head


``` git	
~/Desktop/GITHUB_FaceID/FaceID (master   )
$ git fetch

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/OnscreenChecker/
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/OnscreenChecker/
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/OnscreenChecker/
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git add FaceID.py Binaries/RemoteDesktopLogin/OnscreenChecker/

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explore
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yell
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.P
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximiz
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.P
        new file:   Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows
        modified:   FaceID.py

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Faces/
        Models/


~/Desktop/GITHUB_FaceID/FaceID (master)
$ git commit -m 'updated faceid and added login assist'
[master e0208f4] updated faceid and added login assist
 16 files changed, 85 insertions(+), 6 deletions(-)
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explore
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yell
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.P
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximiz
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.P
 create mode 100644 Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git push
Username for 'https://github.com': xames3
Counting objects: 22, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (21/21), done.
Writing objects: 100% (22/22), 13.90 KiB | 490.00 KiB/s, done.
Total 22 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/xames3/FaceID.git
   ef3fd2c..e0208f4  master -> master

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git fetch
remote: Enumerating objects: 22, done.
remote: Counting objects: 100% (22/22), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 17 (delta 9), reused 13 (delta 5), pack-reused 0
Unpacking objects: 100% (17/17), done.
From https://github.com/xames3/FaceID
   e0208f4..3a6f5bf  master     -> origin/master

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git pull
error: cannot pull with rebase: You have unstaged changes.
error: please commit or stash them.

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Excels/ResourceDetails.xlsx

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git rm . -r
error: the following files have local modifications:
    Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
    Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
    Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
    Excels/ResourceDetails.xlsx
(use --cached to keep the file, or -f to force removal)

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git rm . -r -f
rm '.gitignore'
rm 'Admin.pyw'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop2.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explorer.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yellow.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximize.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder2.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_active.P
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_inactive
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.PNG'
rm 'Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows.PNG'
rm 'Binaries/RemoteDesktopLogin/config/Images/img19.jpg'
rm 'Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log'
rm 'Binaries/RemoteDesktopLogin/config/RMGNEncPass.txt'
rm 'Binaries/RemoteDesktopLogin/config/RMGNUserID.txt'
rm 'Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt'
rm 'Binaries/RemoteDesktopLogin/config/RMGPUserID.txt'
rm 'Binaries/RemoteDesktopLogin/config/RMGVEncPass.txt'
rm 'Binaries/RemoteDesktopLogin/config/RMGVUserID.txt'
rm 'Binaries/RemoteDesktopLogin/config/env_config.ps1'
rm 'Binaries/RemoteDesktopLogin/config/rdp_auto_login.ps1'
rm 'Binaries/RemoteDesktopLogin/config/rdp_setting.txt'
rm 'Binaries/RemoteDesktopLogin/open_login_gui.hta'
rm 'Cascades/FacialLandmarksPredictor/facial_landmarks.dat'
rm 'Cascades/Haar/haarcascade_eye.xml'
rm 'Cascades/Haar/haarcascade_eye_tree_eyeglasses.xml'
rm 'Cascades/Haar/haarcascade_frontalcatface.xml'
rm 'Cascades/Haar/haarcascade_frontalcatface_extended.xml'
rm 'Cascades/Haar/haarcascade_frontalface_alt.xml'
rm 'Cascades/Haar/haarcascade_frontalface_alt2.xml'
rm 'Cascades/Haar/haarcascade_frontalface_alt_tree.xml'
rm 'Cascades/Haar/haarcascade_frontalface_default.xml'
rm 'Cascades/Haar/haarcascade_fullbody.xml'
rm 'Cascades/Haar/haarcascade_lefteye_2splits.xml'
rm 'Cascades/Haar/haarcascade_licence_plate_rus_16stages.xml'
rm 'Cascades/Haar/haarcascade_lowerbody.xml'
rm 'Cascades/Haar/haarcascade_profileface.xml'
rm 'Cascades/Haar/haarcascade_righteye_2splits.xml'
rm 'Cascades/Haar/haarcascade_russian_plate_number.xml'
rm 'Cascades/Haar/haarcascade_smile.xml'
rm 'Cascades/Haar/haarcascade_upperbody.xml'
rm 'Excels/ResourceDetails.xlsx'
rm 'FaceID.py'
rm 'Images/Admin_Banner.png'
rm 'Images/Create_New_Profile_Banner.png'
rm 'Images/Create_New_Profile_Banner.psd'
rm 'Images/Face_ID_Banner.png'
rm 'Images/Modify_Profile_Banner.png'
rm 'Images/Profile_Wizard_Banner.png'
rm 'Images/xa_logo.ico'
rm 'Launcher.pyw'
rm 'ModifyExistingProfile.pyw'
rm 'ProfileWizard.pyw'
rm 'README.md'
rm 'SetupFacialRecognition.py'

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git fetch

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git pull
error: cannot pull with rebase: Your index contains uncommitted changes.
error: please commit or stash them.

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        deleted:    .gitignore
        deleted:    Admin.pyw
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explore
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yell
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.P
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximiz
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.P
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows
        deleted:    Binaries/RemoteDesktopLogin/config/Images/img19.jpg
        deleted:    Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        deleted:    Binaries/RemoteDesktopLogin/config/RMGNEncPass.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGNUserID.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGVEncPass.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGVUserID.txt
        deleted:    Binaries/RemoteDesktopLogin/config/env_config.ps1
        deleted:    Binaries/RemoteDesktopLogin/config/rdp_auto_login.ps1
        deleted:    Binaries/RemoteDesktopLogin/config/rdp_setting.txt
        deleted:    Binaries/RemoteDesktopLogin/open_login_gui.hta
        deleted:    Cascades/FacialLandmarksPredictor/facial_landmarks.dat
        deleted:    Cascades/Haar/haarcascade_eye.xml
        deleted:    Cascades/Haar/haarcascade_eye_tree_eyeglasses.xml
        deleted:    Cascades/Haar/haarcascade_frontalcatface.xml
        deleted:    Cascades/Haar/haarcascade_frontalcatface_extended.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_alt.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_alt2.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_alt_tree.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_default.xml
        deleted:    Cascades/Haar/haarcascade_fullbody.xml
        deleted:    Cascades/Haar/haarcascade_lefteye_2splits.xml
        deleted:    Cascades/Haar/haarcascade_licence_plate_rus_16stages.xml
        deleted:    Cascades/Haar/haarcascade_lowerbody.xml
        deleted:    Cascades/Haar/haarcascade_profileface.xml
        deleted:    Cascades/Haar/haarcascade_righteye_2splits.xml
        deleted:    Cascades/Haar/haarcascade_russian_plate_number.xml
        deleted:    Cascades/Haar/haarcascade_smile.xml
        deleted:    Cascades/Haar/haarcascade_upperbody.xml
        deleted:    Excels/ResourceDetails.xlsx
        deleted:    FaceID.py
        deleted:    Images/Admin_Banner.png
        deleted:    Images/Create_New_Profile_Banner.png
        deleted:    Images/Create_New_Profile_Banner.psd
        deleted:    Images/Face_ID_Banner.png
        deleted:    Images/Modify_Profile_Banner.png
        deleted:    Images/Profile_Wizard_Banner.png
        deleted:    Images/xa_logo.ico
        deleted:    Launcher.pyw
        deleted:    ModifyExistingProfile.pyw
        deleted:    ProfileWizard.pyw
        deleted:    README.md
        deleted:    SetupFacialRecognition.py


~/Desktop/GITHUB_FaceID/FaceID (master)
$ gti reset HEAD
bash: gti: command not found

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git reset HEAD
Unstaged changes after reset:
D       .gitignore
D       Admin.pyw
D       Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop2.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explorer.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yellow.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximize.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder.PN
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_click_folder2.P
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_acti
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_manager_inac
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.PNG
D       Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows.PNG
D       Binaries/RemoteDesktopLogin/config/Images/img19.jpg
D       Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
D       Binaries/RemoteDesktopLogin/config/RMGNEncPass.txt
D       Binaries/RemoteDesktopLogin/config/RMGNUserID.txt
D       Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
D       Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
D       Binaries/RemoteDesktopLogin/config/RMGVEncPass.txt
D       Binaries/RemoteDesktopLogin/config/RMGVUserID.txt
D       Binaries/RemoteDesktopLogin/config/env_config.ps1
D       Binaries/RemoteDesktopLogin/config/rdp_auto_login.ps1
D       Binaries/RemoteDesktopLogin/config/rdp_setting.txt
D       Binaries/RemoteDesktopLogin/open_login_gui.hta
D       Cascades/FacialLandmarksPredictor/facial_landmarks.dat
D       Cascades/Haar/haarcascade_eye.xml
D       Cascades/Haar/haarcascade_eye_tree_eyeglasses.xml
D       Cascades/Haar/haarcascade_frontalcatface.xml
D       Cascades/Haar/haarcascade_frontalcatface_extended.xml
D       Cascades/Haar/haarcascade_frontalface_alt.xml
D       Cascades/Haar/haarcascade_frontalface_alt2.xml
D       Cascades/Haar/haarcascade_frontalface_alt_tree.xml
D       Cascades/Haar/haarcascade_frontalface_default.xml
D       Cascades/Haar/haarcascade_fullbody.xml
D       Cascades/Haar/haarcascade_lefteye_2splits.xml
D       Cascades/Haar/haarcascade_licence_plate_rus_16stages.xml
D       Cascades/Haar/haarcascade_lowerbody.xml
D       Cascades/Haar/haarcascade_profileface.xml
D       Cascades/Haar/haarcascade_righteye_2splits.xml
D       Cascades/Haar/haarcascade_russian_plate_number.xml
D       Cascades/Haar/haarcascade_smile.xml
D       Cascades/Haar/haarcascade_upperbody.xml
D       Excels/ResourceDetails.xlsx
D       FaceID.py
D       Images/Admin_Banner.png
D       Images/Create_New_Profile_Banner.png
D       Images/Create_New_Profile_Banner.psd
D       Images/Face_ID_Banner.png
D       Images/Modify_Profile_Banner.png
D       Images/Profile_Wizard_Banner.png
D       Images/xa_logo.ico
D       Launcher.pyw
D       ModifyExistingProfile.pyw
D       ProfileWizard.pyw
D       README.md
D       SetupFacialRecognition.py

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    .gitignore
        deleted:    Admin.pyw
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/LoginAssist.py
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/desktop
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/explore
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/hta_gui
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ie_yell
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/login.P
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/maximiz
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/ok.png
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/one_cli
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/server_
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/start.P
        deleted:    Binaries/RemoteDesktopLogin/OnscreenChecker/Screenshots/windows
        deleted:    Binaries/RemoteDesktopLogin/config/Images/img19.jpg
        deleted:    Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        deleted:    Binaries/RemoteDesktopLogin/config/RMGNEncPass.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGNUserID.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGVEncPass.txt
        deleted:    Binaries/RemoteDesktopLogin/config/RMGVUserID.txt
        deleted:    Binaries/RemoteDesktopLogin/config/env_config.ps1
        deleted:    Binaries/RemoteDesktopLogin/config/rdp_auto_login.ps1
        deleted:    Binaries/RemoteDesktopLogin/config/rdp_setting.txt
        deleted:    Binaries/RemoteDesktopLogin/open_login_gui.hta
        deleted:    Cascades/FacialLandmarksPredictor/facial_landmarks.dat
        deleted:    Cascades/Haar/haarcascade_eye.xml
        deleted:    Cascades/Haar/haarcascade_eye_tree_eyeglasses.xml
        deleted:    Cascades/Haar/haarcascade_frontalcatface.xml
        deleted:    Cascades/Haar/haarcascade_frontalcatface_extended.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_alt.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_alt2.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_alt_tree.xml
        deleted:    Cascades/Haar/haarcascade_frontalface_default.xml
        deleted:    Cascades/Haar/haarcascade_fullbody.xml
        deleted:    Cascades/Haar/haarcascade_lefteye_2splits.xml
        deleted:    Cascades/Haar/haarcascade_licence_plate_rus_16stages.xml
        deleted:    Cascades/Haar/haarcascade_lowerbody.xml
        deleted:    Cascades/Haar/haarcascade_profileface.xml
        deleted:    Cascades/Haar/haarcascade_righteye_2splits.xml
        deleted:    Cascades/Haar/haarcascade_russian_plate_number.xml
        deleted:    Cascades/Haar/haarcascade_smile.xml
        deleted:    Cascades/Haar/haarcascade_upperbody.xml
        deleted:    Excels/ResourceDetails.xlsx
        deleted:    FaceID.py
        deleted:    Images/Admin_Banner.png
        deleted:    Images/Create_New_Profile_Banner.png
        deleted:    Images/Create_New_Profile_Banner.psd
        deleted:    Images/Face_ID_Banner.png
        deleted:    Images/Modify_Profile_Banner.png
        deleted:    Images/Profile_Wizard_Banner.png
        deleted:    Images/xa_logo.ico
        deleted:    Launcher.pyw
        deleted:    ModifyExistingProfile.pyw
        deleted:    ProfileWizard.pyw
        deleted:    README.md
        deleted:    SetupFacialRecognition.py

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git pull
error: cannot pull with rebase: You have unstaged changes.
error: please commit or stash them.

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git checkout repository_assets
Switched to a new branch 'repository_assets'
Branch 'repository_assets' set up to track remote branch 'repository_assets' from '

~/Desktop/GITHUB_FaceID/FaceID (repositor
$ git branch
  master
* repository_assets

~/Desktop/GITHUB_FaceID/FaceID (repositor
$ git checkout master
Checking out files: 100% (66/66), done.
Switched to branch 'master'
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git fetch

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git pull master
fatal: 'master' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git pull
Updating e0208f4..3a6f5bf
Fast-forward
 .../LoginAssist.py => terminal/LoginAssist.pyw}    |  28 ++--------------
 .../screenshots}/desktop.PNG                       | Bin
 .../screenshots}/desktop2.PNG                      | Bin
 .../screenshots}/explorer.PNG                      | Bin
 .../screenshots}/hta_gui.PNG                       | Bin
 .../screenshots}/ie_yellow.PNG                     | Bin
 .../Screenshots => terminal/screenshots}/login.PNG | Bin
 .../screenshots}/maximize.PNG                      | Bin
 .../Screenshots => terminal/screenshots}/ok.png    | Bin
 .../screenshots}/one_click_folder.PNG              | Bin
 .../screenshots}/one_click_folder2.PNG             | Bin
 .../screenshots}/server_manager_active.PNG         | Bin
 .../screenshots}/server_manager_inactive.PNG       | Bin
 .../Screenshots => terminal/screenshots}/start.PNG | Bin
 .../screenshots}/windows.PNG                       | Bin
 FaceID.py                                          |  37 +++++++++++++++------
 SetupFacialRecognition.py                          |   4 +--
 17 files changed, 30 insertions(+), 39 deletions(-)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/LoginAssist.py => terminal/LoginAssist.pyw} (56%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/desktop.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/desktop2.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/explorer.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/hta_gui.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/ie_yellow.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/login.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/maximize.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/ok.png (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/one_click_folder.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/one_click_folder2.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/server_manager_active.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/server_manager_inactive.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/start.PNG (100%)
 rename Binaries/RemoteDesktopLogin/{OnscreenChecker/Screenshots => terminal/screenshots}/windows.PNG (100%)
Current branch master is up to date.

~/Desktop/GITHUB_FaceID/FaceID (master)
$
```

## push the inprogress file
``` git
~/Desktop/GITHUB_FaceID/FaceID (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Binaries/RemoteDesktopLogin/config/Logs/Rdp_Login.log
        modified:   Binaries/RemoteDesktopLogin/config/RMGPEncPass.txt
        modified:   Binaries/RemoteDesktopLogin/config/RMGPUserID.txt
        modified:   Binaries/RemoteDesktopLogin/terminal/LoginAssist.pyw
        modified:   Excels/ResourceDetails.xlsx
        modified:   FaceID.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Binaries/RemoteDesktopLogin/terminal/screenshots/tog_ie.PNG
        Faces/
        Models/

no changes added to commit (use "git add" and/or "git commit -a")

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git add FaceID.py

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git commit -m 'removed dependency on loginassist file'
[master 54c02e0] removed dependency on loginassist file
 1 file changed, 31 insertions(+), 2 deletions(-)

~/Desktop/GITHUB_FaceID/FaceID (master)
$ git push
Username for 'https://github.com': xames3
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 695 bytes | 115.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/xames3/FaceID.git
   3a6f5bf..54c02e0  master -> master

~/Desktop/GITHUB_FaceID/FaceID (master)
$
```
