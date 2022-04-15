# Detailed Project Proposal

2022.04.03

2022.04.15

> The proposal includes the objectives and scope of the project and the schedule for the implementation. Students should consult their supervisors about the feasibility of their proposals. They should also state the estimated number of learning hours for each milestone of the project in the proposal.

### Project Title

Development of Library Management System with Separate Front-End and Back-End

### Supervisor

Leo C.Y. Yeung

### Student 1 (leader)

Xia Kaibo

## Aim

The purpose of this project is to explore and practice Web App development with front-end and back-end separation mode.

Spring Boot, MyBatis, MySQL will be used for constructing the back-end project. Vue.js, Element-UI will be used for constructing the front-end project. Several middlewares, such as Redis, Elasticsearch, MongoDB, RabbitMQ, will be integrated for advanced functions. In detailed, Redis for cache, Elasticsearch as the search engine, MongoDB as the NoSQL database, RabbitMQ for the Message Queue.

I choose the library management system as the practical case basing on the development mode and the corresponding frameworks and middlewares.

Through user authentication and authorization, it will realize simple book searching, checking and borrowing functions from the readers' perspective, as well as book searching and management, book borrowing request processing, and other functions from the administrator's perspective.

It is also an important practice to deploy the front-end and back-end projects on the cloud server, making it accessible from the Internet.

## Brief Literature Review

The Internet is an indispensable part of our daily life. Its development has significantly influenced many fields like industry, education, government, entertainment, and people’s personal and working life [1]. For example, instant messaging, online meetings, watching video online and other activities are inseparable from the Internet.

World Wide Web, or Web for short, plays an crucial role in Internet. And the front-end and back-end separation mode is an important part of Web application development.

The front-end and back-end separation mode is the industry standard method for Web application development today. It constructs a solid foundation for massive distributed architecture, elastic computing architecture, micro-service architecture, and multi-terminal services.

In a traditional Java Web project, JSP (Java Server Page) was used to display information on the web page. As the book *The Java Web Services Tutorial*, which was published in 2002, said, "A JSP page is a text-based document that contains two types of text: static template data, which can be expressed in any text-based format, and JSP elements, which construct dynamic content [2]."

It shows that the display code and data processing code in a traditional Java Web project are highly mixed. In another word, the coupling is too high, which increases the workload of the development work. In addition, JSP itself has certain limitations, causing the slow page response speed. As another paper said, since static and dynamic resources are mixed together in the server, the pressure of the server is also quite high [3].

But things changed a lot after over 10 years. In the more modern front-end and back-end separation mode, as the authors said in a paper in 2017, the back-end executes the service logic and processes the data under the controller, also provides the interfaces to the outsiders. And the front-end is mainly responsible for the data display and request responses [4]. Therefore, the separating of front-end and back-end achieves the decoupling of them.

Under the design idea of front-end and back-end separation, with the help of some brand new frameworks, the development process can be conducted faster and more convenient, as the frameworks can construct the project skeleton for us [5]. In the field of Java back-end development, the Spring series open source frameworks improve the development efficiency of developers and the maintainability of the system. In addition, the front-end has also become engineered, and front-end frameworks such as Angular, React, and Vue have also appeared one after another. They keep the code organized and make the web or app more agile and extensible [5].

Apart from the development mode and related techniques I aim to explore and practice in this project, the library management system is also an indispensable part. It is mentioned that with the advent of the Internet age, many fields have been influenced. Now library management system exists in every education related institutes [6]. 

As the paper *Open source library management system software: a review* mentioned, the library management system software packages should have some essential components. The first component is the traditional services provided by the libraries, that is the acquisitions of the books. The ordering, cataloging, circulation of books are in this component. The second component is the inter-library loan management system, for requesting some needed but not held materials from other libraries. The third component is the e-materials and digital media managing system. And the last component, the user account management feature, security system, also the statistical and administrative related features [6].

  

