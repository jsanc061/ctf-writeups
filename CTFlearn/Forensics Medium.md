Forensics Medium

## 07601
### Given:
```
https://mega.nz/#!CXYXBQAK!6eLJSXvAfGnemqWpNbLQtOHBvtkCzA7-zycVjhHPYQQ I think I lost my flag in there. Hopefully, it won't get attacked...
```
Link given downloads ``` AGT.png ``` 
Used binwalk to extract any hidden files
```
binwalk -D='.*' AGT.png
```
### Output:
``` 
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
9584          0x2570          Zip archive data, at least v1.0 to extract, name: Secret Stuff.../
9646          0x25AE          Zip archive data, at least v2.0 to extract, name: Secret Stuff.../.DS_Store
10270         0x281E          Zip archive data, at least v1.0 to extract, name: __MACOSX/
10325         0x2855          Zip archive data, at least v1.0 to extract, name: __MACOSX/Secret Stuff.../
10396         0x289C          Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../._.DS_Store
10546         0x2932          Zip archive data, at least v1.0 to extract, name: Secret Stuff.../Don't Open This.../
10627         0x2983          Zip archive data, at least v2.0 to extract, name: Secret Stuff.../Don't Open This.../.DS_Store
10988         0x2AEC          Zip archive data, at least v1.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../
11078         0x2B46          Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../._.DS_Store
11247         0x2BEF          Zip archive data, at least v2.0 to extract, name: Secret Stuff.../Don't Open This.../I Warned You.jpeg
150550        0x24C16         Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../._I Warned You.jpeg
151810        0x25102         End of Zip archive
151832        0x25118         Zip archive data, at least v1.0 to extract, name: Secret Stuff.../
151894        0x25156         Zip archive data, at least v2.0 to extract, name: Secret Stuff.../.DS_Store
152518        0x253C6         Zip archive data, at least v1.0 to extract, name: __MACOSX/
152573        0x253FD         Zip archive data, at least v1.0 to extract, name: __MACOSX/Secret Stuff.../
152644        0x25444         Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../._.DS_Store
152794        0x254DA         Zip archive data, at least v1.0 to extract, name: Secret Stuff.../Don't Open This.../
152875        0x2552B         Zip archive data, at least v2.0 to extract, name: Secret Stuff.../Don't Open This.../.DS_Store
153236        0x25694         Zip archive data, at least v1.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../
153326        0x256EE         Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../._.DS_Store
153495        0x25797         Zip archive data, at least v2.0 to extract, name: Secret Stuff.../Don't Open This.../I Warned You.jpeg
292768        0x477A0         Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../._I Warned You.jpeg
294028        0x47C8C         End of Zip archive
294050        0x47CA2         Zip archive data, at least v1.0 to extract, name: Secret Stuff.../
294112        0x47CE0         Zip archive data, at least v2.0 to extract, name: Secret Stuff.../.DS_Store
294736        0x47F50         Zip archive data, at least v1.0 to extract, name: Secret Stuff.../Don't Open This.../
294817        0x47FA1         Zip archive data, at least v2.0 to extract, name: Secret Stuff.../Don't Open This.../.DS_Store
295162        0x480FA         Zip archive data, at least v2.0 to extract, name: Secret Stuff.../Don't Open This.../I Warned You.jpeg
434433        0x6A101         Zip archive data, at least v1.0 to extract, name: __MACOSX/
434488        0x6A138         Zip archive data, at least v1.0 to extract, name: __MACOSX/Secret Stuff.../
434559        0x6A17F         Zip archive data, at least v1.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../
434649        0x6A1D9         Zip archive data, at least v2.0 to extract, name: __MACOSX/Secret Stuff.../Don't Open This.../._I Warned You.jpeg
435702        0x6A5F6         End of Zip archive
```

After viewing the extracted files, I changed the second file ``` 25102 ``` into a zip by adding the extension to the file. Then I used ``` unzip 25102.zip ``` to extract the zip folder which contained a Secret Folder that seemed suspicious. At the end of this Secret Folder directory held a JPEG file ``` I Warned You.jpeg ``` which I then ran the strings and grep commands to look for the flag.
```
strings 'I Warned You.jpeg' | grep "CTF"
```
### Output:
```
ABCTF{Du$t1nS_D0jo}1r
```
### Flag:
``` 
CTFlearn{Du$t1nS_D0jo}
```

