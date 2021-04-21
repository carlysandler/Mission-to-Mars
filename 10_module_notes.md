# 0.0.2
Module 10 Roadmap
Looking Ahead
Module 10 Roadmap Image

In this module, you'll automate a web browser to visit different websites to extract data about the Mission to Mars. You'll store it in a NoSQL database, and then render the data in a web application created with Flask. The completed work will be displayed in your portfolio, which you will also create.

Web scraping is a method used by organizations worldwide to extract online data for analysis. Large companies employ web scraping to assess their reputations or track their competitors' online presence.

On a smaller scale, web scraping automates tedious tasks for personal projects. For example, if you're collecting current news on a specific subject, web scraping can make it a simple process. Instead of visiting each website and copying an article, a web scraping script will perform those actions and save the scraped data for later analysis.

What You Will Learn
By the end of this module, you will be able to: 

Gain familiarity with and use HTML elements, as well as class and id attributes, to identify content for web scraping.
Use BeautifulSoup and Splinter to automate a web browser and perform a web scrape.
Create a MongoDB database to store data from the web scrape.
Create a web application with Flask to display the data from the web scrape.
Create an HTML/CSS portfolio to showcase projects.
Use Bootstrap components to polish and customize the portfolio.
Planning Your Schedule
Here's a quick look at the lessons and assignments you'll cover in this module. You can use the time estimates to help pace your learning and plan your schedule.

Introduction (15 minutes)
Get Started Using Web Scraping Tools (1 hour)
Open the Window to the Internet (2 hours)
Automate a Web Browser and Perform a Web Scrape (3 hours)
Access Data in MongoDB (1 hour)
Display Data With Flask (3 hours)
Make It Pretty (3 hours)
Show It Off (2 hours)
Application (5 hours)

10.1.1
Install Your Tools
Robin is pretty excited about putting together this web-scraping project. Being able to get the latest news and updates with the click of a button? That's a really useful tool for someone who wants to keep up with the Mission to Mars.

First things first, though—preparation. Robin needs to download a few libraries and tools that she'll need when she's ready to start scraping data: Splinter to automate a web browser, BeautifulSoup to parse and extract the data, and MongoDB to hold the data that has been gathered.
With all of the information available on the web, people are able to stay up-to-date with almost every subject out there. What if a person wants to narrow their focus to a single topic? Are there tools that would make gathering the latest data easier?

Robin, who loves astronomy and wants to work for NASA one day, has decided to use a specific method of gathering the latest data: web scraping. Using this technique, she has the ability to pull data from multiple websites, store it in a database, then present the collected data in a central location: a webpage.

Use the web scraping method to extract and store online data into MongoDB.

IMPORTANT
Before installing new tools, open your terminal and make sure your Python coding environment is active.

Let's get the tools we'll need to complete this web-scraping project: Splinter, BeautifulSoup, and MongoDB.

Splinter
Splinter is the tool that will automate our web browser as we begin scraping. This means that it will open the browser, visit a webpage, and then interact with it (such as logging in or searching for an item). To do all of this, we'll need to install Splinter and ChromeDriver.

To install Splinter, open your terminal and make sure your coding environment is active. Then, run the command pip install splinter. Once that installation is complete, we'll install ChromeDriver.

IMPORTANT
To successfully use the ChromeDriver and scrape website data, a separate package will need to be installed into our virtual environment.

Web-Driver Manager
The web driver manager package will allow us to easily use a driver that to scrape websites without having to go through the complicated process of installing the stand alone ChromeDriver.

To install the manager make sure your are still in your active coding environment and run the command pip install webdriver_manager.

BeautifulSoup
To install BeautifulSoup, run the command pip install bs4 in your terminal. Make sure the environment you plan to work from is active first.

MongoDB
MongoDB (also known as Mongo) is a document database that thrives on chaos. Well, maybe it's not that extreme, but it is far more flexible when it comes to storing data than a structured database such as SQL. It's able to handle smaller, more personal projects as well as larger-scale projects that a company might require. For this module, Mongo is a better choice than SQL because the data we'll scrape from the web isn't going to be uniform. For example, how would we break down an image into rows and columns? We can't. But Mongo will store and access it as a document instead.

IMPORTANT
To install PyMongo, first open a terminal window (make sure your virtual environment is active) and execute the "pip install pymongo" command. PyMongo is the tool that allow developers to use Python with Mongo.

Now let's install MongoDB.

Windows
To install Mongo on your Windows computer, follow the instructions in the official documentation (Links to an external site.). Be sure to follow all of the steps listed for installing the MongoDB Community Edition.

Adding a Data Directory to Root
You'll also need to add the data directory to your root directory on your computer; otherwise, MongoDB won't run. Open your Anaconda Prompt terminal, then navigate to your root directory with cd c:\.

