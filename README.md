# vitalsource_downloader
Simple script to download Vitalsource book

# Usage

This script downloads images from an online book resource in the JPEG format.
To use the script, set the ISBN number of the book in the script. The script
downloads each image by sending an HTTP GET request and saving the response in a
JPEG file. The user can specify the start and end page numbers as command line
arguments.

# How to use
To use the script, follow these steps:

1. Open the script in a text editor.
2. Set the ISBN number of the book in the script (line 5).
3. Copy the cookie from browser and add to the script - Firefox - Developer Tools -> Network Tab -> Look for https://jigsaw.vitalsource.com/books/ url -> Right click on the url -> Copy Value -> Copy Request Headers
4. Open a terminal and navigate to the directory where the script is saved.
5. Type chmod +x vitalsource.sh to make the script executable.
6. Type ./vitalsource.sh <start_page> <end_page> where <start_page> and <end_page> are the page numbers of the book images to download.

For example, to download pages 1 to 10, type `./vitalsource.sh 1 10`

Note: the script will create a directory named after the ISBN number of the book in the same directory where the script is run. If the directory already exists, the script will continue downloading images to that directory.

After downloading all images you can convert it to pdf using img2pdf tool by following command 

`img2pdf $(ls $folder_name/*.jpg | sort -n) -o "$folder_name.pdf"`

