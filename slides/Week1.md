Week 1 of Project 3
========================================================
author: Charlotte Chang
date: 2020-10-25
width: 1440
height: 900
autosize: true

Goals:

* Authenticate access to Google sheets
* Select an issue and platform with a clear rationale
* Begin compiling environmental social media data

Getting started
========================================================

* First, make a copy of the [Google sheet](https://docs.google.com/spreadsheets/d/1hQy8kR81GHmMDPivpyd8XzAGU7A6oUCUArq1bltm5EQ/edit?usp=sharing) in your own Google drive account. 
* You can do this using either:
    + `File -> Make a copy`  
    + or copy-pasting the contents over to your own Google spreadsheet file.


Authenticating Google sheets access
========================================================

Next, you can run the following code in your `RStudio Server` session in the console (copy and paste these lines of code into the `Console` which always has the `>` symbol to take in a command).

`library(googlesheets4)`

This may generate some messages, like ` Warning message: replacing previous import ‘vctrs::data_frame’ by ‘tibble::data_frame’ when loading ‘dplyr’ `. Don't worry about that; it is simply warning you that by loading `googlesheets4` into your workspace, you are overriding the command `data_frame` from the package `vctrs` with the command `data_frame` from the (`tidyverse`) package `tibble`. 

Note that the double colons in `tibble::data_frame` represent the syntax for calling a function (`data_frame`) from a specific package (`tibble`).


Initial interaction with Google sheets API in R
========================================================

Then, the first time you interact with a Google sheet, it will ask you about permissions to store your credentials to access your Google account in the future from your `RStudio Server` workspace. Select `1: Yes`.

`enviro_soc_media_DF <- googlesheets4::read_sheet("https://docs.google.com/spreadsheets/d/1hQy8kR81GHmMDPivpyd8XzAGU7A6oUCUArq1bltm5EQ/edit?usp=sharing")` 

Note that we are storing the data from the Google sheet into a variable called `enviro_soc_media_DF`, short for "environmental social media `data.frame`".

(Note that you will want to replace the link here with the `sharing` link for your own Google sheet eventually.)

Next step:
========================================================
In the console, you will then see:

```
Is it OK to cache OAuth access credentials in the folder '/Users/chc02006/.R/gargle/gargle-oauth' between R sessions?

1: Yes
2: No

Selection:
```

Type `1`. The console will then print:
```
Waiting for authentication in browser...
Press Esc/Ctrl + C to abort
```

========================================================
At the same time, another browser tab should open, displaying:


<img src="misc/grantTidyverse.png" title="Googlesheets authentication query for your Google account." alt="Googlesheets authentication query for your Google account." height="800px" />

========================================================
Select `Allow`. Next, you will see:

<img src="misc/permissions.png" title="a landing page asking you to confirm your access choices." alt="a landing page asking you to confirm your access choices." height="800px" />

========================================================
Ensure that you have selected the checkmark next to 

`See, edit,create, and delete your spreadsheets in Google Drive`. 

Then click `Allow`. 

You should then see this message:

![success message](misc/success.png)
