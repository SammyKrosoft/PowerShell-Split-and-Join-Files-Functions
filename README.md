# Split / Join file functions

There are 2 functions in this sample. You can either dot source the Split/Join ps1, or copy/paste the Split/Join functions into your own scripts.
The Split function will split a file into chunks of a specified size. The Join function will join the chunks back into the original file.

Utilization example:

## Split file

I have a 20MB fichier in my C:\temp directory that I want to split into 2MB chunks:

![Alt text](media/image.png)

I will run the below (you need the Split function to be either loaded from dotsourcing or copied/pasted in your script):

```powershell
Split -Path "C:\Temp\MonFichier.Zip" -ChunkSize 2MB
```

The result will be 10 files in the same directory:

![Alt text](media/image-1.png)

## Join file

To join file back, you need to specity the initial file name (like ```MonFichier.zip```), and the file will be joined in the same directory as the splitted files (FileName.<extention>.<Number>.part).

> Note: the splitted files can be copied in any directory, just make sure to specify the path to the original name of the file.

```powershell
Join -Path c:\temp2\MonFichier.zip
```

And you will retrieve the join file in the same directory (first file in the below screenshot, also note the ```c:\temp2``` directory):

![Alt text](media/image-2.png)