Bash terminal navigating to the c: directory

Next, we want to make a directory with the command mkdir data\db.

Bash terminal command creating a data/db directory.

This is the default location for Mongo's databases. Without this, Mongo won't have a designated spot to create collections and store data. It will refuse to run, no matter how many cookies we offer it.

Configuration
You'll also want to add MongoDB's path to the PATH environment variables for your computer so that you can run and launch MongoDB easily from the command line.

First, locate the directory where you installed MongoDB. This is likely C:\\Program Files\\MongoDB\\Server\\\\bin. Copy this directory to your clipboard with CTRL + C.

Once the file path is highlighted, we can add it to our PATH environment variable. To update your Path, dig into your security settings on your computer. See the instructions below.



Next, the following video will aid in launching Mongo from your command line interface.



To test if this worked, close your current Anaconda Prompt window, and then reopen it and run this command: mongod. If Mongo continues to run in the terminal, it's been successfully installed—great job!

NOTE
There is no "b" in the mongod command.

Troubleshooting
If mongod didn't run and, instead, your Anaconda Prompt threw a "command not found" error, make sure you added MongoDB's bin directory to your PATH variable. When you navigate through your Windows Explorer to the MongoDB folder, make sure you click all the way through into the bin folder, then copy the path. Then, close out Anaconda Prompt and try running mongod again.

If mongod starts but closes after a series of prompts, make sure you created the \data\db directory in your root. MongoDB cannot run without this directory.

macOS
Installation
To install Mongo on your macOS computer, follow the instructions in the official documentation (Links to an external site.). Be sure to follow all of the steps listed for installing the MongoDB Community Edition.

Here are a few important tips during this installation:

It's best to use the Homebrew brew package for this installation. In your terminal, the installation command will start with brew tap.

Once Mongo is installed, we want to run it as a macOS service because doing so will automatically set system ulimit (Links to an external site.) values correctly.

NOTE
Mac users will use this line to create a database instance: brew services start mongodb-community@4.4 instead of mongod.

GITHUB
Navigate to GitHub and create a new repository to hold the code for this module. Name the new repo "Mission-to-Mars" and clone it into your class folder. Remember to add, commit, and push your code as you work through the module.

Additional Libraries
There are two final Python libraries required to run scraping code successfully: html5lib and lxml. Both packages are used to parse HTML in Python, which will be important as you traverse through different web pages to find and collect information.

To install these libraries, first make sure your coding environment is active. Then, type the following commands in your terminal to install them:

pip install html5lib
pip install lxml
NOTE
Some environments may already have these packages installed; that's totally fine, just continue on to the next section!

10.2.1
Use HTML Elements
Robin has gotten all of her tools installed and tested Mongo to make sure it's ready for data, but before she can really start pulling it off of the web, she needs to be able to identify where the data is stored within the HTML code.

Every webpage is built using hypertext markup language, more commonly known as HTML. Some sites are more sophisticated than others, but they all have the same basic structure. Each element of a page, such as a title or a paragraph, is wrapped in a tag. Each tag is specific to the element it's holding, and there are many different types of tags.

Let's take a closer look at HTML tags.
Think of a webpage as a window into the internet. HTML is the glass, boards, and blinds on that window. Just like there are many sizes and shapes to windows, each webpage has been customized to present users with a view into a different topic. Consider a weather report delivered through a weather site. Think of a news source or social media platform. Each of these examples are all built using custom HTML. Our first step will be to explore that design so that we can write a script that knows what it's looking at when it interacts with a webpage.

Open VS Code and create a file named index.html. This file can be saved to your desktop because it's just for practice.

In this blank HTML file put an exclamation point on the first line and press Enter. This should autofill the editor to contain everything we need for a basic HTML page.

<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <meta http-equiv="X-UA-Compatible" content="ie=edge">
 <title>Document</title>
</head>
<body>
</body>
</html>
In this code, each line of code is wrapped in a tag, such as <title>. Let's take a closer look at this tag to get a feel for HTML syntax.

HTML tags always begin with a left angle bracket (<), followed by the name of the tag (in our case, "title"). Once the name has been entered, the tag is then closed with a right angle bracket (>). This is only the first half of the completed tag, or the opening tag. We'll also need to add the closing tag.

A closing HTML tag is very similar to the opening tag, but the only difference is a single character, the forward slash inside the left angle bracket: </title>. Now that there are both opening and closing HTML title tags, you can add the title of the document.

For example, if you wanted your webpage title to be "Math Is Fun!" then the entire line of HTML code would look like this: <title>Math Is Fun!</title>.

NOTE
Sometimes you'll see tags like this: <title />. This isn't a new-fangled way of presenting HTML code, it's just a way of summarizing the tags and their contents. This is more commonly seen in written descriptors of HTML and not in live HTML code.

