# Data-Engineering-Zip-File-Processing

# Overview

This program is designed extract and process a folder of 53 zip files, into a list of usable pandas dataframes with key insights extracted.

# Process

To begin this program I built an empty pandas dataframe containing required columns that I will fill later in the program.

Then I began handling my folder of zip files, starting with connecting the file path and listing all the files contained within the directory. Now that I have my list of files I'll find the delimiter for each zip file. I set up a for loop that iterates over each file in the zip files list, opens the file in read mode, and defines the files delimiter using csv sniffer. I then store the file name and the appropriate delimiter in a dictionary for future use.

Next I needed to check each of my zip files for the presence of headers, as I need all my dataframes to be uniform in the final product. Again I wrote a for loop that iterates over every file name in the zip file list and opens the file in read mode. I then nested another for loop to read the specific file's first character on line 1. If there is a character that matches d for datetime, the file has headers so I can open this file into a pandas dataframe and handle the delimiter. If the file does not have a d as the first character in the first line I will open the file into a pandas dataframe, handle the delimiter, and assign headers. Finally I append the dataframe into my final dataframe list.

Finally I can fill in the empty dataframe I created at the beginning of the program with data from the df's in my final dataframe list. Here we want the count of unique card no's from each dataframe, the count of unique dates in each dataframe, and the rows from each dataframe.

Finally we can see the final result in the Wedge Summary line.
