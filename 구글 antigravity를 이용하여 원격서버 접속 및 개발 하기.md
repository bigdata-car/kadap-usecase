# Antigravity 설치

https://antigravity.google/download

<img width="1186" height="784" alt="image" src="https://github.com/user-attachments/assets/93c77fda-a956-4376-9a25-7a6d73c19c7c" />

```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://us-central1-apt.pkg.dev/doc/repo-signing-key.gpg | \
  sudo gpg --dearmor --yes -o /etc/apt/keyrings/antigravity-repo-key.gpg
echo "deb [signed-by=/etc/apt/keyrings/antigravity-repo-key.gpg] https://us-central1-apt.pkg.dev/projects/antigravity-auto-updater-dev/ antigravity-debian main" | \
  sudo tee /etc/apt/sources.list.d/antigravity.list > /dev/null
```

```
sudo apt update && sudo apt install antigravity
```


# 원격 개발 서버 생성

> 본 문서에서는 `자동차 산업 클라우드`에서 가상 머신(VM)을 생성내용을 담고 있습니다. AWS나 개인 서버도 생성 후의 방식은 동일 합니다.

# Antigravity 에서 ssh로 원격 서버 접속

## 1. 인증키를 이용하여 접속 하기 (추천) 

### 1.1 접속할 서버의 입력키(*.pem)을 다운로드 받습니다. 

자동차 산업 클라우드에서는 VM > 접속 정보 > `접속 인증 키(Key) : default` 를 클릭하여 다운로드 받을수 있습니다. 

<img width="379" height="381" alt="image" src="https://github.com/user-attachments/assets/b27d86b4-3555-4d1d-81db-9fc387d32e1c" />

### 1.2 클라이언트 툴에서 접속 정보 및 키 위치 입력 하기 

<img width="886" height="274" alt="image" src="https://github.com/user-attachments/assets/82b90416-c8ec-4bc3-a051-da726c8cffa1" />

```
  Host 10.10.17.63
    HostName 10.10.17.63
    User kadap
    IdentityFile "C:\Users\admin\Downloads\2-82_default.pem"
    Port 22
    StrictHostKeyChecking accept-new
```

### `Ctrl` + `Shift` + `p` : remote-ssh

<img width="709" height="142" alt="image" src="https://github.com/user-attachments/assets/a40ab005-fe38-47b7-9cc6-8b4e599fd2ea" />

<img width="705" height="140" alt="image" src="https://github.com/user-attachments/assets/2cfec886-423a-4c24-9a6f-52e037030995" />



## 2. 비밀번호 키보드 입력으로 접속 하기 

> 일부 윈도우 환경에서는 입력창이 활성화 되지 않는 오류 보고 됨 

Crtl + Shift + p

<img width="740" height="225" alt="image" src="https://github.com/user-attachments/assets/2c22d75c-206a-44d9-bcfc-b50139e4bd7f" />

<img width="709" height="140" alt="image" src="https://github.com/user-attachments/assets/6bb720a1-4e66-481b-93f8-5b962753d238" />


```
2025-12-26 12:08:13.693 [info] [Trace	- 03:08:13.692] [stderr] @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
2025-12-26 12:08:13.693 [info] [Trace	- 03:08:13.692] [stderr] @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
2025-12-26 12:08:13.693 [info] [Trace	- 03:08:13.692] [stderr] @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
2025-12-26 12:08:13.693 [info] [Trace	- 03:08:13.693] [stderr] IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] Someone could be eavesdropping on you right now (man-in-the-middle attack)!
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] It is also possible that a host key has just been changed.
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] The fingerprint for the ED25519 key sent by the remote host is
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] SHA256:x76V2wABf8aNIis5eikzpsl6DuQaNaDXR6mTsF2XZvk.
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] Please contact your system administrator.
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] Add correct host key in C:\\Users\\admin/.ssh/known_hosts to get rid of this message.
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] Offending ECDSA key in C:\\Users\\admin/.ssh/known_hosts:26
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.693] [stderr] Host key for 10.10.17.32 has changed and you have requested strict checking.
2025-12-26 12:08:13.694 [info] [Trace	- 03:08:13.694] [stderr] Host key verification failed.
2025-12-26 12:08:13.698 [info] [Error	- 03:08:13.697] SSH server closed unexpectedly.
Error code: 255
```

<img width="709" height="106" alt="image" src="https://github.com/user-attachments/assets/e58098de-0a56-46c5-9c65-293eae399112" />
