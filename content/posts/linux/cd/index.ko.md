---
title: "리눅스 명령어: cd"
date: 2021-04-29T00:07:30+09:00
draft: false
---

# cd

Change the working directory

{{< vs 2 >}}

---
## 용도

작업중인 디렉토리의 위치를 변경한다


#### 주의사항 

이동할 디렉토리를 지정하지 않으면 해당 계정의 HOME Directory (일반적으로 /home/(계정이름)/ or ~)로 이동한다.

{{< vs 2 >}}

---
## 디렉토리 명에서 활용하는 기호

  | Notation | Meanings                                              |
  | -------- | ----------------------------------------------------- |
  | ~        | 사용자의 home directory (일반적으로 /home/(username)) |
  | /        | root directory                                        |
  | .        | 지금 작업중인 디렉토리                                |
  | ..       | 지금 작업중인 디렉토리의 상위 디렉토리                |
  | -        | 지금 작업하기 이전의 디렉토리 (뒤로가기)              |


{{< vs 2 >}}

---
## 예시

   - *cd*

     {{< img src="images/cd.png" >}}

      {{< vs 2 >}}
   - *cd (directory)*

     {{< img src="images/cdtest.png" >}}

