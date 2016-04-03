# M101J

Homework: Homework 3.2 (MongoProc)
===

Making your blog accept posts

In this homework you will be enhancing the blog project to insert entries into the posts collection. After this, the blog will work. It will allow you to add blog posts with a title, body and tags and have it be added to the posts collection properly.

We have provided the code that creates users and allows you to login (the assignment from last week). To get started, please download blog.zip from the Download Handout link and unpack. You will be using these file for this homework and for homework 3.3.

The areas where you need to add code are marked with "XXX". You need only touch the BlogPostDAO class. There are three locations for you to add code for this problem. Scan that file for XXX to see where to work.

Here is an example of valid blog post:

> db.posts.find().pretty()
{
    "_id" : ObjectId("513d396da0ee6e58987bae74"),
    "title" : "Martians to use MongoDB",
    "author" : "andrew",
    "body" : "Representatives from the planet Mars announced today that the planet would adopt MongoDB as a planetary standard. Head Martian Flipblip said that MongoDB was the perfect tool to store the diversity of life that exists on Mars.",
    "permalink" : "martians_to_use_mongodb",
    "tags" : [
        "martians",
        "seti",
        "nosql",
        "worlddomination"
    ],
    "comments" : [ ],
    "date" : ISODate("2013-03-11T01:54:53.692Z")
}

Note: You must add at least one post like the one above to the posts collection before running the blog.

As a reminder, to run your blog you type:

mvn compile exec:java -Dexec.mainClass=course.BlogController

Or, use an IDE to run it.

To play with the blog you can navigate to the following URLs:

http://localhost:8082/
http://localhost:8082/signup
http://localhost:8082/login
http://localhost:8082/newpost

Ok, now it's time to validate that you got it all working using MongoProc. To do that, locate this problem in the homework browser pane in MongoProc. When you believe you have solved the problem correctly, test your solution using the "Test" button. When you see confirmation that you have completed the assignment successfully in the feedback window, you can Turn in your assignment.

You will see a message below about your number of submissions at the bottom of this page, but you must submit this assignment using MongoProc.

Tip: Be sure to go to settings in mongoProc, and point mongod1 to your mongod (probably localhost:27017), and web1 to your web url (probably localhost:8082)

Homework: Homework 3.3 (MongoProc)
=======
Making your blog accept posts
In this homework you will add code to your blog so that it accepts comments. You will be using the same code as you downloaded for HW 3.2.

Once again, the area where you need to work is marked with an XXX in the BlogPostsDAO class. There is only a single location you need to work to insert comments. You don't need to figure out how to retrieve comments for this homework because the code you did in 3.2 already pulls the entire blog post (unless you specifically projected to eliminate the comments) and we gave you the code in the template that pulls them out of the JSON document.

This assignment has fairly little code, but it's a little more subtle than the previous assignment because you are going to be manipulating an array within the Mongo document. For the sake of clarity, here is a document out of the posts collection from a working project that also has comments.

{
	"_id" : ObjectId("513d396da0ee6e58987bae74"),
	"author" : "andrew",
	"body" : "Representatives from the planet Mars announced today that the planet would adopt MongoDB as a planetary standard. Head Martian Flipblip said that MongoDB was the perfect tool to store the diversity of life that exists on Mars.",
	"comments" : [
		{
			"author" : "Larry Ellison",
			"body" : "While I am deeply disappointed that Mars won't be standardizing on a relational database, I understand their desire to adopt a more modern technology for the red planet.",
			"email" : "larry@oracle.com"
		},
		{
			"author" : "Salvatore Sanfilippo",
			"body" : "This make no sense to me. Redis would have worked fine."
		}
	],
	"date" : ISODate("2013-03-11T01:54:53.692Z"),
	"permalink" : "martians_to_use_mongodb",
	"tags" : [
		"martians",
		"seti",
		"nosql",
		"worlddomination"
	],
	"title" : "Martians to use MongoDB"
}


Note that you add comments in this blog from the blog post detail page, which appears at

http://localhost:8082/post/post_slug

where post_slug is the permalink. For the sake of eliminating doubt, the permalink for the example blog post above is http://localhost:8082/post/martians_to_use_mongodb
As a reminder, to run your blog you type:

mvn compile exec:java -Dexec.mainClass=course.BlogController


Or, use an IDE to run it.

To play with the blog you can navigate to the following URLs

http://localhost:8082/
http://localhost:8082/signup
http://localhost:8082/login
http://localhost:8082/newpost


When you believe you have solved the problem correctly, test your solution in MongoProc. When you see confirmation that your solution is correct, turn it in.

You will see a message below about the number of times you have submitted a solution through MongoProc. You should not submit until testing in MongoProc confirms that your solution is correct. 