#### References

[1] S. Murugesan, Y. Deshpande, S. Hansen and A. Ginige, "Web engineering: A new discipline for development of web-based systems," *Web Engineering*, pp. 3-13, 2001. "

[2] E. Armstrong, S. Bodoff, D. Carson, M. Fisher, D. Green and K. Haase, The Java Web Services Tutorial. Addison-Wesley, 2002.

[3] Y. Gong, F. Gu, K. Chen and F. Wang, "The Architecture of Micro-services and the Separation of Frond-end and Back-end Applied in a Campus Information System," *2020 IEEE International Conference on Advances in Electrical Engineering and Computer Applications (AEECA)*, pp. 321-324, 2020.

[4] K. Liu, J. Jiang, X. Ding and H. Sun, "Design and Development of Management Information System for Research Project Process Based on Front-End and Back-End Separation," *2017 International Conference on Computing Intelligence and Information System (CIIS)*, pp. 338-342, 2017.

[5] S. Guan, W. Hu and H. Zhou, "Front-end and Back-end Separation - React Based Framework for Networked Remote Control Laboratory," *2018 37th Chinese Control Conference (CCC)*, pp. 6314-6319, 2018.

## Proposed Methodology

#### Back-End

- Use Spring Boot as the basic back-end framework
- Use Mybatis as the persistence layer framework
- Use MySQL as the database
- Use Redis for new reader registration
- Use Spring Security and JWT for user login
- Use Elasticsearch for book information search
- ...

#### Front-End

- Use Vue.js as the front-end framework
- Use Element UI for the front-end components 
- Use Axios for sending HTTP request to back-end
- ...

#### Deployment

- Buy a cloud server to deploy the application
- Use Nginx as the front-end server
- Use Docker to deploy back-end application
- ...

## Milestones

|      |                            Tasks                             | Estimated completion time | Estimated number of learning hours |
| :--: | :----------------------------------------------------------: | :-----------------------: | :--------------------------------: |
|  1   |        System functions design, techniques selection         |         Apr. 1st          |                 20                 |
|  2   |             Refer to the database design example             |         Apr. 5th          |                 10                 |
|  3   |       Database tables creation and test data insertion       |         Apr. 10th         |                 10                 |
|  4   | Back-end project creation, basic book CRUD functions realization |         Apr. 20th         |                 30                 |
|  5   | Front-end project creation, page layout design and basic user operation logic implementation |         Apr. 30th         |                 50                 |
|  6   | Realize the Cross-Origin Resource Sharing, connect the front-end and back-end |         May 30th          |                 10                 |
|  7   | Realize the advanced functions one by one, by repeating the "front-end design, back-end programming and database tables creation" process |         July 10th         |                100                 |
|  8   | Try to crawl some book information from avaliable API and store them in the database |         July 15th         |                 20                 |
|  9   | Try to generate the reader's name, ID, borrowing history and other information, and store them in the database |         July 20th         |                 10                 |
|  10  | Complete the deployment of front-end and back-end projects on the server |         July 30th         |                 40                 |
|      |                                                              |                           |             Total: 300             |



## Deliverables

|      |                            Items                             |
| :--: | :----------------------------------------------------------: |
|  1   |     Register and login function (readers'  perspective)      |
|  2   | Searching book and checking detailed  information  function (readers' perspective) |
|  3   | Choosing  books and making borrowing request function (readers'  perspective) |
|  4   | Checking personal borrowing records function (readers'  perspective) |
|  5   | Managing book information (CRUD) function (administrator's  perspective) |
|  6   | Handling borrowing requests function (administrator's  perspective) |
|  7   | Handling book returning function (administrator's  perspective) |
|  8   | Checking books' lending records function (administrator's  perspective) |
|  9   | Checking readers'  borrowing records  function (administrator's perspective) |
|  10  | Managing  users' permissions  function (administrator's perspective) |













