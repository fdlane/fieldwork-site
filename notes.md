https://www.youtube.com/watch?v=noB98K6A0TY&list=PLl-K7zZEsYLmnJ_FpMOZgyg6XcIGBu2OX&index=1#t=65.287333

https://www.youtube.com/watch?v=k1D0_wFlXgo&list=PLl-K7zZEsYLmnJ_FpMOZgyg6XcIGBu2OX&index=1

Notes for capstone 2380
Keys
Trello mhvolk@pstcc.edu Tsf5r7^<CO4v
Begin March 8, 2017
Components is for isolating code- can take the same component and use elsewhere- a component is isolated, portable, testable—a component is a black box ex. button component- look into handlebars
“on” method to run when there is a change// “afterRender” event
What about a list-item component
Github markdown
End March 8, 2017
***

Begin March 3, 2017
A go-to-meeting at 9 with: DeWayne, Keith ?, Zach from KUB and Amber, Michal, Donald, Maude from PSTCC
Working on login, forgot password, have not started logout; Donald is using nodes for populating the database but will need to switch to Torii because it is tied to the session of the user
Zack and keith are out of town next week. Amber talked about getting Travis set up
Next meeting 3/10 in erc start at 1:30 
End March 3, 2017
Wednesday, February 08, 2017 begin
Use ember to make a model using (ember g model job) where g is for generate and job is the modelname
We have assignedTo, createdBy, editedBy, location, metaId and you do that by assignedTo:DS.attr(‘string’), … metaId:DS attr(‘number’) where DS data store
Above is a model and reference by job.assignedTo
To create a function in ember do:
model(){
return this.get(‘store’).findAll(‘job’)}
where model() is the function name and findAll is a method
in GitHub do a “squash and merge” and delete the branch
back to Ember https://guides.emberjs.com/v2.11.0/getting-started/quick-start/ 
from command line so C:\Users\Volk> cd ember-quickstart then once in that directory type “ember server” then open http://localhost:4200
Code School

Worker Screens:
1.	Login Screen: 2 text boxes, 2 labels, one button
2.	Job Screen: Buttons, one for each job assigned to that technician
3.	Details Screen: Once a button is pressed for a job the details screen is displayed as follows:
a.	Label for JobName at the top
b.	Button for logout
c.	A label area will have the location and any other details
d.	A take picture button
e.	Labels to hold Thumbnails of pictures taken for the job
f.	Text box for comments – must be not null
g.	Button to edit text box
h.	Drop-down for status (completed, rejected-takes it back to pending)
i.	Button for submit
Walking the board (Trello) looking at that to see what is in progress and what has been moved to done so that everybody knows what they are supposed to do
Take login use case- on dispatcher and worker (can do another project to solve problem) – since its shared functionality- dispatcher has to do the list of jobs-show a list of jobs- so list has to be done in both so go by functionality: login, logout, forgot password, reset password; make list-workers & jobs
Functionality of requesting list from the database and put it in an html
Dn firebase has built in funct. To get data from database but in heroku must get admin to get data
Dl do we need different ; getting static aps in firebase
These primitive use cases can be primitive for now; wbs work breakdown structure
Add github squash and merge delete branch
Javascript method called “on” whenever value changes it runs callback function- got to firecast utbe chanel to get sample code; there is an on when updating, total of 4 major ons can get to objects id to put them in order;; firecast will use raw javascript on the page and understand what is happening then when use emberfire will understsand what’s going on
Next week get list and login (plain, forgot, new, authenticate);; functionality vs appearance;; tools: worker, dispatcher but to do the tools must do all login and list –slow so move towards functionality
Overall project, goals, schedule, how meetings, process for approval, all the technologies, how the project was tackled, roles-decisions, a decision document, ; present different schemes for the look-keep in mind working conditions so workers can see, talk about meeting structure, continuous integration kub will take lead, ; open dialog with Kieth about projects

