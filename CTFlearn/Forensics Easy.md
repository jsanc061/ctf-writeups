Forensics Easy

## Forensics 101
Given this link https://mega.nz/#!OHohCbTa!wbg60PARf4u6E6juuvK9-aDRe_bgEL937VO01EImM7c

Downloads this file ``` 95f6edfb66ef42d774a5a34581f19052.jpg ```

Converted JPEG into TXT

Used nano to find the flag using ``` Ctrl + W ``` and then searching ``` flag ``` throughout the file

### Flag:
```
CTFlearn{wow!_data_is_cool}
```

### Alternate Solution (1):

Use the command 
``` 
grep -i --color -a "flag" 95f6edfb66ef42d774a5a34581f19052.txt 
```
### Output:
``` 
E�{}>�@n4�vk�39�AM;�"k��(+�Yc7X�8��d8OɄ��!"U�S���c�\ܺE��e&�eny���>��;W)O�iDl�����k�E���p(��*�+׿���`t&�KڹP@�Ny��/���(�flag{wow!_data_is_cool}�S�gYG
```

### Flag: 
``` 
CTFlearn{wow!_data_is_cool} 
```
### Alternate Solution (2):

Use the command 
``` 
strings 95f6edfb66ef42d774a5a34581f19052.jpg | grep "flag"
```
### Output:
``` 
flag{wow!_data_is_cool}
```

### Flag: 
``` 
CTFlearn{wow!_data_is_cool} 
```

## Taking LS
Given this link: https://mega.nz/#!mCgBjZgB!_FtmAm8s_mpsHr7KWv8GYUzhbThNn0I8cHMBi4fJQp8
The link downloaded ``` 'The Flag.zip' ```
Opened the archived zip using 7-Zip to find folder ``` The Flag ```
Browsed ``` The Flag ``` directory and opened ``` The Flag.pdf ```
This file was protected by a password so I need to keep digging around the archive
Opened ``` .ThePassword ``` in ``` The Flag ``` directory which contained ``` ThePassword.txt ```
Opened this file to view: 
```
Nice Job!  The Password is "Im The Flag". 
```
Used the password on ``` TheFlag.pdf ``` which displayed: 
```
Here is the Flag: ABCTF{T3Rm1n4l_is_C00l} 
```

### Flag: ``` CTFlearn{T3Rm1n4l_is_C00l} ```

## Binwalk
Given this link: https://mega.nz/#!qbpUTYiK!-deNdQJxsQS8bTSMxeUOtpEclCI-zpK7tbJiKV0tXYY
Downloaded ``` PurpleThing .jpeg ``` 

Tried the command ``` binwalk -Me PurpleThing.jpeg ``` to recursively extract the files, but led to extracting a seemingly endless loop of folders such as 0.zlib
Tried to extract the zlib files using 7z and gzip, did not work

Used Cyberchef to extract the images files and found ``` extracted_at_0x25795.png ``` 
Opened up this image to find the flag 
### Flag: 
``` 
CTFlearn{b1nw4lk_is_us3ful}
```
### *Alternate Solution*
Use binwalk command to extract all the files 
``` 
binwalk -D='.*' PurpleThing.jpeg
```
Navigated the extracted files and converted them all into PNG by adding the proper file extension
File 25795.png revealed the flag 
Flag:
```
ABCTF{b1nw4lk_is_us3ful}
```

## WOW .... So Meta
### Given:
```
This photo was taken by our target. See what you can find out about him from it. https://mega.nz/#!ifA2QAwQ!WF-S-MtWHugj8lx1QanGG7V91R-S1ng7dDRSV25iFbk
```
### Output:
``` 
3UWLBAUCb9Z2.jpg 
```

Examined the file using exiftool command to extract all metadata to find the flag
``` 
exiftool 3UWLBAUCb9Z2.jpg 
``` 
### Output:
``` 
ExifTool Version Number         : 10.80
File Name                       : 3UWLBAUCb9Z2.jpg
Directory                       : .
File Size                       : 101 kB
File Modification Date/Time     : 2020:08:05 23:01:46-05:00
File Access Date/Time           : 2020:08:05 23:05:03-05:00
File Inode Change Date/Time     : 2020:08:05 23:02:10-05:00
File Permissions                : rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Current IPTC Digest             : dbad0204d16a63027791298bc460859a
Coded Character Set             : UTF8
Application Record Version      : 2
Digital Creation Time           : 16:45:55
Digital Creation Date           : 2014:12:27
Time Created                    : 16:45:55
IPTC Digest                     : dbad0204d16a63027791298bc460859a
Exif Byte Order                 : Big-endian (Motorola, MM)
Orientation                     : Horizontal (normal)
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Software                        : Photos 1.5
Modify Date                     : 2014:12:27 16:45:55
Exif Version                    : 0221
Date/Time Original              : 2014:12:27 16:45:55
Create Date                     : 2014:12:27 16:45:55
Components Configuration        : Y, Cb, Cr, -
Light Source                    : Tungsten (Incandescent)
Flashpix Version                : 0100
Color Space                     : sRGB
Exif Image Width                : 4002
Exif Image Height               : 1536
Scene Capture Type              : Standard
Sharpness                       : Hard
Padding                         : (Binary data 2060 bytes, use -b option to extract)
XMP Toolkit                     : XMP Core 5.4.0
Creator Tool                    : Photos 1.5
Date Created                    : 2014:12:27 16:45:55
Warning                         : [minor] Fixed incorrect URI for xmlns:MicrosoftPhoto
Camera Serial Number            : flag{EEe_x_I_FFf}
Image Width                     : 800
Image Height                    : 307
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Date/Time Created               : 2014:12:27 16:45:55
Digital Creation Date/Time      : 2014:12:27 16:45:55
Image Size                      : 800x307
Megapixels                      : 0.246
```
### Flag:
``` 
CTFlearn{EEe_x_I_FFf}
```

## Rubber Duck
### Given:
```
Find the flag! Simple forensics challenge to get started with.
RubberDuck.jpg
```

Used the following command to extract metadata from the image:
```
exiftool RubberDuck.jpg
```
### Output:
``` 
ExifTool Version Number         : 10.80
File Name                       : RubberDuck.jpg
Directory                       : .
File Size                       : 192 kB
File Modification Date/Time     : 2020:08:05 23:52:28-05:00
File Access Date/Time           : 2020:08:05 23:53:00-05:00
File Inode Change Date/Time     : 2020:08:05 23:52:43-05:00
File Permissions                : rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 72
Y Resolution                    : 72
Comment                         : CTFlearn{ILoveJakarta}.
Profile CMM Type                : Apple Computer Inc.
Profile Version                 : 4.0.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 2017:07:07 13:22:32
Profile File Signature          : acsp
Primary Platform                : Apple Computer Inc.
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             : Apple Computer Inc.
Device Model                    :
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Perceptual
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Apple Computer Inc.
Profile ID                      : ca1a9582257f104d389913d5d1ea1582
Profile Description             : Display P3
Profile Copyright               : Copyright Apple Inc., 2017
Media White Point               : 0.95045 1 1.08905
Red Matrix Column               : 0.51512 0.2412 -0.00105
Green Matrix Column             : 0.29198 0.69225 0.04189
Blue Matrix Column              : 0.1571 0.06657 0.78407
Red Tone Reproduction Curve     : (Binary data 32 bytes, use -b option to extract)
Chromatic Adaptation            : 1.04788 0.02292 -0.0502 0.02959 0.99048 -0.01706 -0.00923 0.01508 0.75168
Blue Tone Reproduction Curve    : (Binary data 32 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 32 bytes, use -b option to extract)
Image Width                     : 1536
Image Height                    : 2048
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 1536x2048
Megapixels                      : 3.1
```
### Flag:
``` 
CTFlearn{ILoveJakarta}
```

## Snowboard
### Given:
```
Find the flag in the jpeg file. Good Luck!
Snowboard.jpg
```

Used the following command to extract metadata from the image:
```
exiftool Snowboard.jpg
```
### Output:
``` 
ExifTool Version Number         : 10.80
File Name                       : Snowboard.jpg
Directory                       : .
File Size                       : 103 kB
File Modification Date/Time     : 2020:08:05 23:55:00-05:00
File Access Date/Time           : 2020:08:05 23:55:50-05:00
File Inode Change Date/Time     : 2020:08:05 23:55:40-05:00
File Permissions                : rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Comment                         : CTFlearn{CTFIsEasy!!!}.
Exif Byte Order                 : Little-endian (Intel, II)
Make                            : Canon
Camera Model Name               : Canon EOS 6D Mark II
X Resolution                    : 300
Y Resolution                    : 300
Resolution Unit                 : inches
Software                        : GIMP 2.10.6
Modify Date                     : 2019:05:07 14:37:21
Exposure Time                   : 1/1250
F Number                        : 4.0
Exposure Program                : Manual
ISO                             : 100
Sensitivity Type                : Recommended Exposure Index
Recommended Exposure Index      : 100
Exif Version                    : 0230
Date/Time Original              : 2018:08:23 12:52:08
Create Date                     : 2018:08:23 12:52:08
Shutter Speed Value             : 1/1250
Aperture Value                  : 4.0
Exposure Compensation           : 0
Max Aperture Value              : 4.0
Metering Mode                   : Multi-segment
Flash                           : Off, Did not fire
Focal Length                    : 88.0 mm
Sub Sec Time Original           : 75
Sub Sec Time Digitized          : 75
Focal Plane X Resolution        : 6673.796791
Focal Plane Y Resolution        : 6720.516963
Focal Plane Resolution Unit     : inches
Custom Rendered                 : Normal
Exposure Mode                   : Manual
White Balance                   : Auto
Scene Capture Type              : Standard
Serial Number                   : 082051002328
Lens Info                       : 24-105mm f/?
Lens Model                      : EF24-105mm f/4L IS USM
Lens Serial Number              : 0000502af2
Compression                     : JPEG (old-style)
Photometric Interpretation      : YCbCr
Samples Per Pixel               : 3
Thumbnail Offset                : 932
Thumbnail Length                : 8284
XMP Toolkit                     : XMP Core 4.4.0-Exiv2
Document ID                     : xmp.did:5745BC0FB0ABE811B17E9DE2D509CE38
Instance ID                     : xmp.iid:2a75c26f-74d2-4550-bdf1-6260a95890e8
Original Document ID            : EE719D915149C0C012BA4285EC4D4875
Api                             : 2.0
Platform                        : Windows
Time Stamp                      : 1557232658413988
Approximate Focus Distance      : 11.9
Firmware                        : 1.0.3
Flash Compensation              : 0
Image Number                    : 0
Lens                            : EF24-105mm f/4L IS USM
Already Applied                 : True
Auto Lateral CA                 : 0
Blacks 2012                     : -10
Blue Hue                        : 0
Blue Saturation                 : 0
Brightness                      : 0
Camera Profile                  : Embedded
Clarity                         : 0
Clarity 2012                    : +21
Color Noise Reduction           : 0
Contrast                        : 0
Contrast 2012                   : +5
Convert To Grayscale            : False
Crop Angle                      : 0
Crop Bottom                     : 1
Crop Constrain To Warp          : 0
Crop Height                     : 3872
Crop Left                       : 0.069159
Crop Right                      : 1
Crop Top                        : 0.069159
Crop Unit                       : pixels
Crop Width                      : 5808
Defringe                        : 0
Exposure                        : 0.00
Exposure 2012                   : +0.10
Fill Light                      : 0
Grain Amount                    : 0
Green Hue                       : 0
Green Saturation                : 0
Has Crop                        : True
Has Settings                    : True
Highlight Recovery              : 0
Highlights 2012                 : -21
Hue Adjustment Aqua             : 0
Hue Adjustment Blue             : 0
Hue Adjustment Green            : 0
Hue Adjustment Magenta          : 0
Hue Adjustment Orange           : 0
Hue Adjustment Purple           : 0
Hue Adjustment Red              : 0
Hue Adjustment Yellow           : 0
Incremental Temperature         : 0
Incremental Tint                : 0
Lens Manual Distortion Amount   : 0
Lens Profile Enable             : 0
Lens Profile Setup              : LensDefaults
Luminance Adjustment Aqua       : 0
Luminance Adjustment Blue       : 0
Luminance Adjustment Green      : 0
Luminance Adjustment Magenta    : 0
Luminance Adjustment Orange     : 0
Luminance Adjustment Purple     : 0
Luminance Adjustment Red        : 0
Luminance Adjustment Yellow     : 0
Luminance Smoothing             : 0
Parametric Darks                : 0
Parametric Highlight Split      : 75
Parametric Highlights           : 0
Parametric Lights               : 0
Parametric Midtone Split        : 50
Parametric Shadow Split         : 25
Parametric Shadows              : 0
Perspective Horizontal          : 0
Perspective Rotate              : 0.0
Perspective Scale               : 100
Perspective Vertical            : 0
Post Crop Vignette Amount       : 0
Process Version                 : 6.7
Red Hue                         : 0
Red Saturation                  : 0
Saturation                      : +5
Saturation Adjustment Aqua      : 0
Saturation Adjustment Blue      : 0
Saturation Adjustment Green     : 0
Saturation Adjustment Magenta   : 0
Saturation Adjustment Orange    : 0
Saturation Adjustment Purple    : 0
Saturation Adjustment Red       : 0
Saturation Adjustment Yellow    : 0
Shadow Tint                     : 0
Shadows                         : 0
Shadows 2012                    : +66
Sharpen Detail                  : 25
Sharpen Edge Masking            : 0
Sharpen Radius                  : +1.0
Sharpness                       : 0
Split Toning Balance            : 0
Split Toning Highlight Hue      : 0
Split Toning Highlight Saturation: 0
Split Toning Shadow Hue         : 0
Split Toning Shadow Saturation  : 0
Tone Curve                      : 0, 0, 255, 255
Tone Curve Blue                 : 0, 0, 255, 255
Tone Curve Green                : 0, 0, 255, 255
Tone Curve Name                 : Linear
Tone Curve Name 2012            : Linear
Tone Curve PV2012               : 0, 0, 255, 255
Tone Curve PV2012 Blue          : 0, 0, 255, 255
Tone Curve PV2012 Green         : 0, 0, 255, 255
Tone Curve PV2012 Red           : 0, 0, 255, 255
Tone Curve Red                  : 0, 0, 255, 255
Version                         : 7.0
Vibrance                        : +15
Vignette Amount                 : 0
Whites 2012                     : 0
Format                          : image/jpeg
Creator Tool                    : GIMP 2.10
Metadata Date                   : 2018:08:29 14:22:51-03:00
Location Created                :
Location Shown                  :
Artwork Or Object               :
Registry ID                     :
History Action                  : derived, saved, saved
History Parameters              : saved to new location
History Changed                 : /, /
History Instance ID             : xmp.iid:5745BC0FB0ABE811B17E9DE2D509CE38, xmp.iid:6047bbb2-fd56-4c4c-bc52-1b0854f657ac
History Software Agent          : Adobe Photoshop Lightroom 4.0 (Windows), Gimp 2.10 (Windows)
History When                    : 2018:08:29 14:22:51-03:00, 2019:05:07 14:37:38
Derived From Document ID        : EE719D915149C0C012BA4285EC4D4875
Derived From Original Document ID: EE719D915149C0C012BA4285EC4D4875
Image Supplier                  :
Image Creator                   :
Copyright Owner                 :
Licensor                        :
Current IPTC Digest             : 6cd3ab5fbec9aa23bd736996a08e8c96
Coded Character Set             : UTF8
Date Created                    : 2019:05:07
Digital Creation Date           : 2018:08:23
Digital Creation Time           : 12:52:08+00:00
Application Record Version      : 4
Time Created                    : 14:37:21-14:37
Image Width                     : 1200
Image Height                    : 800
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:4 (1 1)
Aperture                        : 4.0
Date/Time Created               : 2019:05:07 14:37:21-14:37
Digital Creation Date/Time      : 2018:08:23 12:52:08+00:00
Image Size                      : 1200x800
Megapixels                      : 0.960
Scale Factor To 35 mm Equivalent: 1.5
Shutter Speed                   : 1/1250
Create Date                     : 2018:08:23 12:52:08.75
Date/Time Original              : 2018:08:23 12:52:08.75
Thumbnail Image                 : (Binary data 8284 bytes, use -b option to extract)
Circle Of Confusion             : 0.020 mm
Field Of View                   : 15.3 deg
Focal Length                    : 88.0 mm (35 mm equivalent: 133.7 mm)
Hyperfocal Distance             : 97.88 m
Lens ID                         : Canon EF 24-105mm f/4L IS USM
Light Value                     : 14.3
```

Found a flag but it did not work...
```
CTFlearn{CTFIsEasy!!!}
```

Used Binwalk this time to examine this file
```
binwalk -D='.*' Snowboard
```
Then ran binwalk again on these new files to find out which were JPEG files
```
binwalk *
```
### Output:
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
90            0x5A            TIFF image data, little-endian offset of first image directory: 8
932           0x3A4           JPEG image data, JFIF standard 1.01
9397          0x24B5          Unix path: /www.w3.org/1999/02/22-rdf-syntax-ns#"> <rdf:Description rdf:about="" xmlns:iptcExt="http://iptc.org/std/Iptc4xmpExt/2008-02-29/
14651         0x393B          Copyright string: "CopyrightOwner> <rdf:Seq/> </plus:CopyrightOwner> <plus:Licensor> <rdf:Seq/> </plus:Licensor> </rdf:Description> </rdf:RDF> </x:"
14685         0x395D          Copyright string: "CopyrightOwner> <plus:Licensor> <rdf:Seq/> </plus:Licensor> </rdf:Description> </rdf:RDF> </x:xmpmeta>  "
```

Used the following command to search for the flag in the first JPEG file
```
strings -n 8 0
```
### Output:
```
CTFlearn{CTFIsEasy!!!}
Q1RGbGVhcm57U2tpQmFuZmZ9Cg==
Canon EOS 6D Mark II
GIMP 2.10.6  
...
```
Decoded string found below this pseudo-flag as it stuck out as a Base-64 encoded string
### Output:
```
CTFlearn{SkiBanff}
```
### Flag:
``` 
CTFlearn{SkiBanff}
```

## PikesPeak
### Given:
```
Pay attention to those strings!
PikesPeak.jpg
```

Used the following command to examine the file:
```
file PikesPeak.jpg
```
### Output:
``` 
PikesPeak.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, comment: "CTFLEARN{PikesPeak}", comment: "CTFLearn{Colorado}", comment: "ctflearn{MountainMountainMountain}", comment: "cTfLeArN{CTFMountainCTFmOUNTAIN}", comment: "CTF{AsPEN.Vail}", comment: "CTFlearn{Gandalf}", comment: "ctflearning{AUCKLAND}", comment: "ctfLEARN{MtDoom}", comment: "ctflearninglearning{Mordor.TongariroAlpineCrossing}", comment: "CTFLEARN{MountGedePangrangoNationalPark}", comment: "ctflearncTfLeARN{MountKosciuszko}", progressive, precision 8, 680x510, frames 3
```

Added grep to the command to narrow down the flag
```
file PikesPeak.jpg | grep 'CTFlearn'
```
### Output:
``` 
CTFlearn{Gandalf}
```
### Flag:
``` 
CTFlearn{Gandalf}
```

## GandalfTheWise
### Given:
```
Extract the flag from the Gandalf.jpg file. You may need to write a quick script to solve this.
Gandalf.jpg
```

Used the following command to examine the file:
```
file Gandalf.jpg
```
### Output:
``` 
Gandalf.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, comment: "Q1RGbGVhcm57eG9yX2lzX3lvdXJfZnJpZW5kfQo=", comment: "xD6kfO2UrE5SnLQ6WgESK4kvD/Y/rDJPXNU45k/p", comment: "h2riEIj13iAp29VUPmB+TadtZppdw3AuO7JRiDyU", baseline, precision 8, 225x225, frames 3
```
Tried decoding the first comment as base64 and found a flag hint
### Input
```
Q1RGbGVhcm57eG9yX2lzX3lvdXJfZnJpZW5kfQo=
```
### Output
```
CTFlearn{xor_is_your_friend}
```

I found two additional comments using the ``` strings ``` command:
```
strings Gandalf.jpg
```

### Output:
```
JFIF
+Q1RGbGVhcm57eG9yX2lzX3lvdXJfZnJpZW5kfQo=
+xD6kfO2UrE5SnLQ6WgESK4kvD/Y/rDJPXNU45k/p
+h2riEIj13iAp29VUPmB+TadtZppdw3AuO7JRiDyU
```

Then I decoded the other two comment strings and placed their output into individual files:
```
echo 'xD6kfO2UrE5SnLQ6WgESK4kvD/Y/rDJPXNU45k/p' | base64 -d > outfile1.txt
echo 'h2riEIj13iAp29VUPmB+TadtZppdw3AuO7JRiDyU' | base64 -d > outfile2.txt
```

From here, I was able to view the outfile's hex information to read the raw byte output using the following commands:
### Input:
```
xxd outfile1.txt
```
### Output:
```
00000000: c43e a47c ed94 ac4e 529c b43a 5a01 122b  .>.|...NR..:Z..+
00000010: 892f 0ff6 3fac 324f 5cd5 38e6 4fe9       ./..?.2O\.8.O.
```

### Input:
```
xxd outfile2.txt
```
### Output:
```
00000000: 876a e210 88f5 de20 29db d554 3e60 7e4d  .j..... )..T>`~M
00000010: a76d 669a 5dc3 702e 3bb2 5188 3c94       .mf.].p.;.Q.<.
```

After grabbing the two hex values from each output file, we can now use the xor operation to find the final flag. To perform this calculation, I used the following website, http://www.xor.pw/ and placed each hex string into the inputs as hexadecimal base 16 to produce the flag in a hex string.
```
c43e a47c ed94 ac4e 529c b43a 5a01 122b 892f 0ff6 3fac 324f 5cd5 38e6 4fe9
876a e210 88f5 de20 29db d554 3e60 7e4d a76d 669a 5dc3 702e 3bb2 5188 3c94
```
### Output:
```
4354466c6561726e7b47616e64616c662e42696c626f42616767696e737d
```
Finally, converting the string from hex to ascii text we see the final flag.
### Flag:
``` 
CTFlearn{Gandalf.BilboBaggins}
```

## Tux!
### Given:
```
The flag is hidden inside the Penguin! Solve this challenge before solving my 100 point Scope challenge which uses similar techniques as this one.
Tux.jpg - https://ctflearn.com/challenge/download/973 

