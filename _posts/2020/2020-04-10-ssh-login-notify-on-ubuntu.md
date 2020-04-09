---
title:  "텔레그램을 이용한 SSH 접속 알림 (Ubuntu 18.04 LTS)"
tags: Ubuntu
---

우분투(18.04 LTS) 서버에 SSH 로그인하면 텔레그램으로 메시지를 전송한다.


1. /etc/pam.d/sshd 파일에 아래 내용을 추가한다.
    ```
    session optional pam_exec.so seteuid /etc/ssh/login-notify.sh
    ```
2. /etc/ssh/login-notify.sh 파일을 만들고 퍼미션을 설정한다.
    ```sh
    $ sudo touch /etc/ssh/login-notify.sh
    $ sudo chmod +x /etc/ssh/login-notify.sh
    ```
3. /etc/ssh/login-notify.sh 파일에 아래 내용을 입력한다.
    ```sh
    #!/bin/sh

    apiToken=112233445:AAFaljLKJdAJklJkd04jlkvcljkdf0ajv-sjelkafjkle
    chatId=123456789
    url="https://api.telegram.org/bot$apiToken/sendMessage"

    if [ "$PAM_TYPE" != "close_session" ]; then
      host="`hostname`"
      message="SSH Login: $PAM_USER from $PAM_RHOST on $host"

      curl -s -X POST $url -d chat_id=$chatId -d text="$message"
    fi
    ```