Got to routing in https://guides.emberjs.com/v2.11.0/getting-started/quick-start/ 
Code school at https://www.codeschool.com/courses/try-ember 
using atom as text editor
Dispatcher Screen ideas: 
One idea:
1.	Login
2.	Summary – two halves one side has all workers other side all jobs
3.	Two buttons at bottom for details and one for assign
4.	Use scroll bars as in little arrows above and below the lists 
Another idea uses tables
February 8, 2017 end
February 1, 2017 begin
Have a url that will run a method via heroku using http codes: 200 –good, 300 –redirect, 400 problem with request, 500 –serverside error;; all based on http stack;; firebase admin addon has a conflict –creates 2 ; 
Goals: build charter Title and description and whiteboard entire system, photo and visio it up
Title: cloud-based fieldwork system
Description: create a cloud-based poc for kub’s fieldwork system. Hosted on firebase using their db, security, photo. Implemented ember js use github for source control. Ember js to create a dispatching ap and mobile ap (ember js is just for development)
Description: The goal is to create a cloud-based proof of concept for KUB’s fieldwork system. The host is Firebase and we will use their database, security, and photo storage.

Nodejs on heroku
January 25, 2017
At KUB downtown: Repositories, one for each project; post own github account to Trello; Becky does middle-tiered development
When learning ember/semantic have all doc and when at kub ; when does ember server hosts express server and hosts ap, live reload server sets up socket, live reload server watches for changes; entire system doesn’t realize code is not new data, but can change it in the ember expender;; addin on chrome;; mirage helpful for debugging;; server-side api and all of its info;; mirage overwrites base implementation, so if sending api call for something it hijacks it and returns what you want;; not a lot of data to work with;; seeding the firebase database-just a giant Jason file;; so we need an account in the firebase database;; experience building in the cloud;; can take mirage for fieldwork and modify;; create repositories for the fake data; write ember ap or build node ap; ;; a node ap will have to be written;; dispatcher ember ap, worker ember ap, node ap for seeding the database, firebase database and the api that sits on top of it; authentication start with simple; also seeder needs to authenticate to firebase; need a place to store images; can we go straight from dispatcher to photo storage
Summary: dispatcher, worker, nodeJs, firebase data, photo storage, authentication (TORII);; firebase has a nosql database &database storage, all coming from the company firebase;; the two ember aps will live in firebase
Have to host a node ap somewhere separately; its api has to be listening all the time but static assets are gotten on a file by file bases;; the node ap needs to be run all the time heroko is a place in the cloud where this would run, so there needs to be an account to run it;; firebase is static
Code will lives in github; take that code and compile and put on server;; process from source control to server is the process of deployment ie continuous integration- have to set up a method to test; ; set up link between github and heroku
Can have a branch for development, testing, ..;; can configure heroku to do automatic updates
Wbs-work breakdown structure – check out slack, get for phone
My job create firebase database & ember handles that data
Ember cli want to access np;; npn can be just files but also can run;; bower is just files
Conemu is a shell; it uses bash; if you have git you have bash; it allows multiple windows
;; ember cli then ember new semantic-sample;; not stored but in a local git repository;;semantic ember ui may be the way to go;; create code with ember g
Installed Git  file:///C:/Program%20Files/Git/ReleaseNotes.html 
Fellix Rieseberg Check https://github.com/felixriesberg/ember-cli-windows
Conemu.github.io
Use adam for javascript
Conclusion: make a to-do list (keep a backlog that moves into the to-do list), post in Trello, team members pick one, when done will put in review column
Grab a task and move it to “in progress” and when finished move it to “review.” If it is code create a branch in github (past the url into Trello), look at pull request commits, the others run the code to be certain that it runs; must pass ember test. If component is modified then the test must be modified when running ember t. The author of the code does not merge it. Two people to approve one code.
Make screenshots of progress.
NEXT WEEK: Static hosting – for hosting ember aps and hosting data stored in Firebase, App Hosting, node seeder express js// field work – manager// jeckle page//readme.md Written in markdown// when new repo check readme option. Me: create users for the database ap in firebase
School: This is the full link in case the other one doesn't work.
https://www.couchbase.com/profile 
https://event.on24.com/eventRegistration/EventLobbyServlet?target=registration.jsp&partnerref=CL012517-Couchbase-01&eventid=1342418&sessionid=1&key=55CD0F5AF008FAA71B96EC646174276D&regTag=&sourcepage=register&mkt_tok=eyJpIjoiTTJWaE56ZGxaREJrWkdZMyIsInQiOiI2TFZzYnhId2lnQVMxSFM1c1BQa0xrRkVyZ2FodmxiZ0hTdngzQW9PRzVmQ0FTZjVtVVpraHlBUTBGM3lPVWJIUitmZDZlWFd2U3lYRnppbTJkRTVSZDFIeHpCUVMrV2gzZDFWRnhnbEF1Mk1mTkptQmtlaWtsSkQ1Q1RQZTNKMyJ9
Professor Burlingame,  BCT/CSIT
GitHub name MaudeVolk mhvolk@pstcc.edu U_i3<*eNaq https://guides.github.com/activities/hello-world/#intro
https://www.youtube.com/user/github 
On GitHub, saved changes are called commits. Each commit has an associated commit message, which is a description explaining why a particular change was made. Commit messages capture the history of your changes, so other contributors can understand what you’ve done and why.
Make and commit changes
Click the README.md file.
1.	Click the pencil icon in the upper right corner of the file view to edit. 
2.	In the editor, write a bit about yourself. 
3.	Write a commit message that describes your changes. 
4.	Click Commit changes button.
Pull Requests are the heart of collaboration on GitHub. When you open a pull request, you’re proposing your changes and requesting that someone review and pull in your contribution and merge them into their branch. Pull requests show diffs, or differences, of the content from both branches. The changes, additions, and subtractions are shown in green and red.
As soon as you make a commit, you can open a pull request and start a discussion, even before the code is finished.