## Git Is Good
### Given:
```
The flag used to be there. But then I redacted it. Good Luck. https://mega.nz/#!3CwDFZpJ!Jjr55hfJQJ5-jspnyrnVtqBkMHGJrd6Nn_QqM7iXEuc
```
The link downloaded a zip file ``` gitIsGood.zip ```
Using ``` unzip gitIsGood.zip ``` I extracted the files the zip folder had.
Change the directory to ``` gitIsGood ``` and list all of the files using 
```
ls -lah
``` 
### Output:
``` 
drwxrwxrwx 1 512 Aug 10 01:58 .
drwxrwxrwx 1 512 Aug 10 01:57 ..
drwxrwxrwx 1 512 Aug 10 01:57 .git
-rwxrwxrwx 1  15 Oct 30  2016 flag.txt
```
The ``` flag.txt ``` had a redacted version of the flag that needs to be figured out.
Navigating to the ``` .git ``` folder should have some more information.

To inspect the git logs use the command 
``` 
git log
```
### Output: 
```
commit d10f77c4e766705ab36c7f31dc47b0c5056666bb (HEAD -> master)
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:33:18 2016 -0400

    Edited files

commit 195dd65b9f5130d5f8a435c5995159d4d760741b
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:32:44 2016 -0400

    Edited files

commit 6e824db5ef3b0fa2eb2350f63a9f0fdd9cc7b0bf
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:32:11 2016 -0400

    edited files
(END)
```
This displays the the project's commits including the initial commit and two other commits.
Examining the second commit should show what has been changed from the initial commit.
```
git show 195dd65b9f5130d5f8a435c5995159d4d760741b
```
### Output:
```
commit 195dd65b9f5130d5f8a435c5995159d4d760741b
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:32:44 2016 -0400

    Edited files

diff --git a/flag.txt b/flag.txt
index c5250d0..8684e68 100644
--- a/flag.txt
+++ b/flag.txt
@@ -1 +1 @@
-flag{REDACTED}
+flag{protect_your_git}
(END)
```
### Flag:
``` 
CTFlearn{protect_your_git}
```

## Up For A Little Challenge?
### Given:
```
These numbers were scratched out on a prison wall. Can you help me decode them? https://mega.nz/#!al8iDSYB!s5olEDK5zZmYdx1LZU8s4CmYqnynvU_aOUvdQojJPJQ
```
The link downloads 'Begin Hack'.png

By using the ``` strings ``` command we can view some of the information held inside this file, notably the following strings:

### Output:
``` 
https://mega.nz/#!z8hACJbb!vQB569ptyQjNEoxIwHrUhwWu5WCj1JWmU-OFjf90Prg -N17hGnFBfJliykJxXu8
Mp real_unlock_key: Nothing Is As It SeemsU
password: Really? Again
flag{Not_So_Simple...}
```

Following the link found in the strings output, we are taken to another MEGA url download that produces the file ``` Up For A Little Challenge.zip ```
After extracting this zip and explore the folder, not much of the information found inside was useful.
However, when using binwalk to analyze the ``` Begin Hack.jpg ``` file reveals hidden files and directories inside of it.

```
binwalk -D='.*' Begin\ Hack.jpg
```
``` 
cd _Begin Hack.jpg.extracted
```
```
ls -la
```
### Output: 
```
total 176
drwxrwxrwx 1     512 Aug 10 02:47  .
drwxrwxrwx 1    512 Aug 10 02:42  ..
-rwxrwxrwx 1  21856 Aug 10 02:42  0
-rwxrwxrwx 1  21826 Aug 10 02:42  1E
drwxrwxrwx 1     512 Aug 10 02:58 'Did I Forget Again?'
-rwxrwxrwx 1  104853 Aug 10 02:47 'Up For A Little Challenge.zip'
drwxrwxrwx 1     512 Dec  1  2016  __MACOSX
```
Navigating to 'Did I Forget Again?' directory reveals two more files ``` .Processing.cerb4 ``` and ``` 'Loo Nothing Becomes Useless ack.jpg' ```
### Output:
```
total 288
drwxrwxrwx 1    512 Aug 10 02:58  .
drwxrwxrwx 1    512 Aug 10 02:47  ..
-rwxrwxrwx 1  32822 Nov 30  2016  .Processing.cerb4
-rwxrwxrwx 1  83736 Nov 30  2016 'Loo Nothing Becomes Useless ack.jpg'
```
Using the ``` file ``` command on the first file found reveals that it is an archived zip file.
```
file .Processing.cerb4
```
### Output: 
``` 
.Processing.cerb4: Zip archive data, at least v2.0 to extract
```
We can change the file to a zip by adding the ``` .zip ``` exentsion using the command:
```
cp .Processing.cerb4 .Processing.cerb4.zip
```
Now the zip folder can be extracted by using the command:
```
unzip .Processing.cerb4.zip
```
The user is prompted with a password while unzipping this folder so we'll try the password we found earlier in the strings output of the ``` 'Begin Hack'.jpg ``` file
```
real_unlock_key: Nothing Is As It Seems
``` 
Once the password is accepted, another file ``` skycoder.jpg ``` is extracted.
The final flag can be found by opening and viewing this JPG in a photo viewer.
The flag will be found in the bottom right section of this image in a small, red font.

