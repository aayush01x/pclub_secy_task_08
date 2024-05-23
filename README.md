# pclub_secy_task_08
I was a complete beginner in the domain of web exploitation. So, to start off, I started learning about Burpsite and solved 10-15 NATAS.
After that I got some idea for flag 1, which was to access routes.txt. I added the gallery to scope in Burpsite and I use repeater to access /getFile?file=/home/kaptaan/PClub-DVWA/routes.txt
![image](https://github.com/aayush01x/pclub_secy_task_08/assets/153027947/8274c847-d9d3-4eb5-9d87-a7fdee98c42c)

![image](https://github.com/aayush01x/pclub_secy_task_08/assets/153027947/e23c901f-b14c-4f53-b5e8-85b1d868b165)

`Flag 1 : pclub{path_trav3rsa1_1s_fun}`

Part 2 was pretty easy as I found location where MAC address is located. MAC Address: 60:45:bd:af:3f:e5
https://stackoverflow.com/questions/1779715/how-to-get-mac-address-of-your-machine-using-a-c-program, again I used repeater.
`Flag 2: pclub{60:45:bd:af:3f:e5}`

Part 3 was kinda annoying. I think I although cheated my way though. I discovered you can perform command injection in ip address lookup page, although cd was disabled, dir worked.
`Flag 3: pclub{01d_1s_g01d_sql1}`
This enabled me to explore the directory, but I was not able to access file by cat, strings, grep  or anything else. Idk but fortunally running `strings *` worked in the folder which gave me the code inside python file.

The python file leaked passwords of users. Using passwords, I got into accounts of kaptaan(password was what was inside of md5), ritvik, aman. By this, I got link of pwn task, 1 flag, and an image of ARIITK.
![image](https://github.com/aayush01x/pclub_secy_task_08/assets/153027947/f5e4c909-c66b-42d9-8c85-4a07d09331b9)
![image](https://github.com/aayush01x/pclub_secy_task_08/assets/153027947/c5ee553b-a56b-4a24-a9d2-eadccd36c831)


I ran the image through steghide, which gave me a qr code. Scanning the QR code, gave a base64 encoded message, which on decrypting gave a ROT13 cipher, which on decrypting gave the flag.
`Flag 4: pclub{data_1s_3v3ryth1ng}`
