---
layout: page
title: Sprint 3 Reflection and MCQ analysis
permalink: /S3MCQ/
---

<html>

<h2> Sprint 3 Reflection </h2> 

<h4>Our project journey has been really interesting, with every piece coming together seamlessly after lots of work and collaboration. We take great pride in our ideation process, particularly in designing the platform to feature live chat rooms and different pages for topics relating to Del Norte High School. This structure enhanced clarity and accessibility, encouraging consistent user engagement with the platform and with each other.
<br>
<br>
<div class="floatright">
<img align="right" 
         src=
"https://private-user-images.githubusercontent.com/179050906/388257807-f1960d76-2262-436b-b831-91b15a350fd5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzIxMzk4MDIsIm5iZiI6MTczMjEzOTUwMiwicGF0aCI6Ii8xNzkwNTA5MDYvMzg4MjU3ODA3LWYxOTYwZDc2LTIyNjItNDM2Yi1iODMxLTkxYjE1YTM1MGZkNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTIwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTEyMFQyMTUxNDJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04ODk3NmQ4YzcyNjZjMzgyYTIzNTgzYTc3OTE5ZDkzOTFhZDgwMDQxMTkwYzgzNmY1ZDI4NmUyZTc1OGQ1OGJiJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.MHczaeg0bu-Mkj0izOyJ4GY8U6IiJQms3Oeb39pRXGE" 
         alt="cr">

<br>
<div class="floatright">
<img align="right" 
         src=
"https://private-user-images.githubusercontent.com/179050906/388286620-3e8198eb-6373-4902-ae77-c6bb8ecb0972.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzIxNDI5NDIsIm5iZiI6MTczMjE0MjY0MiwicGF0aCI6Ii8xNzkwNTA5MDYvMzg4Mjg2NjIwLTNlODE5OGViLTYzNzMtNDkwMi1hZTc3LWM2YmI4ZWNiMDk3Mi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTIwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTEyMFQyMjQ0MDJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01ZmZmMGYwZjczYWM3ZTdiNTdkZmRmYjJlNTk3YzZhMDlhODIxYTUyZGNhOWI5N2ZlYTBhOGY4NDhhYWY3YmQ2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.ubnU3HhW1mOkVRRssdnDFYq252G85Lz3cikL_Jk2Vt0" 
         alt="cr">
<br>
<h2>1: fetchGroups()</h1>
<ul>
        <li>Purpose: Fetches a list of groups based on a specified section name ("Create and Compete") and populates a dropdown menu with these groups.</li>
        <li>Process:
Sends a POST request to the /api/groups/filter endpoint with the section name as a parameter.
Checks if the response is successful and throws an error if not.
Parses the response JSON to retrieve the list of groups.
Creates "option" elements for each group and appends them to the dropdown menu identified by its ID (group_id).</li>
    </ul>
<h2>2: fetchChannels(groupname)
<ul>
        <li>Purpose: Fetches a list of channels associated with a selected group and (presumably) populates another dropdown menu or UI component with these channels.</li>
        <li>Process:
Sends a POST request to the /api/channels/filter endpoint with the selected group's name as a parameter.
Similar to fetchGroups(), it validates the response, processes the list of channels, and integrates them into the UI.</li>
    </ul>

<h4>The feedback we received confirmed the success of both our ideation and execution. Users appreciated the platform’s thoughtful design and how the chatrooms helped with inclusion and interaction between users. Many users loved the clear and simple user interface aswell. This feedback made us happy as we had achieved what we had aimed to.
<br>
<h2> MCQ Reflection </h2> 
<br>
<div class="floatright">
<img align="right" 
         src=
"https://private-user-images.githubusercontent.com/179050906/388277666-5b1ca31a-4c1f-4f21-b808-a03ca5c4fc0a.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzIxNDA1MTcsIm5iZiI6MTczMjE0MDIxNywicGF0aCI6Ii8xNzkwNTA5MDYvMzg4Mjc3NjY2LTViMWNhMzFhLTRjMWYtNGYyMS1iODA4LWEwM2NhNWM0ZmMwYS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTIwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTEyMFQyMjAzMzdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1lYTQ4NDIwOGZkMmQyMTg1MTQ4OWU4MjU0MjdlMGVlMDRhYzg2MDVlZWIyZDRiMmE5ZmRkMWE5NWExMjFiYTczJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.oBH62Ky1AlCyIBBWSKk1dhd_OWA-yvfOBOphU6eMkrY" 
         alt="mcq">
<br>
<br>
<br>
<h1 class="center-text">Reflection on 2018 Practice Exam MCQ</h1>
<ul>
        <li>I found the Practice MCQ on AP classroom to be challenging as even though I worked with some of the concepts questioned I wasn't taught them but instead I learned the concept soley for the purpose I was trying to use it.</li>
        <li>I think I should strive to learn how to manipulate the concepts and base codes to do anything with certain programs as that way I can answer questions such as the ones asked in the MCQ with ease and also to increase my CompSci skills and knowledge.</li>
        <li>I feel like 3.9 (Algorithms) and 4.1 (The Internet) were the hardest for me to understand and answer, and 3.3 (Math Expressions) and 3.6 (Conditionals) felt like the easiest as I taught these concepts during Sprint 2 and they are fairly simple</li>
        <li>I think my score is my sign to start understanding the concepts more in depth as it would help me be successful in CSP and for the AP exam.</li>
        <li>Moving forward, I’ll use this as motivation to study, understand, practice problems, and prepare more.</li>
    </ul>
<br>
<br>

<div class="vertical-center">
<a href="https://docs.google.com/presentation/d/1Z3H1QruaoxImEMCblQJg128N5YAwurLE-uoKCiDUK24/edit?usp=sharing" class="button">MCQ Corrections</a>

 </div>
<head>
<style>
.button {
  background-color: #504e4e;
  border: 2px solid #353736;
  border-radius: 8px;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  transition-duration: 0.4s;
  margin: 4px 2px;
  cursor: pointer;
}


</style>
</head>