January 24, 2017 at home
http://emberjs.com/  Notes: npm (node package manager), npm comes with node (see also The Coding Train in You Tube); up to creating an application in Ember in https://guides.emberjs.com/v2.11.0/getting-started/quick-start/ 
January 18, 2017 meeting
Client KUB: DeWayne Lane, Keith Clinard, Zachary Berardo & Team: Amber Rivera, Michal Kaminski, Donald Nash, me met via gotomeeting (note – pick a quiet place)
Currently KUB has a system for a dispatcher to receive jobs that need to be done, dispatcher has a list of field technicians & can assign a technician to a job & can find out its status – sometimes a job is cancelled so in that case the dispatcher wants to be able to communicate this right away. The field technician has a mobile device that receives the dispatchers directives and can keep the dispatcher up to date on their progress. 
Right now KUB is in the process of switching out meters and they want before and after photos of this to ensure correct meter reading at the time of the switch. The problem is the slowness of the system and the bulkiness of the storage.
KUB wants to store data in the cloud and improve speed of communication – they want all devices updated quickly. They do not want the users to have to keep asking about progress or tasks – if something changes then all devices are simultaneously and quickly updated to reflect the new situation.


Quality is most important
Stay updated – do not fall behind. It is unprofessional. Good communication is very important. All questions to the team leader to keep the lines straight. We don’t want multiple, possibly similar questions to the client.
Walk through after spring break. By then most of the project should be completed. Mention problems – do fact finding; goal is 3 wonderful projects.
Week 13 project completed. Presentation is the last day of class.
Today set up a regular schedule and establish good lines of communication within the team. Look at tasks for this week.
Remember storm’n norm’n perfom’n
454 Gay St, miller building
Michael 865-243-1503
Nash 865-405-9264
Pete’s coffee
Remedy 800 Tyson st.
Fire base, amber for data, semantic ui use that library through
Update git hub
NoSQL data base
Working on field work to assign & dispatch people to the field
Using trello and slack
How often should we meet with the client? Who is the contact person or people? How do we access the items that we need?
Fire base authentication
 https://www.raywenderlich.com/139322/firebase-tutorial-getting-started-2 
 https://www.mongodb.com/nosql-explained 
 http://www.techrepublic.com/blog/10-things/10-things-you-should-know-about-nosql-databases/ 

