---
title: "리눅스 명령어: ls"
date: 2021-04-29T00:07:30+09:00
draft: false
---

### ls - list directory contents

1. 용도: 디렉토리 내의 파일 정보를 확인하기 위해서 사용한다.
2. 옵션

| Useful options       | Usage                                                         |
| -------------------- | ------------------------------------------------------------- |
| -a, --all            | 숨김 파일(.으로 시작하는 파일들)도 포함해서 출력              |
| -l                   | 파일의 종류, 권한, 소유자 등 자세한 정보를 포함해서 출력      |
| -h, --human-readable | 파일의 사이즈를 숫자만이 아닌 단위로 표기 (e.g. 1K, 234M, 2G) |

3. 예시

   - ls

     ![cat](/linux/ls.png)

   - ls -a

     ![ls -a](/linux/ls%20-a.png)

   - ls -l

     ![ls -l](/linux/ls%20-l.png)

   - ls -al

     ![ls -al](/linux/ls%20-al.png)

   - ls -alh

     ![ls -alh](/linux/ls%20-alh.png)