### Flag:
``` 
CTFlearn{hack_complete}
```

## Milk's Best Friend
### Given:
```
There's nothing I love more than oreos, lions, and winning. https://mega.nz/#!DC5F2KgR!P8UotyST_6n2iW5BS1yYnum8KnU0-2Amw2nq3UoMq0Y Have Fun :)
```
The given link downloads a file named ``` oreo.jpg ```

To analyze this file, the following binwalk command was exectued:
```
binwalk -D='.*' oreo.jpg
```
### Output:
``` 
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
9515          0x252B          RAR archive data, first volume type: MAIN_HEAD
```
An archived RAR file was found to be hidden in this image but currently it has no file extension. By adding the ``` .rar ``` extension to the ``` 252B ``` file, we can format the file into a proper RAR archive by using the command:
``` 
cp 252B 252B.rar 
```
To extract this rar file, the following command can be used:
```
unrar e 252B.rar
```
This extracts two additional files ``` a ``` and ``` b.jpg ```
To locate the final flag, the ``` strings ``` command was used on ``` b.jpg ``` and the flag was found in the last line of the output
```
strings b.jpg
```
### Output:
```
Finally, flag{eat_more_oreos}
```
### Flag:
``` 
CTFlearn{eat_more_oreos}
```

## Digital Camouflage
### Given:
```
We need to gain access to some routers. Let's try and see if we can find the password in the captured network data: https://mega.nz/#!XDBDRAQD!4jRcJvAhMkaVaZCOT3z3zkyHre2KHfmkbCN5lYpiEoY Hint 1: It looks like someone logged in with their password earlier. Where would log in data be located in a network capture?<br /> Hint 2: If you think you found the flag, but it doesn't work, consider that the data may be encrypted.

Credit: picoCTF 2017
```
The link downloads a file named ``` data.pcap ```
Using Wireshark to examine this pcap file, right-click one of the HTTP or TCP frames, then ``` Follow -> TCPStream ```
The 3rd stream reveals an HTTP POST request with user credentials in the request header.
### Output:
``` 
POST /pages/main.html HTTP/1.1
Referer: 10.0.0.1:8080/index.html
User-Agent: User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:44.0) Gecko/20100101 Firefox/44.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9*/*;q=0.8
Host: 10.0.0.1:8080
Connection: Keep-Alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 43
Accept-Language: en-US,en;q=0.5

userid=hardawayn&pswrd=UEFwZHNqUlRhZQ%3D%3DHTTP/1.0 200 OK
Server: BaseHTTP/0.3 Python/2.7.9
Date: Sat, 19 Mar 2016 02:50:30 GMT
Content-type: text/html
```
### Credentials found
```
userid=hardawayn
&pswrd=UEFwZHNqUlRhZQ%3D%3D
```
The password seems to be encoded with base64 since the string ends with ``` %3D%3D ``` which is URL encoded to mean ``` == ```, a strong indication that it is base64 encoded.
After decoding this password string with base64, we get the string output that can be formatted into the final flag
```
PApdsjRTae
```
### Flag:
``` 
CTFlearn{PApdsjRTae}
```

## Dumpster
### Given:
```
I found a flag, but it was encrypted! Our systems have detected that someone has successfully decrypted this flag, and we stealthily took a heap dump of the program (in Java). Can you recover the flag for me? Here's the source code of the Java program and the heap dump: https://mega.nz/#!rHYGlAQT!48DlH2pSZg10Ei3f-Ivm7RoNBbV16Qw0wN4cWxANUwY
```
The link downloaded a file named ``` dumpster.zip ``` 
After extracting the files from the zip we get two additional files:
### Output:
``` 
Decryptor.java
heapdump.hprof
```

Using a text editor, we can inspect the java file that holds the encrypted flag.
We can modify the code, but we are missing the ``` passHash ``` byte values needed to decode the string so we'll look at the heap dump next for more information.

