## The purpose of this app is to test your skills in .net and angular.  Below you will find a set of tasks to be performed.  You may complete as many or as few as you woudl like.

### Before you begin please fork this repository and work in your own instance. (https://docs.github.com/en/search?query=forking)

## Tasks
1. Bug Fix:  We have a memory leak somewhere in our application.  The description from the user is as follows:
	> For my job I have to navigate between people and places.  As the day gets later my browser seems to slow down a lot.
	
	The performance team ran some tests and found that memory is going up from 5 MB on load to 2 GB after only a couple of hours.
2. Bug Fix:  Navigation issue.  The description from the user is as follows:
	> When I click on the Things nav item nothing happens

3. Enhancement:  The users would like to see the search results cached for at least 2 minutes.  Introduce code that could accomplish this.

4. Refactor:  Remove the X-Powered-By response header

5. Refactor:  The quality of this application can be improved.  In your role as a great developer, please refactor/improve this application as you seem fit.  I know we can create a product that is easier to read by other developers, improve the quality and provide more functionality for our clients.

### For the following you may write code to demonstrate or just describe how it could be done

1. Is DbContext used in a thread safe manner?

2. What would be the server side steps to add an ability to input a new Person record?

3. What are the security concerns with data UPSERT?  How would you resolve those concerns?


## ====================================================================================================

1. Is DbContext used in a thread safe manner?
Ans. =>   DbContext is not thread safe. EF Core does not support multiple parallel operations being run on the same context instance.

2. What would be the server side steps to add an ability to input a new Person record?
Ans. => Steps to add new person record: 
   a.In PeopleController, create a endpoint with [HttpPost] method with parameter to get data from request with an [FormBody] attribute.
   b.Check if person with same name is already exists in the Dbcontext.
   c.If the person dosn't exist then add new person to the dbcontext.People collection.
   d.save the changes made on dbcontext.
   e.return the new updated List of person.

3. What are the security concerns with data UPSERT?  How would you resolve those concerns?
Ans. =>
   a. Access control: Ensure that only authorized users can perform UPSERT operations.
   b. Data validation: Validate incoming data to prevent malicious or incorrect input.
   e. Auditing and logging: Maintain detailed logs of UPSERT operations for auditing purposes.

## ======================================================================================================

5. Refactor:  Some points to improve the quality of this application:

a. Add, edit, delete functionality can be implemented to the People, Places and Things entities. It will provide more control to the user.
b. Pagination feature to display large data.