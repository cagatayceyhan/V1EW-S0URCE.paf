# Intro to Python Write Up

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/py1.PNG)

## What is the name of > 

**Cevap:Greater than**

## What is the name of !=

**Cevap:Not equal to**

## 1 != 0 will this return true or false (T or F)

**Cevap: T**

## What is the name of <=

**Cevap:Less than or equal to**

## Will this sample code return truee or false

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/py2.PNG)

**Cevap:truee** 

---------------

## What data type is 13 

**cevap: İnteger**

## What data type is "65"

**cevap: String**

## What data type is 62.193

**Cevap: Float**

--------------------

Well, you didn't think I would leave you without a challenge?

You'll find a file attached to this task called encoded_flag.txt. Within this file, you will find some encoded information! This is your challenge as follows;

Using the base64 library within python. Can you decode this and retrieve the flag? Note this has been encoded a total of 15 times. Be sure to read from the file provided and the documentation for the base64 library. This will allow you to discover the syntax to aid with this challenge!

from base64 import *


5 times encoded using base 64

5 times encoded using base 32

5 times encoded using base 16!

## Python kodu:
    import base64

    file = open("/home/kali/Desktop/encodedflag.txt","r")

    flag = file.read()

    code =""

    for i in range(0,5):
        code = base64.b16decode(flag)
        flag =code

    for i in range (0,5):
        code =base64.b32decode(flag)
        flag = code 

    for i in range(0,5):
        code = base64.b64decode(code)
        flag = code

    print(flag)

    file.close()


Cevap: 

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/py3.PNG)