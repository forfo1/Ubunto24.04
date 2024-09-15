# Ubunto24.04

![image](https://github.com/user-attachments/assets/9e0b3e77-0775-4133-ad8f-361b92159c17)    
리인스톨할때 **22.04** 꼭 확인하시긔

리인스톨 마친 완전 깨끗한 콘타보로 준비해주세요    
시스템 업그레이드여서 스크립트불가능. 잘읽고 따라하시긔 할일많아요     
**같은 칸에 있는건 같이입력, 따로 둔건 따로입력.**

### 0.
콘타보 로그인하기. 
리인스톨 하고 처음 들어가려고 하면
```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

경고문 뜰수도 있어요.

  ssh-keygen -R 123.456

입력하고

  ssh root@123.456

하면 로그인됨 (123.456 에는 당연히 본인 VPS IP넣기)

### 1.
```
sudo apt update -y
sudo apt list --upgradable | more
sudo apt upgrade -y
```
완료후
```
sudo reboot
```

서버 리부팅해요. 5분간 콘타보 로그인하지않고 기다립니다.

### 2.
로그인하면
```
New release '24.04.1 LTS' available.
Run 'do-release-upgrade' to upgrade to it.

  _____
 / ___/___  _  _ _____ _   ___  ___
| |   / _ \| \| |_   _/ \ | _ )/ _ \
| |__| (_) | .` | | |/ _ \| _ \ (_) |
 \____\___/|_|\_| |_/_/ \_|___/\___/
```
#### **New release '24.04.1 LTS' available.**

흑인하시고 아래 따라치기

```
sudo apt install ubuntu-release-upgrader-core
```

```
grep 'lts' /etc/update-manager/release-upgrades
cat /etc/update-manager/release-upgrades
```
```
sudo do-release-upgrade -d
```

#### **중요!!** **스탑!!!!**
여기서 만약
```
root@vmi123123:~# sudo do-release-upgrade -d
Checking for a new Ubuntu release
Upgrades to the development release are only
available from the latest supported release.
```
이 글이 보이면 3번으로, 아니면 4번으로. 아무것도 누르지말고 4번으로 가세요


## 3.

```
sudo sed 's/^Prompt=lts/Prompt=normal/' /etc/update-manager/release-upgrades | sudo tee /etc/update-manager/release-upgrades > /dev/null
```
```
sudo do-release-upgrade
```

## 4.

![1](https://github.com/user-attachments/assets/79e7cd98-68e5-410a-97c2-fe70dd97848e)    
  **y 엔터**

![2](https://github.com/user-attachments/assets/f4ec478e-12d1-4d00-a275-dc4666373f75)    
  **y 엔터**

![image](https://github.com/user-attachments/assets/49a7fa35-468b-415f-9e42-ecbe91903750)    
  **엔터**

![image](https://github.com/user-attachments/assets/9f8c4c8b-9dfb-4171-b81a-7114d6f1145d)    
  **y 엔터**

![image](https://github.com/user-attachments/assets/bbf7d967-f572-4197-96ac-c500cdf734c1)    
  **y 엔터**
  
![image](https://github.com/user-attachments/assets/39b09890-82b5-4439-8a79-7a7bfb770747)    
  **y 엔터**

![image](https://github.com/user-attachments/assets/61d94555-e854-4047-92b6-0ca30f9d1c9a)    
  **맨위에꺼 (install the package maintainer's version)방향키로 움직이고 엔터**

![image](https://github.com/user-attachments/assets/1efb73a9-05ce-4b4c-9598-84d320167d44)    
  **맨위에꺼 (install the package maintainer's version)방향키로 움직이고 엔터**

![image](https://github.com/user-attachments/assets/ac2a37ba-cf15-49d9-b776-cd10464bdc45)    
  **y 엔터**

![image](https://github.com/user-attachments/assets/155d26cd-4080-44c0-b838-26b22aa1b599)    
  **y 엔터**    
서버 다시 리부팅. 5분뒤에 접속하세효.

## 5.

```
Welcome to Ubuntu 24.04.1 LTS (GNU/Linux 6.8.0-44-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro
  _____
 / ___/___  _  _ _____ _   ___  ___
| |   / _ \| \| |_   _/ \ | _ )/ _ \
| |__| (_) | .` | | |/ _ \| _ \ (_) |
 \____\___/|_|\_| |_/_/ \_|___/\___/
```

### **Welcome to Ubuntu 24.04.1 LTS**
**24.04 업데이트 완!!**
