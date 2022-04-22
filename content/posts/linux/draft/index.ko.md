---
title: "리눅스 명령어 default"
date: 2022-04-22T22:49:30+09:00
draft: true
hero: image-hero
menu:
  sidebar:
    name: (cmd)
    identifier: linux-(cmd)
    parent: linux
    weight: 10
---
<!-- man page: https://man7.org/linux/man-pages/index.html -->
# (cmd)
<!-- man page 내의 NAME 내용을 입력 -->
list directory contents

{{< vs 2 >}}

---
## 용도
<!-- 명령어 주 활용 용도 작성 -->
디렉토리 내의 파일 정보를 확인하기 위해서 사용한다.

{{< vs 2 >}}

---
## 명령어 포맷
<!-- 명령어 작성 방식 -->
ls [directory]

{{< vs 2 >}}

---
## 옵션
<!-- 명령어 주 활용 옵션 작성 -->
| Useful options       | Usage                                                         |
| -------------------- | ------------------------------------------------------------- |
| -a, --all            | 숨김 파일(.으로 시작하는 파일들)도 포함해서 출력              |
| -l                   | 파일의 종류, 권한, 소유자 등 자세한 정보를 포함해서 출력      |
| -h, --human-readable | 파일의 사이즈를 숫자만이 아닌 단위로 표기 (e.g. 1K, 234M, 2G) |

{{< vs 2 >}}

---
## 예시
<!-- 기본 명령어 + 옵션 활용 예시 작성 -->
   - ls

     {{< img src="images/ls.png" >}}

      {{< vs 2 >}}

   - ls -a

     {{< img src="images/ls%20-a.png" >}}

      {{< vs 2 >}}

   - ls -l

      {{< img src="images/ls%20-l.png" >}}

      {{< vs 2 >}}


   - ls -al

      {{< img src="images/ls%20-al.png" >}}

      {{< vs 2 >}}


   - ls -alh

      {{< img src="images/ls%20-alh.png" >}}

      {{< vs 2 >}}

