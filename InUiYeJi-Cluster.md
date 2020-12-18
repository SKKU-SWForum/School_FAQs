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

    [How to use Mobaxterm](https://github.com/SKKU-SWForum/School_FAQs/blob/main/How%20to%20use%20Mobaxterm.md)

4. I would like to change my password.
    - You can use 'yppasswd' command to change password. 
