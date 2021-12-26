# Project - Build a task Manager

## Feature
	- Multiple users can use the app
	- Every user can add tasks
	- After creating a task , user can assign it to different user
	- Tasks
		- has a description
		- has a priority : enum<high/low/medium>
		- has a due date
		- has a state : pending/ completed
		- Notes
			- A task an have multiple notes inside it
			- Notes can be made by the owner asignee
	- The creator of the task can edit/ delete the task
	- The creator or asignee can mark the task as done


## DB Schema Design
---
**NOTE**

- Tables name should be in plural, because there are N users, but and #each row hass one uers, and n rows can have n users(Because so many #records of entities would be there)
- Base_table is not the real table, but other tables will implement base_table and adds its own objects/columns as well
---
base_table
- id - integer autoincrement primary key	
- created_at - date
- updated_at - date	


users 
(user:task = 1: N)
- id - integer autoincrement primary key
- name - string(100)
- emaild -  string(100) : validate(email) #  foramt is xxx@yyy.zzz #foreign key cant be an array 

tasks
- descripti/on - string
- priority- enum[high, medium, low]	
- due_date- date
- status - enum[pending, completed]
- creator_id - fk(users.id)
- asignee_id - fk(users.id)

notes
- task_id - fk(tasks.id) #under which task we are writing this node
- description - string
- author_id - fk(users.id)

## API 
---
**NOTE**

- API's are not concrete, but a class is concrete, they never actually do something
- API tells us how we interact with BEnd, 
- The way to interact with BEnd is HTTP, GET, PUT,PATCH,PATCH.
- Every library has an API
- API is the documentation of how 2 softwares or two pieces of a software interact with eachother
---

HTTP API - server -client communication
OS API app-os or app-kernel communication

## REST API for our project
HTTP methods: get, put, ,patch, delete, post...

## REST API
---
**NOTE**
- servers should be state less, if they are stateful, scalling becomes problem
---
REST API -  Representational state transfer

GET	https:://api.scaler.com/courses      -> get data of all couses
GET	https:://api.scaler.com/courses/dsa  -> get data of the DSA course
GET	https:://api.scaler.com/courses/sd   -> get data of the System Design
GET	https:://api.scaler.com/courses/ml   -> get data of the ML course


GET	https:://api.scaler.com/studnets/44  -> get data of deepika

BASE URL # where our server is hosted
GET	https:://api.scaler.com/

ENDPOINTS # helps us create the url
/courses
/courses/{id}  # strings
/students
/students{id}  # integers

RESOURSES # tables corresponsd to table on our DB
-courses
-students

IDENTIFIERS # corresponsd to Ids
dsa(course)
44(student)

METHODS/ACTIONS/VERBS #corresponsd to CRUD calls
get
put
patch
post
delete

---
**NOTE**

- In post we dont implemnt the resource
- In put we dont implemnet resource, but if dome, it replaces the table	
 ---






