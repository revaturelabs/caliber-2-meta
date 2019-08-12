# caliber-2-meta
Meta Repository for Caliber 2

## the bugs fixed

Fixed the gateway redirect to get the SkillTypes data
To fix it go to Zuul Service and change the application.yml line 34
	strip-prefix: false
	Change it to
	strip-prefix: true
In the front end fixed the data population error where the notes object in the overall component was throwing an error as undefined
To fix it go to overall.component.html line 23 and change lines up to 29 as

	note.qcStatus
	Change it to
	note?.qcStatus

The ? tells TypeScript that the parameter is optional.

In the front end fixed the data population error where the QcNote was not instantiated yet and was throwing undefined object
in the file Audit.service.ts line 17
Change it as
	 overallBatchNote: QcNote;
	Change it to 
 	overallBatchNote: QcNote= new QcNote(0,"",0,0,null,0,"","",0,null,0);
In the front end in associate component fixed the array of notes undefined error by instantiating the notes array
To fix it go to Assess-Batch/Components/associate and open associate.component.html
And change the line 72
<td>
Change it to
<td *ngIf="noteArr.length != 0">

Fixed the cors origin bug by updating the controllers with @CrossOrigin annotation
To fix it add @CrossOrigin(value = "*")
Above each controller class in all services in STS
note*: maybe @CrossOrigin will work so try it
    6. Fixed the bug when you click on the week tab show undefined error
	The file is located at Assess-Batch/Components/associate
	Replace the code inside this file with this code
	https://pastebin.com/VZkM7AVv



	
I added bunch of if conditions to make sure that the traineeArray is filled with data before populating it
	