We can read the heapdump file using ``` VisualVM ```
Link provided if you need to install [VisualVM](https://visualvm.github.io/)

After loading the given file ``` heapdump.hprof ``` into VisualVM, we can use it to inspect the objects created by the java file. We are interested in anything password related so using ``` pass ``` found in the java code can be a lead to search with. The search result outputs an object named ``` Decryptor$Password ``` and upon further inspection reveals a field labeled ``` passHash ``` with the byte values displayed below.

![7c62a525caa6737b5c024c2446cef599.png](../_resources/e568b1e50b124534a308d83e39b5ed07.png)

Now we can use these byte values and add them into the java code along with some modifications to decrypt the flag.
### Source Code
```
import java.util.Base64;

import javax.crypto.Cipher;
import javax.crypto.spec.SecretKeySpec;

public class Decryptor
{
	public static final String FLAG = "S+kUZtaHEYpFpv2ixuTnqBdORNzsdVJrAxWznyOljEo=";
	
	private byte[] passHash;
	
	public byte[] encrypt(byte[] msg) throws Exception
	{
		SecretKeySpec spec = new SecretKeySpec(passHash, "AES");
		Cipher cipher = Cipher.getInstance("AES/ECB/PKCS5Padding");
		cipher.init(Cipher.ENCRYPT_MODE, spec);
		return cipher.doFinal(msg);
	}
	
	public static byte[] decrypt(byte[] msg, byte [] passHash) throws Exception
	{
		SecretKeySpec spec = new SecretKeySpec(passHash, "AES");
		Cipher cipher = Cipher.getInstance("AES/ECB/PKCS5Padding");
		cipher.init(Cipher.DECRYPT_MODE, spec);
		return cipher.doFinal(msg);
	}
	
	public static void main(String[] args) throws Exception
	{
		// Password pass = new Password(System.console().readPassword("Enter password to decrypt flag: "));
		// System.out.println(new String(pass.decrypt(Base64.getDecoder().decode(FLAG.getBytes()))));
		// Thread.sleep(5000); //We did a heap dump right here.

		byte [] passHash = {7,95,-34,16,-89,-86,73,108,-128,71,43,41,100,40,53,-24};
		System.out.println(new String(decrypt(Base64.getDecoder().decode(FLAG.getBytes()), passHash)));
	}
}
```
### Output:
```
stCTF{h34p_6ump5_r_c00l!11!!}
```
### Flag:
``` 
CTFlearn{h34p_6ump5_r_c00l!11!!}
```

## A CAPture of a Flag
### Given:
```
This isn't what I had in mind, when I asked someone to capture a flag... can you help? You should check out WireShark. https://mega.nz/#!3WhAWKwR!1T9cw2srN2CeOQWeuCm0ZVXgwk-E2v-TrPsZ4HUQ_f4
```
The link downloaded a file named ``` file (4) ```.
After inspection using the ``` file ``` command, we find the given file is a PCAP file so I added the proper extention onto a copied version of the file to create ``` flag.pcap ```

Using Wireshark, I inspected the HTTP frames by right-clicking frame 11 -> ``` Follow --> TCP Stream ```
On Stream 5, we find the following GET response:
```
GET /?msg=ZmxhZ3tBRmxhZ0luUENBUH0= HTTP/1.1
Host: www.hazzy.co.uk
Connection: keep-alive
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.78 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: en-GB,en;q=0.8
Cookie: language=en-gb; currency=USD
```

Using the ``` echo ``` and ``` base64 ``` commands on the ``` msg ``` string found in the GET response we can find the flag.

### Command:
```
echo 'ZmxhZ3tBRmxhZ0luUENBUH0=' | base64 -d
``` 
### Output:
``` 
flag{AFlagInPCAP}
```
### Flag:
``` 
CTFlearn{AFlagInPCAP}
```

## The adventures of Boris Ivanov. Part 1
### Given:
```
The KGB agent Boris Ivanov got information about an attempt to sell classified data. He quickly reacted and intercepted the correspondence. Help Boris understand what exactly they were trying to sell. Here is the interception data: https://mega.nz/#!HfAHmKQb!zg6EPqfwes1bBDCjx7-ZFR_0O0-GtGg2Mrn56l5LCkE
```
The link downloaded a file named ``` Boris_Ivanov_1.jpg ``` 

Using the website, https://github.com/zardus/ctf-tools/tree/master/stegsolve, I was able to find the flag using ``` Analyse -> Stereogram Solver ``` and kept increasing the image offset until frame 102 to get the flag output.

![06b28c302ccaf6fdd9a2cd2ffae15f0b.png](../_resources/5608c410d6b94797a6527ae5acc1a95e.png)
### Output:
``` 
flag{d0nt_m3s5_w1th_th3_KGB}
```
### Flag:
``` 
CTFlearn{d0nt_m3s5_w1th_th3_KGB}
```

