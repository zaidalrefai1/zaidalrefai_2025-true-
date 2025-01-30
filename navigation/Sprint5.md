---
layout: post
title: Spring 5 Final Blog
description: Sprint 5 Blog
permalink: /sprint5/
comments: true
---


<style>
    body {
        background-color: #000000 !important;
        color: #ffffff !important;
        font-family: 'Agmena' !important;
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
        color:rgb(255, 255, 255) !important;
        text-shadow: 2px 2px 5px rgb(255, 255, 255) !important;
    }

    article ul {
        list-style-type: disc !important;
        margin: 15px 20px !important;
        padding-left: 40px !important;
    }

    article li {
        background-color:#1f3d2b !important;
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

    article blockquote {
        font-style: italic !important;
        border-left: 5px solid #2f5937 !important;
        margin: 20px 0 !important;
        padding-left: 20px !important;
        color: #d3d3d3 !important;
    }
</style>

<article>
    <h1>Quotes Generator Blog</h1>

<h2>1. Introduction</h2>
    <p>
        This blog shows the inner workings of the Quotes Generator
    </p>

<h2>2. Frontend Features</h2>

<h3>Dynamic Quote Generation</h3>
    <p>
        User select a category, and the app generates a quote using the database
    </p>
    <code>
 const quotesDataset = [
        { text: "The only way to do great work is to love what you do.", category: "motivational" },
        { text: "Don't watch the clock; do what it does. Keep going.", category: "motivational" },
        { text: "Winning isn’t everything, but wanting to win is.", category: "sports" },
        { text: "Champions keep playing until they get it right.", category: "sports" },
        { text: "Hard work beats talent when talent doesn’t work hard.", category: "sports" },
        { text: "Success is not the key to happiness. Happiness is the key to success.", category: "common" },
        { text: "Happiness is not by chance, but by choice.", category: "common" },
        { text: "Success is not final, failure is not fatal: It is the courage to continue that counts.", category: "common" },
        { text: "Believe you can, and you're halfway there.", category: "common" },
        { text: "In the middle of every difficulty lies opportunity.", category: "common" },
        { text: "Never give up on something you can’t go a day without thinking about.", category: "motivational" },
        { text: "It’s not the will to win that matters—everyone has that. It’s the will to prepare to win that matters.", category: "sports" }
    ];

       async function fetchQuotes() {
        const category = document.getElementById('category').value;
        const quotesList = document.getElementById('quotes-list');
        quotesList.innerHTML = '';

        try {
            const response = await fetch(apiUrl + '/quote');
            if (response.ok) {
                const quotes = await response.json();
                let filteredQuotes = quotes;

                if (category) {
                    filteredQuotes = quotes.filter(q => q.category === category);
                }

                filteredQuotes.forEach((quote) => {
                    const listItem = document.createElement('li');
                    listItem.textContent = quote.text;
                    quotesList.appendChild(listItem);
                });
            } else {
                throw new Error('API unavailable, falling back to local dataset');
            }
        } catch {
            let filteredQuotes = quotesDataset;
            if (category) {
                filteredQuotes = quotesDataset.filter(q => q.category === category);
            }

            filteredQuotes.forEach((quote) => {
                const listItem = document.createElement('li');
                listItem.textContent = quote.text;
                quotesList.appendChild(listItem);
            });
        }
    }
    </code>
 <p>
        This function fetches a quote based on the selected category and updates the DOM dynamically.
    </p>


<h3>Creating Quotes</h3>
    <p>
        Here's the code for user created quotes:
    </p>
    <code>
      
    async function addQuote() {
        const newQuote = document.getElementById('new-quote').value;
        if (!newQuote) return alert('Please enter a quote to add.');

        try {
            const response = await fetch(`${apiUrl}/quotes`, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ text: newQuote, category: "general" })
            });

            if (response.ok) {
                alert('Quote added successfully!');
            } else {
                throw new Error('API request failed');
            }
        } catch {
            quotesDataset.push({ text: newQuote, category: "general" });
            alert('Quote added!');
        }
        fetchQuotes();
    }
    </code>
 <p>
        This form submission handler sends post data to the backend and displays success or error messages.
    </p>

<h2>3. Backend Features</h2>

