---
layout: post
title: Final Sync Blog
description: Final Sync
permalink: /finalsync/
comments: true
---
<style>
    body {
        background-color: #2f5937 !important;
        color: #ffffff !important;
        font-family: 'Agmena', serif !important;
        line-height: 1.8 !important;
        margin: 0 !important;
        padding: 20px !important;
    }

    article {
        background: linear-gradient(145deg, #2f5937, #000000) !important;
        border: 4px solid #2f5937 !important;
        padding: 25px !important;
        border-radius: 20px !important;
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.8) !important;
    }

    article h1 {
        text-align: center !important;
        font-size: 2.5em !important;
        color: rgb(255, 255, 255) !important;
    }

    article ul {
        list-style-type: disc !important;
        margin: 15px 20px !important;
        padding-left: 40px !important;
    }

    article li {
        background-color:rgb(29, 71, 37) !important;
        padding: 10px 15px !important;
        margin: 10px 0 !important;
        border-radius: 10px !important;
        border-left: 5px solid #2f5937 !important;
        box-shadow: 0px 5px 10px rgba(18, 18, 18, 0.5) !important;
        color: #ffffff !important;
    }

    article code {
        display: block !important;
        background-color: #2f5937 !important;
        color: #000000 !important;
        padding: 10px !important;
        margin: 15px 0 !important;
        border-radius: 8px !important;
        font-size: 1.2em !important;
    }
</style>

<article>
    <h1>Final Sync</h1>

<h2>Introduction</h2>
    <p>This blog details the development of our full-stack web application, covering frontend, backend, database management, and API integration.</p>
   
<h2> 5 Things I did this Trimester:</h2>
    <ul>
        <li>API Backend Development</li>
        <li>Creating a Database</li>
        <li>Front End API compatibility and integration</li>
        <li>Collaboration and Group roles</li>
        <li>AWS use and Deployment testing</li>
    </ul>

<h2>MCQ Reflection:</h2>
    <img src="https://i.imghippo.com/files/CxQ7069Mq.png" alt="MCQ">
    <h5>I think my Comp Sci knowledge has improved greatly as reflected by my new MCQ score. My score on the last one was 25/67 and now it is a 47/67. This shows my improvement but also that I have much more to learn. I think that as we progress through third trimester along with studying for the AP Exam my score will go up if we take a third MCQ.</h5>

<h2>Project Feature Blog Write Up:</h2>
<h5>The API implemented for the project follows a structured approach to handling quote management using database interactions. The purpose of this API is to allow users to create, update, retrieve, and delete quotes while ensuring data integrity and efficient storage. The program abstracts database operations through a set of procedures, each handling a specific functionality such as adding a new quote, updating an existing one, or removing a quote from the database. This abstraction simplifies the process for users by providing a clean interface that interacts with the database without exposing its underlying complexities.</h5>
<br>
<img src="https://i.imghippo.com/files/UjS8357rA.png" alt="Update, Delete, Create">
<img src="https://i.imghippo.com/files/PAq1492xg.png" alt="DB">
<br>
<h5>To manage complexity, the API uses modular functions that encapsulate key operations. The create, update, and delete methods ensure proper database transactions with commit and rollback mechanisms, handling potential integrity errors to maintain consistency. By structuring the code in this way, the API ensures that each function performs a well-defined task, making it easier to debug, maintain, and expand. The strategy used to test the correctness of the procedure, aside from using test cases, involves logging and debugging. Logging statements capture potential errors that occur during database transactions, providing insights into failures and allowing for debugging without manual intervention. Additionally, interactive testing using a database query tool helps verify that data manipulation functions perform as expected.</h5>
<br>
<img src="https://i.imghippo.com/files/tnDX6311pM.png" alt="UDCFE">
<img src="https://i.imghippo.com/files/RyM6776WA.png" alt="QFE">
<br>
<h5>The API breaks down the larger problem of managing quotes into smaller subproblems, where each procedure addresses a specific database operation. The create method ensures data is properly stored, the update function modifies existing entries, and the delete method removes records safely. Together, these procedures contribute to the overall functionality by forming a CRUD (Create, Read, Update, Delete) structure that supports the application’s ability to manage user-generated quotes efficiently. This modular approach ensures that the API can scale while maintaining clear separation of concerns, making it easier to integrate into larger systems.</h5>

<h2>Comp Sci Future</h2>
    <h5>When I think about my future in Comp Sci I think I would like to pursue internships and program oppurtunities as well as take classes in college relating to Comp Sci as I think it is a very useful field of knowledge. I don't think Comp Sci would be the main focus in my career as I want to do Aerospace Engineering but I do know that it requires some Comp Sci knowledge. I think in highschool taking AP CSP and possibly doing internships relating to Comp Sci would help me a lot in my desired career and throughout the rest of highschool and college.</h5>
<br>
<h2>Project Reflection</h2>
    <h5>I think our project and our group has come a long way since the beginning of the trimester. The overall coding for our project was acceptable, it was not coordinated and neither was our group. We didn't communicate all that well and some of us wouldn't meet deadlines or code according to what we needed. Some were absent for long periods of time without asking or knowing what went on during their leave. But we pulled ourselves together, we started communicating more and as we did our project reflected that. All of our features were coordinated and our whole project flowed together. Our communication process got better and we all met deadlines. All of us stuck to our roles and fufilled our responsiblities and our project shows our hard work. I think our next steps would be to add more features or integrate them better. I think our biggest strength is that all of our features work as needed and without issues with one another or in deployment. I think our biggest weakness is our authentication system as it still has some issues. All in all I think our project reflects our hardwork as a team and has improved alongside our group and collaboration.</h5>
<br>
<h2>Self Reflection</h2>
    <h5>Reflecting on my Comp Sci performance this last trimester I think I improved a lot from last trimester and continued to improve throughout the tri. I think my strengths lie in front end design and integration as well as database creation and deployment. My weaknesses would be my lack in vocabulary knowledge as well as being unfamiliarized with certain programs or features. Throughout las trimester and at the beginning of this trimester I was confused and didn't understand code all that well. But as the trimester moved on I made myself try harder to understand and to get better at code and CS in general. If i had to give myself a grade on this Final I think I would give myself around a 9.6/10 (if possible) based on this break up: </h5>
<br>
<h5> I say this because I think I have tremendously improved my skills and understanding. My blog for this review showcases all the work I've done and my understanding of it. My past reviews show improvement and I have done all that the 10th point requires and for those reasons I think I have earned that 10th point.</h5>
<style>
table, th, td {
  border: 1px solid black;
}
</style>
<h1>Self Grade Break Down</h1>

<table>
  <tr>
    <th>Topic</th>
    <th>% Of Grade</th>
    <th>Points</th>
  </tr>
  <tr>
    <td>5 Things Over 12 Weeks / Issues, Burndown, Presentation</td>
    <td>95%</td>
    <td>4.75/5</td>
  </tr>
  <tr>
    <td>Full Stack Project Demo</td>
    <td>95%</td>
    <td>1.85/2</td>
  </tr>
    <tr>
    <td>Project Feature Blog Write-up</td>
    <td>100%</td>
    <td>1/1</td>
  </tr>
    <tr>
    <td>MCQ</td>
    <td>100%</td>
    <td>1/1</td>
  </tr>
    <tr>
    <td>10th Point</td>
    <td>100%</td>
    <td>1/1</td>
  </tr>
  <tr>
    <td>Total</td>
    <td>96%</td>
    <td>9.6/10</td>
  </tr>
<br>


