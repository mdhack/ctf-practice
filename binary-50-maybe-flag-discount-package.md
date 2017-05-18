## Maybe Flag Discount

### Binary, 120pts

Flag: mdhc{h3x\_th4t\_l0rd\_ur\_7he\_b357}

##### How to h3x it:

So, they give us a broken zip file and a tracking number. Open the broken file in hexed.it. 

The broken zip file in hexed.it:![](/assets/Capture3.PNG)



As we learned, files have metadata, and that is where the tracking number goes. But where in the metadata? If you use the second link given in the discription, it give lots of info about the zip file. But we only want the metadata. So, crl +f and search for format, and we get a chart of the zip file format. 

The table:

![](/assets/Capture5.PNG)

We want to enter it into right after the file name. But when we enter it in there, we get: fix\__file\__signature. So, the tracking number is not the problem, the file signature is. The file signature tells the computer what type of file it is. So, there is a set file signature for all files. After a quick google search, we find that the file signature is 50 4B 03 04 for a pk zip file. So, for this file, after every 50 4B 00 00, we replace it with 50 4B 03 04. 

To change bytes, click on desired byte, and type in the new value:![](/assets/Capture4.PNG)

If you changed anything else, revert it to normal, otherwise, gg no re. Once you export the file, unzip it, and add .txt to the end of all the files within the zip file. Open the files, and you will see that all are encoded in hex. Pull out the hex to ascii tool, and convert evrything to asci, and file 4 should give you the flag!

Contents of file4:

mdhc{h3x\_th4t\_l0rd\_ur\_7he\_b357}³É¬\|&lt;öAá¥T=

«ÈØèqWÆ¤$\_« \]



More easy points!

"dwab on it"-KonTom 2k17



