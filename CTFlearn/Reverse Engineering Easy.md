Reverse Engineering Easy

## Basic Android RE 1
### Given:
```
A simple APK, reverse engineer the logic, recreate the flag, and submit!
BasicAndroidRE1.apk - https://ctflearn.com/challenge/download/962
```
To solve this challenge, we first need to decompile the given apk using the following command:
```
apktool d BasicAndroidRE1.apk
```
This extracts all of the apk's files into a new directory ``` BasicAndroidRE1 ```

If you do not have ``` apktool ``` installed, you can use the following command to install into your linux environment.
```
sudo apt-get install apktool 
```


Next, we use ``` dex2jar ``` tool to create an executable JAR file that will be used to view the APK's source code.
Download the attached link if you need to install onto your linux machine: [dex2jar](https://sourceforge.net/projects/dex2jar/files/latest/download)
```
sh d2j-dex2jar.sh -f path/to/BasicAndroidRE1.apk
```
To view the source code, we need to use the ``` jd-gui ``` tool.
Now we can see packages and classes that is being used to build this application.

After viewing the MainActivity java file, we can see functions that are used to create the app as well as when the password is submitted.
From reading the code, it seems that an MD5 hash value is being compared to validate the correct password. 
Parts of the flag can also be read in the source code, but we need to crack the hash value to get the last output string.

### Output:
``` 
package com.example.secondapp;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
import org.apache.commons.codec.digest.DigestUtils;

public class MainActivity extends AppCompatActivity {
  protected void onCreate(Bundle paramBundle) {
    super.onCreate(paramBundle);
    setContentView(2131296284);
  }
  
  public void submitPassword(View paramView) {
    EditText editText = (EditText)findViewById(2131165239);
    if (DigestUtils.md5Hex(editText.getText().toString()).equalsIgnoreCase("b74dec4f39d35b6a2e6c48e637c8aedb")) {
      TextView textView = (TextView)findViewById(2131165322);
      StringBuilder stringBuilder = new StringBuilder();
      stringBuilder.append("Success! CTFlearn{");
      stringBuilder.append(editText.getText().toString());
      stringBuilder.append("_is_not_secure!}");
      textView.setText(stringBuilder.toString());
    } 
  }
}
```
Using a rainbow table found on https://md5hashing.net/hash/md5, I was able to crack this hash value:
### Input:
```
b74dec4f39d35b6a2e6c48e637c8aedb
```
### Output:
```
Spring2019
```
Finally, we can append this string output to the other parts of the flag to get the final flag.

```
### Flag:
``` 
CTFlearn{Spring2019_is_not_secure!}
```