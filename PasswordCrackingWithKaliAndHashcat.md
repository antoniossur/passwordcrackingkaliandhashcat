# <b>Password Cracking With Kali Linux And Hashcat </b>
There are two methods to cracking passwords: <br>
First is Online which uses the server and try many times to crack the passwords. <br>
Second is Offline which uses hashes code to find the passwords.

# <b> Online </b>
For Online method, you must download Hydra on Terminal. <br>
https://www.geeksforgeeks.org/how-to-install-and-use-hydra-in-linux/ <br>
<br>
Launch terminal and type:
```bash
sudo hydra -L usernames.txt -P wordlist.txt \
(IP) ssh
```
or
```bash
sudo hydra -l "username" -P wordlist.txt \
(IP) ssh
```
The differences between first command and the second command is that <br>
The first command uses a list of usernames defined by "-L" <br>
The second command uses a certain username and not a list <br>
Wordlist.txt is a list of passwords. You can create one or use rockyou.txt 
<br>
<br>
# <b> Offline </b>
For Offline method, you must download hashcat on Terminal. <br>
https://github.com/hashcat/hashcat <br>
<br>
Launch terminal and type: 
```bash
sudo hashcat -a (method) -m (method) -o crackedpasswords.txt \
hashes.txt wordlist.txt
```
-a = attack mode which are 5 <br>
-m = hash types <br>
-o crackedpasswords.txt = where the cracked passwords will be stored <br>
You can find more info in here: <br>
https://hashcat.net/wiki/ <br>
https://hashcat.net/wiki/doku.php?id=example_hashes <br>
# 
http-post-form = indicates the type of form (POST). <br>
/login-url = The login page URL. <br>
:username = The form field where the username is entered. <br>
^USER^ = tells Hydra to use the username. <br>
password = the form field where the password is entered. <br>
^PASS^ = tells Hydra to use the password list supplied earlier. <br>
Login = indicates to Hydra the Login failed message. <br>
Login failed = is the login failure mesasge that the form returns. <br>
F = F means Failure. If this word appears on the page, it's incorrent. <br>
-V = verbose output for every attempt. <br>
#
Thanks to NetworkChunk for the explain with his video: <br>
https://www.youtube.com/watch?v=z4_oqTZJqCo