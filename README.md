# unclutter-desktop-alexa-innovaccer

## This is a project for Hacker Camp 018 by Innovaccer.
Please find the problem statement [here](https://drive.google.com/file/d/1azvXBMhBmhiFRDDTR3cDegJUNTxvg3ak/view).
## Prerequisites
* All the scipts that I have created were tested successfully on **macOS** & other **Linux** based OSes with **Python 2.7.10** or **Python 3** installed on the system.*

## Features
* **Unclutter any directory from *desktop*, *documents*, *downloads*, *music*, *videos*, *pictures***   

It unclutters the selected directory by moving all the files on the directory with an extension e.g .jpg, .pdf etc. in a new folder named after the extension in the *Documents* folder. for e.g

*If user has 3 pdf, 10 mp3 and 4 jpg files on the desktop then 3 folders namely *PDFs*, *MP3s*, *JPGs* will be created in the documents folder and all the files will be moved in their respective folders.*
To unclutter desktop on your system run the script `unclutter.py`. e.g.
``` python unclutter.py ```
To unclutter any other directory from *Downloads*, *Documents*, *Music*, *Pictures* provide the directory name as a command line argument e.g. To unclutter downloads run
```  python unclutter.py downloads ``` .

* **List top n files on the system based on size.** 

To list top 10 files on your system by size, run the script *topFilesBy.py* for e.g.
``` python topFiles.py ```
To list n number of files on the system by size, provide n as a command line argument to the script *topFiles.py* for e.g 
*To see top 50 files by size on your system run*
``` python topFiles.py 50 ```

* **Your computers own history**.

Someone used your system and not sure what they accessed? Look at the most recently accessed files on your system by providing the command line argument 'lat' to the script *topFiles.py* e.g.
``` python topFiles.py lat```
By default it will return top 10 recently accessed files on the system, To view any number of files provide a command line argument n before 'lat' . e.g To view 50 most recently accessed files on your system run 
``` python topFiles.py 50 lat```
* **Recommended files to delete on the system**.

Often we'd like to free up some space onour system but are really unsure of what we might delete. To view the 10 most earliest in time accessed files on your system run the script 'topFiles.py' with the command line argument 'eat' i.e 
``` python topFiles.py eat ```
By default it will return 10 of the most earlier accessed files, to view n number of files provide n as a command line argument for e.g. *To view 50 most earlier accessed files on your system Run*
``` python topFiles.py 50 eat ```
List n most earliest accessed files on the system by providing the command line argument 'eat' which by default provides the top 10 files with earliest access times, Provide command line argument '50 eat' to list top 50 files with earlist access time. 
* **Voice controlled by Alexa.**

To add up on everything if too lazy to run any script on the system, I created an Alexa skill to setup a remote connection to any system using [Paramiko](http://www.paramiko.org/) a Python implementation of the SSHv2 protocol by running a AWS Lambda function and then execute commands on the remote system by giving instructions to your echo device like, 'Alexa, Unclutter my desktop', 'Alexa, list top files by size'. 
Please find the attached video for demo. 


Below infrastructure map shows how Alexa skill to execute commands using your echo device works.

<img src="https://github.com/mehuled/unclutter-desktop-alexa-innovaccer/blob/features/alexaworksFinal.png" width="910" height="364" />

**NOTE** : Since the Alexa skill is not published on the Alexa skill store, any other echo device might not understand the *Unclutter my desktop* or *List top files command*. However I have provided the code for the lambda function that is the endpoint for this skill in the file `alexaSkillOnLambda.py`.It will give an idea of how the skill actually works.

**Lambda Function ARN : arn:aws:lambda:us-east-1:372942179917:function:mehulsGirlfriendOnAlexa**
