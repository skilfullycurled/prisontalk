Scrapers and Parsers for prisontalk.com forums.  My approach is actually to download pages of html and then parse them after the fact.  Parsers have ‘test pages’ in the examples folder which cover all potential errors, differences, and edge cases between pages.  

**IMPORTANT:** *PLEASE MAKE SURE TO SEE NOTE BELOW REGARDING THE CREATION OF USERNAMES*

The notebooks contained extract the following data:

Prison Talk Scrapers

1. Log in/out
2. Get list of forums.
3. Get list of threads in forums.
4. Download HTML pages of posts.
5. Automatic randomized breaks (e.g. throttling, looking like a human)
4. Logging progress
5. Sending email progress reports
6. Sending critical failures as text messages

Prison Talk Forum List Parser

1. Forum number
2. Forum name
3. Number of threads
4. Number of posts
5. Description

Prison Talk Thread Parser

1. Thread ID
2. Thread title
3. Thread replies
4. Number of views

Prison Talk Archive Parser/Scraper

Prisontalk.com has an archive version which is *very* simple to parse.  This is to be used to parse the actual content of the thread which will be joined with other information which can only be obtained from the live site.

1. Date
2. Post ID
3. User
4. Post body

Prison Talk Thank You Scraper

Prison Talk has a gratitude mechanism in which users can ‘thank’ someone for their post.  This is one piece of information the live site contains which is not available on the archive.

1. Date of thanks
2. The post ID of the thanked post
3. Thanker username
4. Thanker user ID

Prison Talk Members List Parser

1. Member ID
2. Username
3. Role (e.g. admin)
4. Join date
5. Number of posts
6. Last visit
7. Profile pic
8. Birthday

Prison Talk User Profile Parser (requires login)

1. Username
2. Member ID
3. About Me
4. Last Post
5. Number of thanks received/given
6. Number of friends
7. Last visit
8. Join date

OTHER: Notebooks from a smaller version of this project which performs topic modeling of the data from the archive.  Can’t yet be simply ‘plugged in’ with the rest of the data but changes will be made so that it can be used in the future.

Prison Talk Topic Modeling  
Prison Talk Document Processing


###REGARDING USERNAMES AND LOGGING IN

There are some (only one if I recall) circumstances in which you may need to login in order scrape the pages.  You can find this out by simply using the site.  For reasons I’ll get to below, if you do not have to login to the site (even when simply exploring it) **don’t**.

So look in the code for places to add your username and password where necessary but note (and I cannot overstate this enough):  

**DO NOT UNDER ANY CIRCUMSTANCES DO THE FOLLOWING:**

1. Create more than one username from the same IP address.
2. Use any of the same or similar identifying information when creating a username and password.
3. Log-in with more than one username from the same IP address.

This will be detected, and they will request that they usernames be merged.  Repeated offenses will probably get you banned.  Please see the ‘cookies’ section in Prison Talk Scrapers.ipynb for more information.
