

# Module 3 Code Challenge

![](demo.gif)


For this code challenge you will be building out the above interface. 

Often, on the side of the screen you will see a list of "all the things", think all of your emails or messages or youtube search results. There will usually be some information about that thing, the email subject and sender for example, but not all of the information that item contains (i.e. not the whole body of the email).

By clicking one particular item in the master list, the application will show more information about that particular item.


In the above example, you see list of courses and when you click on see detail you can see the students in that specific course.

## Deliverables

![](demo.gif)



**As a user, when the page loads I should see a list of courses retrieved from an API on the left hand side of the screen.**

**As a user, when I click the `See Detail` button, the application should reveal more information about that particular class.**

**As a user, when looking at the details of a course. I can edit a student's percentage. Clicking the 'Edit' button will save any changes added to the description in the database**


## Implementation Notes

### The API

#### API Endpoints
`https://sheltered-stream-73510.herokuapp.com/users/1/courses` # See all courses
`https://sheltered-stream-73510.herokuapp.com/users/1/courses/:id` # See a single course
`https://sheltered-stream-73510.herokuapp.com/users/1/students/:id` # Update a student

The API endpoint we need to retrieve all the courses is a conventional RESTful route
* **Route:** GET `https://sheltered-stream-73510.herokuapp.com/users/1/courses`


To see the students for a specific course you'll need to make a GET request 
* **Route:** GET `https://sheltered-stream-73510.herokuapp.com/users/1/courses/:id`

To update a students percentage you'll need to make a PATCH request
* **Route:** PATCH `https://sheltered-stream-73510.herokuapp.com/users/1/students/:id`
* **Body:**
```js
  {percentage: "new percent"}
```
* **Headers:**
```js
  {
    'Content-Type': 'application/json',
    'Accept': 'application/json'
  }
  ```

  **Important Notes:**
  * Don't forget to stringify the body of the request.
  * When using `fetch` to make a PATCH request be sure to capitalize method: 'PATCH'


## Considerations

You are free to solve this in any way you choose. It is not required that you have ES6 classes or use Object Orientation. We would recommend beginning with a straightforward functional implementation and refactoring to objects as needed.
