---
title: "리눅스 명령어: cat"
date: 2021-04-29T00:07:30+09:00
draft: false
---

### cat - concatenate files and print on the standard output

1. 용도: 파일의 내용을 확인하는 과정에 사용된다.
2. 옵션

| Useful options | Usage                                                        |
| -------------- | ------------------------------------------------------------ |
| -A             | -vET와 같은 결과가 나온다.                                   |
| -v             | 원래 따로 출력되지 않는 string을 ^ 와 M- 의 형태로 출력한다. |
| -E             | 각 줄의 마지막에 $를 출력한다.                               |
| -T             | ^l의 형태로 TAB을 출력한다.                                  |

3. 예시

   - cat

     ![cat](static/linux/cat.png)

   - cat -A

     ![cat -A](static/linux/cata.png)
