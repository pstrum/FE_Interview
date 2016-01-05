# Front-End Developer Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

Note: Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## General Questions

### What did you learn yesterday/this week?

### What excites or interests you about coding?

The most exciting aspect to coding, for me, is developing creative solutions to problems. I am a problem solver, when there is a problem to be solved it makes me excited. When that problem has to do with making the web better, I get even more excited. 

My interest in code can be broken down into the languages that I use every day.
**HTML**
I love structure. Having an organized and semantic document makes me excited, and for that document to be accessible to all users of the Internet is a goal I continually strive for. 
**CSS**
I am a visual person. I love design and keeping up with the latest trends and software. What gets me exctied about CSS is creating user interface components that are scalable and reusable. Keeping my styles separate from the document is really, really important to me.
**JavaScript**
I studied music for a long time. When I began to program a few years ago I noticed that both writing music and programming have a similar marriage of syntax and math. I think the my love for solving problems using those elements are a big reason why I have fallen for JavaScript.

### What is a recent technical challenge you experienced and how did you solve it?

I recently had to take an array of objects that populated a timeline view and create a way to add a header element for a certain property of each object--the month. You can imagine a typical blog timeline with the month of the latest post at the top and then another month farther down for the previous posts, and so forth. I needed to create this with my array of objects and change the display. This was using AngularJS.

I solved the problem by sorting the array based on the month within the `dateModified` property of each object. Then, I made the array into a two dimensional array separating the objects into groups by month. I did this by looping through the array and checking whether the current value for month was the same as the previous. If it was different, then slice the array.

Finally, using angular I did an `ng-repeat` for each month in the `vm.months` array and then another `ng-repeat` inside for each post in a month.

### What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?

### Talk about your preferred development environment.

So, this is how I have been setting up my development environment lately:

1. Set up a Repo on Github and make a new project directory on my computer. Git init.
2. Build out the folder structure for the project.
3. Gulp. Decide the bare minimum of what you need Gulp to be watching. Usually this will be a server, Sass, HTML, Webpack, and Watch task.
4. npm install. At this point I need some dependencies to get up and running.
5. I set up my `index.html` file with boilerplate structre. If it is an Angular app, then I set up and ng-app directive.
6. Style Guide. This is an important part to my development process.
7. CSS/Sass. Setup the Sass directory layout and ititial functions.

At this point I'm rocking and rolling. If the app has a front end web framework I'll set that up now and layout the directory structure. Webpack will also get set up now, but if I'm developing from scratch my focus in on the presentation layer first--so I'll get into that a bit later. 

### Which version control systems are you familiar with?

### Can you describe your workflow when you create a web page?

### If you have 5 different stylesheets, how would you best integrate them into the site?

### Can you describe the difference between progressive enhancement and graceful degradation?

Graceful degradation is **maintaining a website in legacy browsers when a large portion of it is not able to work**. The perspective is that you develop with the latest and greatest browsers and then think about support for older browsers towards the end of the development cycle.

Progressive enhancement is all about making sure **any user has access to your content**. The perspective is that content is what is most important, so making sure your markup is conveying the greatest level of detail is essential.

Although progressive enhancement is a game changer, it is also pretty much common sense. The reason why graceful degradation stuck around was because we were developing for the latest browsers and not developing for access to content.

Content reigns king!

### How would you optimize a website's assets/resources?

### How many resources will a browser download from a given domain at a time?

- What are the exceptions?

### Name 3 ways to decrease page load (perceived or actual load time).

### If you jumped on a project and they used tabs and you used spaces, what would you do?

### Describe how you would create a simple slideshow page.

### If you could master one technology this year, what would it be?

### Explain the importance of standards and standards bodies.

### What is Flash of Unstyled Content? How do you avoid FOUC?

### Explain what ARIA and screenreaders are, and how to make a website accessible.

### Explain some of the pros and cons for CSS animations versus JavaScript animations.

### What does CORS stand for and what issue does it address?