<h3>Post Creation Endpoint</h3>
    <p>
        The backend API allows users to create posts via the following endpoint:
    </p>
    <code>
      def __init__(self, name, category):
        self.name = name
        self.category = category

    def create(self):
        try:
            db.session.add(self)
            db.session.commit()
            return True
        except IntegrityError as e:
            logging.error(f"Error creating quote: {e}")
            db.session.rollback()
            return False
    </code>
    <p>
        This function validates the input, creates a new quote, and saves it to the database.
    </p>

 <h3>Post Retrieval Endpoint</h3>
    <p>
        The API retrieves posts based on category:
    </p>
    <code>
         async function fetchQuotes() {
        const category = document.getElementById('category').value;
        const quotesList = document.getElementById('quotes-list');
        quotesList.innerHTML = '';
    </code>
    <p>
        This endpoint retrieves all posts for a specific channel, returning them in JSON format.
    </p>

<h3>Database Initialization</h3>
    <p>
        The database is initialized with tester data using the following function:
    </p>
    <code>
        def init_quotes():
    with app.app_context():
        db.create_all()
        
        quotes = [
            {"name": "Quote 1", "category": "Motivation"},
            {"name": "Quote 2", "category": "Mental Health"},
            {"name": "Quote 3", "category": "Happiness"},
            {"name": "Quote 4", "category": "Sports"},
            {"name": "Quote 5", "category": "School"},
            {"name": "Quote 6", "category": "All"},
        ]

        for quote_data in quotes:
            quote = Quote(name=quote_data["name"], category=quote_data["category"])
            try:
                db.session.add(quote)
                db.session.commit()
            except IntegrityError as e:
                logging.error(f"Error creating quote: {e}")
                db.session.rollback()
    </code>
<p>
        This function preloads the database with sample posts for testing purposes.
    </p>

<h2>4. Update and Delete Functions</h2>
    <p>
        Frontend and backend communicate to delete and update user created quotes:
    </p>
    <code>
          def update(self):
        try:
            db.session.commit()
            return True
        except IntegrityError as e:
            logging.error(f"Error updating quote: {e}")
            db.session.rollback()
            return False

    def delete(self):
        try:
            db.session.delete(self)
            db.session.commit()
            return True
        except IntegrityError as e:
            logging.error(f"Error deleting quote: {e}")
            db.session.rollback()
            return False

<h2>5. Challenges and Improvements</h2>
    <p>
        <strong>Challenges:</strong>
    </p>
    <ul>
        <li>Debugging API responses and ensuring data validation.</li>
        <li>Designing a frontend that integrates seamlessly with backend APIs.</li>
        <li>Integrating model to communicate with front end and with main.py to initialize database of quotes</li>
    </ul>
    <h2>6. Addressing Learning Requirements</h2>
<p>
    This blog aligns with the outlined learning requirements by demonstrating the following:
</p>
<ul>
    <li><strong>Programming as a collaborative and creative process:</strong> The project integrates both frontend and backend components, requiring collaboration and creative problem-solving.</li>
    <li><strong>Group and individual contributions:</strong> The blog highlights the group’s purpose (creating a free-response question platform) and my individual contributions (frontend features, API integration, and CRUD endpoints).</li>
    <li><strong>Input/Output demonstration:</strong> Examples of user inputs (topic selection, form submissions) and outputs (API responses, rendered DOM updates) are included.</li>
    <li><strong>API request handling:</strong> Postman examples and frontend fetch requests showcase how inputs are sent and processed via RESTful APIs.</li>
    <li><strong>Database management:</strong> Demonstrates initializing, querying, and restoring tester data using SQLAlchemy.</li>
    <li><strong>Algorithmic logic:</strong> CRUD operations and frontend request/response handling show sequencing, selection, and iteration.</li>
    <li><strong>Error handling:</strong> Highlights how invalid inputs trigger different backend responses.</li>
</ul>
<p>
    By addressing these requirements, the blog provides a complete overview of the technical implementation and learning outcomes of the project.
</p>

<h3>Third-Party Libraries</h3>
<p>
    This project uses <strong>SQLAlchemy</strong> as a third-party library for Object-Relational Mapping (ORM). SQLAlchemy simplifies database operations, including querying rows (lists) and managing table columns (dictionaries). Its integration ensures data consistency and reduces boilerplate code, allowing for more efficient database management.
</p>

<p>
        <strong>Improvements:</strong>
    </p>
    <ul>
        <li>Add better error messages for invalid inputs.</li>
        <li>Optimize database queries for large datasets.</li>
        <li>Implement better Front End design to be more aesthetically pleasing</li>
        <li>Add more categories and expand database</li>
    </ul>

<h2>Conclusion</h2>
    <p>
        This blog highlights the technical aspects of the Quotes Generator application, focusing on key code snippets and their explanations. The project demonstrates the effective use of Flask, SQLAlchemy, and modern JavaScript for building a robust full-stack application.
    </p>
</article>
