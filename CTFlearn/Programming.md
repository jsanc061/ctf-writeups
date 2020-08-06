Programming

## Simple Programming
### Given:
```
Can you help me? I need to know how many lines there are where the number of 0's is a multiple of 3 or the numbers of 1s is a multiple of 2. Please! Here is the file: https://mega.nz/#!7aoVEKhK!BAohJ0tfnP7bISIkbADK3qe1yNEkzjHXLKoJoKmqLys
```
The link downloaded ``` data.dat ``` which had binary data on each line
Using Python3, I created a small script to read each line and create a counter for each of the zeros and ones. If the number of zeroes were a multiple of 3, then I increased the counter. If the number of ones were a multiple of 2, then I increased the counter. At the end of the program, the counter resulted in 6662.

#### Source Code - Using Python3
``` 
file = open('data.dat')
try:
	count = 0
    print('file opened')
    l = file.readlines()
    print('reading file lines ')
    for line in l:
        zero = line.count('0') # counts number of zeros in each line
        one = line.count('1')  # counts number of ones in each line
        if(zero % 3== 0 or one % 2 == 0):
            count += 1
finally:
    print('Number of lines: ' + str(count))
    file.close()
    print('closing file... ')
```
### Output: 
```
file opened
reading file lines
Number of lines: 6662
closing file...
```
### Flag:
``` 
CTFlearn{6662}
```