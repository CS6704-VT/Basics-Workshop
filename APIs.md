# APIs

People can communicate with each other by expressing thoughts, needs, and ideas through language (written and spoken), gestures, or facial expressions. At the same time, human interaction with computers, apps, and websites requires _user interface_ (UI) components –-- i.e., a screen with a menu and graphical elements, a keyboard, and a mouse.

Software, on the other hand, does not need a graphical user interface to talk to other software. To communicate and exchange data and functionalities, programs use machine-readable interfaces called **_application programming interfaces_** (APIs).

An API is a set of programming code that enables data transmission between one software product and another. It also contains the terms of this data exchange. The working principle of an API is commonly expressed through the request-response communication between a client and a server. The _client_ is any front-end application that a user interacts with. The _server_ is in charge of backend logic and database operations. In this scenario, an API works as a middle layer between the client and the server, making it possible to send data requests and responses.

## REST APIs

There are many different types of APIs. One of the most common are REST or RESTful (representational state transfer) APIs, which adhere to a set of architectural constraints. When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation), HTML, XLT, Python, PHP, or plain text. JSON is the most generally popular file format to use because, despite its name, it’s language-agnostic, as well as readable by both humans and machines. These APIs also use HTTP requests to work with resources, most notably POST, GET, PUT, and DELETE corresponding with CRUD (create, read, update, delete) operations.

Many software products and services provide REST APIs for developers to use and incorporate into other technical projects. For example, the [GitHub REST API](https://docs.github.com/en/rest) allows users to build scripts and applications that automate processes, integrate with GitHub, and extend GitHub. The GitHub API is also commonly leveraged in research to mine data from open source repositories and investigate a wide variety of other SE concepts--which can have various advantages and disadvantages [3]. We will read a number of papers in class that use this methodology, and you might want to consider using it for your own project! 

## 📝 Activity: Practice using the GitHub REST API!

There are many programming language libraries that act as wrappers for the GitHub REST API, however this activity will focus on using a simplified bash version. To set up, you will need to first complete the following tasks based on previous workshop activities:

1. Run the following commands to install the bash GitHub API scripts (you should have installed wget in the Package Managers notebook).
```bash|{type: 'command'}
wget https://gist.githubusercontent.com/mbohun/b161521b2440b9f08b59/raw/ccb2b0187dff124a129700d2cd4642e7007e8e1f/githubapi-get_json.sh
wget https://gist.githubusercontent.com/mbohun/b161521b2440b9f08b59/raw/ccb2b0187dff124a129700d2cd4642e7007e8e1f/githubapi-get.sh
```

2. Set up an environment variable named `$GITHUBTOKEN` with your GitHub personal access token (`export GITHUBTOKEN=<token>`)

3. Make the githubapi-get bash files executable (`chmod a+x <file>`)

Next, complete the following to practice retreiving data from the GitHub API.

This command will list all of your GitHub repositories:
```bash|{type: 'command'}
./githubapi-get.sh $GITHUBTOKEN /users/<username>/repos
```

This command will list all of your GitHub repositories sorted alphabetically by name:
```bash|{type: 'command'}
./githubapi-get.sh $GITHUBTOKEN /users/<username>/repos | grep '"name":' |sort
```

This command will list the commit messages for commits to the repository for this workshop:
```bash|{type: 'command'}
./githubapi-get.sh $GITHUBTOKEN /repos/CS6704-VT/Basics-Workshop/commits | grep '"message":'
```

This command lists the titles for all of the open pull requests for the Octocat Hello World repo:
```bash|{type: 'command'}
./githubapi-get.sh $GITHUBTOKEN /repos/octocat/Hello-World/pulls?state=open | grep '"title":'
```

Using what you know about bash scripts, APIs, and GitHub, come up with *two* queries to collect different types of information from GitHub repositories. Put the generated output of these queries as `.json` files with descriptive names and add the scripts used into a separate file named `scripts.txt` (or `scripts.sh` if you wrote them as a bash file) with a description of what they do. Add these to your workshop repository for submission.

## [Project Management ⏭️](Project.md)


[1] https://www.altexsoft.com/blog/what-is-api-definition-types-specifications-documentation/
[2] https://www.redhat.com/en/topics/api/what-is-a-rest-api
[3] Kalliamvakou, Eirini, et al. "The promises and perils of mining github." Proceedings of the 11th working conference on mining software repositories. 2014.