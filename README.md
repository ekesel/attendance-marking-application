# attendance-marking-application
Attendance marking API software
1. Detect location of class and student's.
2. Shows list of students who marked attendance with time and date of marking.
3. QR code and link disables after fix timing set by creator.

🌚🌚 (Works on django and nextjs )

Works on API Basis,
Post Api to create event and QR LINK, this generates unique code which will use to identify.

POST API, when QR is scanned to update db with attendee data ( take attendee I'd, name and mob no)

GET API to list down attendees who have marked attendance with either PRESENT OR LOCATION MISMATCH.

GET API TO export attendee list to excel file.

DB structure -->
1. attendance_creator table 
unique_uuid_code -- string 
creator_location_lng -- string
creator_location_lat -- string
creator_location -- string
event_name -- string
created_datetime -- datetime
end_datetime -- datetime
check_location -- boolean

2. attendee table
unique_uuid_code -- foreign key
name -- string 
created_datetime -- datetime
phone_no -- string
attendee_location_lng -- string
attendee_location_lat -- string
attendee_location -- string
marked -- choice string field 


Frontend -->

Home page  --

Has a search page for a unique code, calls get api and returns another page with list of students with columns name ,phoneno, marked timing and marked status. Has a export button at top right to export to excel. Left side will show QR code to mark attendance.
Triggering QR will open link page.

Has a create button to open another page and open form to enter event name and marking end datetime picker with a submit button which will return a unique code and link through which attendee's can mark attendance.

Link page --
Has a form first containing student name and  phone number and then capture location on submit. 

About me page --

Links about me and how to contact me inside this page.