Used the ``` file ``` command on the given file
```
### Output:
``` 
973: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, comment: "ICAgICAgUGFzc3dvcmQ6IExpbnV4MTIzNDUK", baseline, precision 8, 196x216, frames 3
```

Converted the comment string from base64 found in the output
### Output: 
```
Password: Linux12345
```
Next, use the binwalk command to extract all files including the hidden ones
```
binwalk -D='.*' 973
```
### Output:
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
5488          0x1570          Zip archive data, encrypted at least v1.0 to extract, compressed size: 39, uncompressed size: 27, name: flag
5679          0x162F          End of Zip archive
```

A file ``` 1570 ``` is found within the JPEG image that contains a description that it might be a zip folder. Next, we change the to the directory that holds the extracted files and then convert the file by adding the .zip extension using 
```
cp 1570 1570.zip
```
Now the information in the zip file can be extracted by using
```
unzip 1570.zip
```

This prompts a password in order for the files to be extraced which we already found earlier in the file's comments section, ``` Password: Linux12345 ```
Once the password is entered, a ``` flag ``` file is extracted. 
Using the command ``` cat flag ``` outputs the final flag for this challenge.

### Flag:
``` 
CTFlearn{Linux_Is_Awesome}
```

## Chalkboard
### Given:
```
Solve the equations embedded in the jpeg to find the flag. Solve this problem before solving my Scope challenge which is worth 100 points.
math.jpg - https://ctflearn.com/challenge/download/972
```

