---
title: "리눅스 명령어 cp"
date: 2022-04-22T22:49:30+09:00
draft: false
hero: images/cp-hero.png
menu:
  sidebar:
    name: cp
    identifier: linux-cp
    parent: linux
    weight: 10
---
<!-- man page: https://man7.org/linux/man-pages/index.html -->
# cp
<!-- man page 내의 NAME 내용을 입력 -->
copy files and directories

{{< vs 2 >}}

---
## 용도
<!-- 명령어 주 활용 용도 작성 -->
파일 혹은 디렉토리를 복사하는 데 활용한다.

{{< vs 2 >}}

---
## 명령어 포맷
<!-- 명령어 주 활용 용도 작성 -->
cp [OPTION] (SOURCE) (DEST)      

{{< vs 2 >}}

---
## 옵션
<!-- 명령어 주 활용 옵션 작성 -->
| Useful options       | Usage                                                         |
| -------------------- | ------------------------------------------------------------- |
| -R, -r --recursive   | 디렉토리의 하위 파일들도 모두 복사한다                           |

{{< vs 2 >}}

---
## 예시
<!-- 기본 명령어 + 옵션 활용 예시 작성 -->
   - cp file1 file2

     {{< img src="images/cp.png" >}}

      {{< vs 2 >}}

   - cp -r test/ test2/

      {{< img src="images/cpOpR.png" >}}

      {{< vs 2 >}}