find an area where it is inconsistent
and propose change in intern channel
make pr
has to be signed


make friday reflection

Bug: text input going outside container in request form when you click create request, when it is supposed to stay inside the request form container

How to get to the bug:
In any user role, click the 'Create Request' found at the left sidebar. There, you can find the overlapping textarea input(seen in image #1)

Proposal: remove the column attribute within the textarea tag (seen selected within the textarea tag in image #2) and give it a style with a width of 100%. (Result shown in image #3)

Proposal: remove the column attribute within the textarea tag (seen selected within the textarea tag) and give it a style with a width of 100%. (Result shown in image #3)


Proposal: implement horizontal scrollbar by either adding or overriding the

Bug: 
The "Assign to" input textbox overlapping the apply button. it is going outside its div container (seen in image #1)

Reproduction:
for LEAD and SUPER_ADMIN roles: click on the tickets dropdown found at the left sidebar and select the entire department option and then click any check box and you can see the "filter date" input will change into an "assign to" input. bug reported can be found there.

Proposal:
To remove the width property in the .ticket-autocomplete selector in app.css
(before and after demonstrated in images #2 and #3)



Bug:
no links on the ticket status navbar. if a user wants to check a ticket with a status other than "new", they have no way to access a page to view that. (bug illustrated in video)

Reproduction:
for any user role this can be seen if you view a page with a ticket table like assigned tickets and entire department pages

Proposal:
add an 'a' tag for each ticket status with their respective href's

inconsistency #4: table for tickets is not size responsive for smaller windows
![[Screenshot 2023-08-25 at 2.32.55 PM.png]]

![[Screenshot 2023-08-25 at 2.36.28 PM.png]]

proposal: add horizontal scroll bar for 


---

Bug: (jade)
Tables overflowing its container

Description:
The the contents of the two tables in the dashboard would extend/overlap its container when resizing the window into a smaller view width

Bug Reproduction Steps:
1. For any user role, in the dashboard. Resize the browser window horizontally, making it narrower.
2. Observe that after a certain point, the tables would no longer have their widths shorten. However its container will.
3. Continue resizing and the table would already be extending over its container.

Proposed Solution:
- Add a CSS overflow property to the containers of both tables to prevent them from overflowing outside its container.

---

Bug:
Create Button on hover changes cursor to a text cursor.

Description:
When a user hovers over the elements such as, users, view tickets, and dashboard, found in the left sidebar of the application. It changes the cursor to a pointer, this visually communicates to the user that the element is clickable.

However the same does not happen if a user hover overs the 'Create Request' button. It is inconsistent in communicated to the user that they can click on this element.

Bug Reproduction Steps:
1. In any page, for any user. However over the 'Create Request' button found on the left sidebar.
2. Notice how the cursor changes to a cursor used for text rather than a clickable element.

Proposal:
add a CSS 'cursor' property with a value of 'pointer' to the button when a user hovers of it.

---

Bug:
text input already has value by default if there is no user assigned when assigning ticket

Description:
Text input already has value by default if there is no user assigned when assigning ticket. If a user wants to assign a newly created ticket to another user. They will find out that instead of selecting the text input and then typing the name of the assignee, they would have to remove the content inside instead of typing the name immediately. This is because that the text box is already containing text with the default value 'None'

Bug Reproduction Steps:
1. For any user, navigate the left sidebar and select tickets.
		For certain roles, a dropdown may appear instead, so select the 'entire department' option
2. click on any ticket found in the tickets table
3. Select the text input to the right of 'Assign to'
4. Notice how rather than clearing the placeholder, a value of "None" is already within the input.

Proposal:
- Change the input from having no value by default if there are no assigned users rather thane having a value of 'None'.

---

Bug: (me)
Pending button in japanese localization breaks content because it is too long

Description:
The pending button in japanese localization breaks content because it is too long. In the word 'ペンディング', the 'グ' gets cut off is put in a new line under the word.

Bug Reproduction Steps:
1. From any page, for any user roles navigate the tickets page on the left sidebar.
2. If you are in english view, switch the localization but clicking on the localization switcher found on the top right of the website. 
3. Select 'Japanese'
4. Issue can be found on the top navbar where 'ペンディング'(Pending) is as the content is too long and gets cut-off the rest goes to a newline under.

Proposal:
- Remove the width property of the buttons found in the CSS under the nav-opt selector.
- Apply padding instead of width which will make the button content-responsive rather than staying in an absolute length.
- padding: 0 2.5pc;