Used ``` exiftool ``` on the JPEG file given
### Output:
``` 
ExifTool Version Number         : 10.80
File Name                       : 972
Directory                       : .
File Size                       : 187 kB
File Modification Date/Time     : 2020:07:20 23:39:17-05:00
File Access Date/Time           : 2020:08:09 23:46:18-05:00
File Inode Change Date/Time     : 2020:08:09 23:45:44-05:00
File Permissions                : rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Comment                         : The flag for this challenge is of the form:..CTFlearn{I_Like_Math_x_y}..where x and y are the solution to these equations:..3x + 5y = 31..7x + 9y = 59...
Image Width                     : 640
Image Height                    : 316
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:4 (1 1)
Image Size                      : 640x316
Megapixels                      : 0.202
```

To solve the next part, I wrote a small python program to solve the systems of equations given for x and y.
### Source Code
```
import numpy as py

# Solve for x and y 
# 3x + 5y = 31
# 7x + 9y = 59

A = py.array([[3, 5], [7, 9]])
B = py.array([31, 59])
ans = py.linalg.solve(A,B)
print(ans)  # [2, 5] => x=2, y=5
```
After solving for x and y, replace the found values into the flag found earlier from the comments section.
### Flag:
``` 
CTFlearn{I_Like_Math_2_5}
```

