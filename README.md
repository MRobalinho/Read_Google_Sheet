# Read_Google_Sheet
Read Google Spreadsheet

## A workflow system based on email and Google Forms
## GOAL:
Use the information collected by Google Forms, to apply a process of sending email with python, managing the information registered in Google spreadsheet in a massive and automatic way.

 
## Definition:
Workflow is the sequence of steps necessary to automate business processes, according to a set of defined rules, allowing them to be transmitted from one person to another.
In theory, this management can be organized manually, but currently most of the workflow is systematized in the context of information technologies, better known as IT systems.

What is workflow from a technological point of view and how does it improve business processes?
Workflow technology refers to a set of tools that, when viewed from a macro-environmental perspective, bridge the gap between eventual units and the office of a particular company.
In general, workflow technology not only guarantees communication and information exchange between different departments involved in the same business process, but also ensures that any and all tasks are performed by the employee for whom it is intended.
 
## Development:
We need to develop 5 strategies to our work:
1.	Create a Google Forms (very easy)
2.	Define a key API to Google Drive
3.	Share the information for Google Spreadsheet, that contains the collected information from Google Forms
4.	Read Spreadsheet with python program to a pandas dataframe
5.	Create python program to send email, with the information from a pandas dataframe

Let’s go:
1.	Create a Google Forms
Google Forms is a search administration application included in the Google Drive office suite, along with Google Docs, Google Sheets and Google Slides. Forms presents all the collaboration and sharing features found in Documents, Spreadsheets and Presentations. It is powerful and an easy and free way to create your inquiries and / or collect formatted information from your customers.
Go to https://docs.google.com/forms/  and create your form.
 
Google automatically creates a spreadsheet Google Spreadsheet associated with the form, where it will put all the information received from filling out the form. It's a spreadsheet, in the cloud. My example the spreadsheet created:
 
2.	Define a key API to Google Drive
To access the Google Drive with a program, we need create our API. To create the API go to Google Console: https://console.developers.google.com/
A good work describes this process, here:
https://towardsdatascience.com/accessing-google-spreadsheet-data-using-python-90a5bc214fd2

 

3.	Share the information for Google Spreadsheet, that contains the collected information from Google Forms
The last step gave us a key to use in our documents on Google Drive. This key is the element to whom we give sharing to our spreadsheet. Use the “client_email” information.
 
 

	
We can use this key to access the file in the python program.
4.	Read Spreadsheet with python program to a pandas dataframe
We need to import gspread and oauth2client.
The file “Client_My_Drive_API_Secret.json” is created during the configuration tha Google API. It’s a JSON file that contains the Keys to access the Google Drive using a program. Need to put the JSON file in your work path.
 
Another way is obtain a Key to the Spreadsheet. 
For that we need to publish our Google Spreadsheet file: File > Publish on WEB > CSV format
 

 
In the Python program we access like that, to read the Speadsheet and put then in a Pandas dataframe:
 
 
5.	I created a python program to send email, with the information from a pandas dataframe
 	I tried 2 ways, once using email.mime functions and another using Yagmail. Its easier to use yagmail.
Need to import yagmail, and make I created a cycle that reads the pandas dataframe and calls the function sending email.
 
In the body we can use HTML to create a better design.
 
For the attachments only need to inform the path and name file to attach in the email. I tried to attach many types of files, including PDF, JPG, and ICS (for calendar appointments), with successful execution. One easier way to create ics files, I found the web page https://ical.marudot.com/, where we can define the event and download to a file ics format.