You'll see different tags referred to in the same manner as you learn how to create and customize webpages.

REWIND
HTML is a coding language used for creating webpages. It’s built using specific tags and arranging them in a nested order, a bit like building blocks. For example, if we wanted a header and a paragraph in the same section of a webpage, we would nest <h1 /> and <p /> tags inside a <div /> tag, with the <div /> tag acting as a box to hold the other pieces.

<div>
   <h1>Hello, world!</h1>
   <p>This is a great beginning.</p>
</div>

Most elements have opening and closing tags, which are identical except for the forward slash that begins the closing tag. The closing tags represent the end of that HTML element.
These tags are what define each element of this webpage. We can open this page right now, but it will be blank because we haven't added anything to it yet. Let's take a closer look at how these different elements work together.

Each HTML tag in this graphic is defined later in this section.

Let's define each HTML tag shown in the graphic:

<!DOCTYPE html> is a declaration, not a tag. It tells web browsers in which HTML version the document is written. This should always be the first line in an HTML document.

<head> is the opening tag that serves as a container for the setup elements. Jupyter Notebook imports occur in the top cell whereas Python imports occur at the top of the code. HTML imports (e.g., a stylesheet or a library) will be within the <head>.

<meta> is short for "metadata" and tells the web browser basic information, such as page width.

<title> and </title> are the opening and closing tags that serve as a container for the page title displayed on the tab at the top of your web browser. In the example above, the title is "Document" and would appear like so in the browser:

The document title appears at the top of the web browser.

</head> is the closing tag for the <head> tag, much like the end of a code block in Python.

<body> and </body> are opening and closing tags. They also serve as a container, but for data we can see (navigation menus, lists, and paragraphs).

<html lang=”en”> and </html> are opening and closing tags that serve as a container for all elements within an HTML page.



IMPORTANT
Nesting is when HTML elements are contained within other elements. Picture a set of nesting dolls with each nested in proper order, by design, into the largest doll. It is the same for HTML tags—they must be in the correct order to not break the design of the webpage.



An easy way to keep the tags in visual order is by using indentation. Containers nested within other containers are indented by two to four spaces. This helps to keep our code clean and easy to understand.

Nested HTML code appears indented so it is easier to understand.

Let's take another look at this webpage, only with a few more elements added to it:

<!DOCTYPE html>
<html lang="en">
 <head>
   <meta charset="UTF-8" />
   <meta name="viewport" content="width=device-width, initial-scale=1.0" />
   <meta http-equiv="X-UA-Compatible" content="ie=edge" />
   <title>Document</title>
 </head>
 <body>
   <h1>Hello, world!</h1>
   <p>
     Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin aliquet
     iaculis lorem non sollicitudin. Fusce elementum ac elit finibus auctor.
     Curabitur orci sem, accumsan a diam sit amet, efficitur tristique velit.
   </p>
   <ul>
     <li>First list item</li>
     <li>Second list item</li>
     <li>Third list item</li>
   </ul>
 </body>
</html>
There are several more tags within the <body /> container. Add this new code to your index.html file and save it. Then, open the file by navigating to it and double-clicking it. Now you have a simple static webpage open in your browser, built from scratch. It's not super exciting yet, but that's okay. It's the innards of the page we're focusing on right now.



Let's review the new tags:

<h1 /> is a first-level header. The text in this tag will be displayed bigger and bolder than the rest of the page's text. There are many different headers available to use, from h1 to h6, with h1 returning the largest text.
<p /> is a paragraph tag, currently holding lorem ipsum sentences. (lorem ipsum is dummy text used to stage websites). More can be read about it on the Lorem Ipsum reference website (Links to an external site.).
<ul /> is an unordered list.
<li /> is a list item.


This is only a small taste of how many tags exist out there. Remember, these tags are all part of website customization. Without the variety available to use, websites would look plain and uninspired. The sites that Robin intends to scrape data from are far more sophisticated, using many more combinations of tags than what we've discussed here. Understanding the basic layout and how nesting and containers work is an important part of successful web scraping.

We know that when we scrape data from the web, we're simply pulling specific data from websites we've chosen. How do we specify the data? Let's say we want the latest news article from a Mars website. Before we can program our script to pull that data, we have to tell it where to look. Basically, our script would say, "look in this <div /> tag, then look inside that for a <p /> tag."

For example, if the webpage was a window, we would use our script to direct it to a certain pane.

The script specifies that data should be pulled from the bottom center pane of the webpage.

Once it found that pane, we can also tell it to look even closer, such as at the bottom-center pane.

The script specifies that data should be pulled from a selected spot within the bottom center pane of the webpage.

That's a simple way of putting it, but we'll dive more deeply into how web scraping works soon. Visit W3Schools' developer site for an extensive list of HTML tags (Links to an external site.).