## Exif
### Given:
```
If only the password were in the image?

https://mega.nz/#!SDpF0aYC!fkkhBJuBBtBKGsLTDiF2NuLihP2WRd97Iynd3PhWqRw You could really ‘own’ it with exif.
```
The link downloaded a file named ``` Computer-Password-Security-Hacker - Copy.jpg ```

Used the following command to find the flag in the metadata of this image:
``` 
exiftool Computer-Password-Security-Hacker\ -\ Copy.jpg 
```
### Output:
``` 
Owner Name : flag{3l1t3_3x1f_4uth0r1ty_dud3br0}
```
### Flag:
``` 
CTFlearn{3l1t3_3x1f_4uth0r1ty_dud3br0}
```

## Pho Is Tasty!
### Given:
```
The flag is hidden in the jpeg file. Good Luck! Have some Pho! Solve this challenge before solving my Scope challenge for 100 points.
Pho.jpg - https://ctflearn.com/challenge/download/971
```
Used the following command to view the hex dump of this image to find the flag:
```
xxd Pho.jpg
```
### Output:
``` 
00000000: ffd8 ffe0 0010 4a46 4946 0001 0100 0001  ......JFIF......
00000010: 0001 0000 ffe3 006f 5361 6d73 756e 6700  .......oSamsung.
00000020: 5361 6d73 756e 6720 4761 6c61 7879 2053  Samsung Galaxy S
00000030: 3820 436f 6c6f 7220 5061 6c65 7474 653a  8 Color Palette:
00000040: 1d09 4304 1554 0206 4614 0d6c 160e 6506  ..C..T..F..l..e.
00000050: 1961 171f 721b 186e 010c 7b04 0749 0f03  .a..r..n..{..I..
00000060: 5f02 0e4c 1618 6f1f 0476 190c 651f 065f  _..L..o..v..e.._
00000070: 1801 5011 1068 1314 6f1a 0221 0402 2113  ..P..h..o..!..!.
00000080: 1421 0b14 7dff db00 8400 0808 0808 0808  .!..}...........
```
### Flag:
``` 
CTFlearn{I_Love_Pho!!!}
```


