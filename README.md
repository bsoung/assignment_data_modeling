DB Analysis

Basic:

You are building a free online learning platform which will be used by students who are exclusively online (but don't need to be logged in or kept track of). You offer many different courses, each with a title and description, and each course has multiple lessons which can be displayed. Lesson content consists of a title and body text. What are the Goals? Entities? Attributes, types and constraints? Relationships? Design the data model for this web app.

Many to Many
Students => Courses
Courses <= Students



Student table
Course table
Join table :contains Student ID and Course ID



Student
ID  First_Name  Last_Name  Email  Address  Created_At
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Courses
ID  First_Name  Last_Song  Description   Created_At   
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          

Student ID | Course ID
----------------------
1          | 3
2          | 1
2          | 4
2          | 2

One to Many
Lessons => Courses
Students => Courses

Courses
ID  Title  Description  Link  Created_At
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Lessons
ID    Course_ID   Created_At  
-----------------------------------------
          |           |         
          |           |        
          |           |         
          |           |        
          |           |         
          |           |         
          
******
You are building the profile page for a new User on your login site. You are already storing your User's username and email, but now you want to collect demographic information like City, State, Country, Age and Gender. Think -- how many profiles should a User have? How would you relate this to the User model? Design the data model for this web app.


One to One
Lessons => Courses
Students => Courses

User
ID  City  State  Country  Age  Gender Created_At
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |


Profile
ID  User_ID  Page Views  Link   Created_At
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |


You want to build a message board like Hacker News. Users can post links. Other users can comment on these submissions or comment on the comments. How would you make sure a comment knows where in the hierarchy it lives? Design the data model for this web app.

One to Many
Comment => User
Post => User
Comment => Post

User
ID  City  State  Country  Age  Gender  Created_At
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Comment
ID  Comment_ID  User_ID  Post_ID    Created_At        
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |


Post
Post_ID  User_ID    Content   Created_At
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |



You want to build an e-commerce site like a very simplified Amazon.com. You'll need to keep track of products, users, orders, shipments and all the bits and pieces necessary to glue them all together. Design the data model for this web app. How can you handle the quantity of items in each order? How do you know where an order has been shipped? Bonus: What happens to your historical data if a user opts to delete their account? How might you handle this?


One to Many
Order => User
Shipment => User

Many to Many
User => Product
Product => User

Shipment => Order
Order => Shipment



User
User_ID  City  State  Country  Age  Gender  Created_At 
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Order
Order_ID  User_ID     Time     Created_At   
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |



Product
Product_ID      User_ID     Date    Description  Created_At   
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Join
User ID | Product ID
----------------------
1          | 3
2          | 1
2          | 4
2          | 2

Join
Order ID | Product ID
----------------------
1          | 3
2          | 1
2          | 4
2          | 2

Shipment
ID     User_ID   Product_ID     Date    Shipping_name    Created_At 
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Join
Shipment ID | Order ID
----------------------
1          | 3
2          | 1
2          | 4
2          | 2


(Optional) You want to collect analytics data for visitors and logged-in-users who are visiting your website. This includes basic information like page views and more advanced things like link clicks and time on page. You ideally want to tie this information back to a given user if possible. Design the data model for this analytics infrastructure. You'll have to use your judgement about what additional attributes would be interesting to track

User
User_ID     Url     Click  Age  Log_Status     
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |

Link
Link_ID      User_ID  Url     Click  Age   
-------------------------------------------------
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |
          |           |          |      |







