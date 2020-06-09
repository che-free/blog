---
title:  "Bitbucket SSH Key 등록 및 TortoiseGit SSH Key 설정"
---

## Bitbucket SSH Key 등록 및 TortoiseGit SSH Key 설정

### 1. SSH Key 생성
> SSH Key 생성 명령 : ssh-keygen -t rsa -C "your_email@example.com"

```
C:\>ssh-keygen -t rsa -C "your_email@example.com"
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\user1/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in C:\Users\user1/.ssh/id_rsa.
Your public key has been saved in C:\Users\user1/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:5Zh7mGGcM4J6PkASS75bDkB4JHEudpM9o7HECJwURkQ your_email@example.com
The key's randomart image is:
+---[RSA 2048]----+
|@E=              |
|=O+ o            |
|=*.B +    .      |
|=o+ =.o. *       |
|.o.o. . S .      |
| o.o   o B       |
|  *..   + .      |
| . +.    .       |
|    ..           |
+----[SHA256]-----+
```

> ssh-keygen 명령은 OpenSSH에 포함되어있다.


### 2. Bitbucket에 생성한 SSH key 추가하기
1. Bitbucket Server로 로그인
1. Manage account > SSH keys에서 Add key 버튼 클릭
1. Add public key에서 Key 영역에 위에서 생성한 id_rsa.pub 파일의 내용 붙여넣기
    > id_rsa.pub 파일 내용 : "ssh-rsa AAAAB3...." (406 byte)


### 3. PuTTY 키 파일 생성
1. puttygen.exe 실행
1. Conversons > Import key 메뉴 실행
1. id_rsa 파일 선택
1. Save private key 버튼 클릭
1. id_rsa 파일과 같은 경로에 id_rsa_putty.ppk 파일명으로 저장


### TortoiseGit Clone
1. 탐색기를 열고 Git 저장소를 저장 할 폴더에서 마우스 오른쪽 버튼 클릭 후 "Git Clone..." 메뉴 선택
1. Git clone 설정 화면에서 Load Putty Key 체크박스 선택 후 id_rsa_putty.ppk 파일 선택
1. Git Clone 진행


### TortoiseGit 설정 (기존 Git 저장소가 있는 경우)
1. 탐색기를 열고 Git 저장소 폴더에서 마우스 오른쪽 버튼 클릭 후 TortoiseGit > Settings 메뉴 선택
1. Settings > Git > Remote 메뉴 선택
1. 오른쪽 Remote에서 origin 선택
1. Putty Key에서 id_rsa_putty.ppk 파일 선택
