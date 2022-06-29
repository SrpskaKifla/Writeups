<h1><b>VUCIC WRITEUP</b></h1> </br>
This room covers cracking zip files, steganography and simple decoding. It's a pretty easy box. First let's download the zip file!
<br>
When we try to unzip it we can see that it requires a password.
<br>
So let's run <b>FCRACKZIP</b> tool to crack it. But you can use something like <b>John</b> or <b>HashCat</b> too.
<hr>
We re going to use <b><i>fcrackzip -u -D -p ~/Hacking/wordlists/rockyou.txt Medicine.zip</i></b> <br>
<i>Note: </i> My wordlist is located in my "Hacking" directory in my home. Your is probably in <b>/usr/share/wordlists/</b>
<hr>

![unknown](https://user-images.githubusercontent.com/93349641/176450450-1ecd0143-8d18-4443-a31b-3806c2e0bb0b.png)
<hr>
Great! Now, when we unzip it we can see that we got an image!
<br><br>

![dio](https://user-images.githubusercontent.com/93349641/176451171-8d3545b3-3633-48da-a05e-37ed6d012936.jpg)

<br>
This is creepiest image i saw in a while... But we must continue!
<br>

Looks like it's a jpg, so let's try to see if something is there using <b>Steghide</b> tool.
<hr>

![unknown](https://user-images.githubusercontent.com/93349641/176452751-7795d44c-8dba-4449-9036-b47e5272486f.png)
	
<hr>
Looks like we might need to find a password for that.
Let's try to find something using <b>Strings</b> command
<hr>

![image](https://user-images.githubusercontent.com/93349641/176453344-8dd582f7-f425-484c-85bf-cbf69e3f88de.png)

<hr>
Looks like we got a message that says "Try harder". So let's try harder! <br>
Next, let's see if we can find something using <b>Exiftool</b>
<hr>

![image](https://user-images.githubusercontent.com/93349641/176454159-2ebeffab-4716-4b4b-bca3-328090b67844.png)

<hr>
Looks like we need to bruteforce it! <br>
Let's use <b>Stegseek</b> tool for this! <br>
<i>Note: </i> You can use <b>Stegcracker</b> too, but it's much slower than stegseek
<hr>

![image](https://user-images.githubusercontent.com/93349641/176460014-2defe94d-e4a6-4ed1-aadf-85b3e2be61ee.png)

<hr>
Now that we have a password let's use <b>Steghide</b> again to extract files! <br>
We got a "medicine.txt"! Let's see what's in there.
<hr>

![image](https://user-images.githubusercontent.com/93349641/176462698-a94782d4-042c-4eb8-995c-6a298543d2bc.png)

<hr>
It looks like it's base32 encoded.
<hr>

![image](https://user-images.githubusercontent.com/93349641/176463898-b23e26d5-f2eb-4797-a201-bfc2cc4032a6.png)
<hr>
It looks like it's base64 encoded now.
<hr>

![image](https://user-images.githubusercontent.com/93349641/176464636-0bf40e6c-3de0-48f3-bbb7-fab947818da8.png)
<hr>
And there is the flag!!!
It was a pretty easy box, hope you enjoyed it!
