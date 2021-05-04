---
title: "리눅스 명령어"
date: 2021-04-29T00:07:30+09:00
draft: false
hero: images/commands-hero.png
menu:
  sidebar:
    name: 명령어 모음
    identifier: linux-lists
    parent: linux
    weight: 10
---

# 리눅스 기초 명령어 모음

{{< vs 2 >}}

---
## Information

- 파일과 디렉토리에 모두 적용가능한 명령어의 경우 일반적으로 디렉토리에 적용하려할 경우 추가적인 옵션을 넣어야 하는 경우가 많습니다. 옵션 확인하셔서 적용하시기 바랍니다.
- 기타 Notation들은 아래 표를 참고 바랍니다.

   | Notation  | Meaning                                                       |
   | --------- | ------------------------------------------------------------- |
   | (-------) | 입력하지 않아도 되는 부가 옵션                                |
   | [------]  | command 실행에 필수적이거나 없으면 실행 전과 변화가 없는 옵션 |
   | usage     | 구체적인 활용법을 정리한 페이지로 링크                        |

{{< vs 2 >}}

---
## Linux filesystem

| command                     | description                                      | example             | man page                                                   | usage                         |
| --------------------------- | :----------------------------------------------- | ------------------- | ---------------------------------------------------------- | ----------------------------- |
| ls (option) (directory)     | directory 내 리눅스 파일 정보 탐색               | ls                  | [Link](https://man7.org/linux/man-pages/man1/ls.1.html)    | [Link](https://skkuoverflow.com/ko/posts/linux/ls/)  |
| cd (directory)              | directory 로 경로를 이동                         | cd Test/            | [Link](https://man7.org/linux/man-pages/man1/cd.1p.html)   | [Link](https://skkuoverflow.com/ko/posts/linux/cd/)  |
| mkdir [name]                | name을 이름으로 가진 directory 생성              | mkdir Test          | [Link](https://man7.org/linux/man-pages/man1/mkdir.1.html) |                               |
| cp (option) [name1] [name2] | name1 파일/디렉토리를 name2 파일/디렉토리로 복사 | cp test1 test2      | [Link](https://man7.org/linux/man-pages/man1/cp.1.html)    |                               |
| mv (option) [name1] [name2] | name1 파일을 name2파일로 이동                    | mv file1 Test/file2 | [Link](https://man7.org/linux/man-pages/man1/mv.1.html)    |                               |
| rm (option) [name]          | name 파일/디렉토리를 삭제                        | rm file1            | [Link](https://man7.org/linux/man-pages/man1/rm.1.html)    | [Link](https://skkuoverflow.com/ko/posts/linux/rm/)  |
| cat (option) (filename)     | filename 내용을 출력                             | cat file1           | [Link](https://man7.org/linux/man-pages/man1/cat.1.html)   | [Link](https://skkuoverflow.com/ko/posts/linux/cat/) |

{{< vs 2 >}}

---
## Linux package manager

### 시작하기에 앞서...

1. **CAUTION!** 표시는 **서버 전체를 재설정해야 할 수 있을 정도**의 위험도를 가진 명령어입니다. 자기 데스크탑이면 몰라도 랩 서버 혹은 타인의 서버에서 하는 경우 꼭! 담당자에게 확인을 받고 실행을 하시기 바랍니다!
2. Caution 표시는 기존 패키지와의 충돌 위험성이 있는 명령어입니다. 만약 실행 이후 문제가 생긴다면 이 명령어가 문제는 아니었는지 고려해보시면 됩니다.
3. 일반적으로 위의 경고 표시는 설치하는 명령어들입니다. 윈도우에서도 설치할 때 조심할 필요가 있듯, 리눅스도 그렇습니다.

### Ubuntu

| command                    | description                                    | example              | caution      |
| -------------------------- | ---------------------------------------------- | -------------------- | ------------ |
| apt update                 | 기존에 설치된 패키지의 업데이트 확인           | sudo apt update      |              |
| apt upgrade                | 업데이트할 패키지가 있는 경우 업데이트 진행    | sudo apt upgrade     | **CAUTION!** |
| apt install [package]      | package와 package가 요구하는 추가 package 설치 | sudo apt install gcc | Caution      |
| apt-cache policy [package] | package와 package에 대한 정보 탐색             | apt-cache policy gcc |              |

{{< vs 2 >}}

---
## Others

| command       | description                                                  | example |
| ------------- | ------------------------------------------------------------ | ------- |
| man [command] | command의 역할, 활용법, 옵션 등 매뉴얼을 출력해줍니다. RTFM! | man cat |

---

# Contributors

| Name     | Contribution                                                            |
| -------- | ----------------------------------------------------------------------- |
| raven724 | Create file, write information, Linux filesystem, Linux package manager |
