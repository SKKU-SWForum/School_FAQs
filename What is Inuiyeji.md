
# What is Inuiyeji cluster?

'Inuiyeji' cluster is a server cluster that is available for SKKU students who major in Software Engineering. Currently the 'In' server is runs independently, and the 'uiyeji' server is bounded with nfs.

Translation of the below notice about the server. ([https://cs.skku.edu/news/notice/view/2587](https://cs.skku.edu/news/notice/view/2587))

<details>
<summary>Translated Notice</summary>
[Software college's 4-node Linux cluster server setup completed]

4-node Linux cluster server is now available for SW college students. 

Students who want to use it can use it freely.

**Hosts:**
```
- swin.skku.edu

- swui.skku.edu 

- swye.skku.edu

- swji.skku.edu
```


- SSH Port: 1398 (SKKU's date of establishment)

- ID: Student ID

- Password: Last Name in full capital letters.
```
ex: PARK (If this throws an error, try writing your full name in capital letters, with no spaces)
```
 
- Others:
1) All accounts are shared by four nodes by NIS.  
2) To Change password after login, use the following command: `yppasswd`
3) You can make private homepages by creating a `public_html` directory under the home directory, but due to security concerns, it will be only accessible on campus network. (It is recommended to use this only for html-related classes/courses.)
4) Account related inquiry 
- Professor Nam Bum-seok(bnam@skku.edu)
</details>

## Hosts
- 인(In): `swin.skku.edu`
- 의(Ui): `swui.skku.edu`
- 예(Ye): `swye.skku.edu`
- 지(Ji): `swji.skku.edu`

## Connection guide
| Type | Value | Remarks |
|:----:|:--:|------|
| Port | 1398 | SKKU's date of establishment |
| ID | Student ID | 10 digit |
| PW | Last Name | All in capital letters; If this throws an error, try writing your full name in capital letters, with no spaces |

# FAQ

### Inuiyeji Cluster

 0. Please note that the server is divided by 'In' and 'uiyeji'. + Read more about 'Inuiyeji' here: [What is Inuiyeji?](../eng_translation/What%20is%20Inuiyeji.md)

1. Is the server down?
    - We'll provide a server status service soon.
2. I can't connect to the server.
    - This depends on the error.
        - `Connection reset by peer`: This is probably the server blocking your IP. Try accessing from a different IP.
        - It says my password is different: If you've ever connected to 'Inuiyeji' server before, try inserting your password and your last 8 digits of your student ID.
        - If the above solution doesn't work: If you haven't logged in for a long time, your account may not have been created. You can contact Professor Nam Bum-suk and ask him to create an account for you. (Email address: [bnam@skku.edu](mailto:bnam@skku.edu))
3. How can I send a file to 'Inuiyeji'?
    - You can use `scp` command-line utility.
    ```sh
    scp -P 1398 (file you want to send) (your ID)@swji.skku.edu:/home/(your ID)/(Directory you want the file sent to)
    ```

    - You can use sftp programs if you don't want to use the command line. You can use `mobaxterm` for windows.

    [Mobaxterm 사용법](https://github.com/SKKU-SWForum/School_FAQs/blob/main/Mobaxterm%20%EC%82%AC%EC%9A%A9%EB%B2%95.md)

4. I would like to change my password.
    - You can use 'yppasswd' command to change password. 