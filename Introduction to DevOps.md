# <ins>DevOps Culture</ins> <font size=1>-[DevOps Handbook](https://github.com/adit0503/Reading_Books/blob/master/Devops/The%20DevOps%20Handbook%20-%20Gene%20Kim,%20Jez%20Humble,%20Patrick%20Debois,%20John%20Willis.pdf)</font>
---
>_DevOps is not a tool or a job title. It is a shared mindset_.

>_Tools we are using are not the solution to a cultural problem._



## <ins>__Definition of DevOps__</ins></font>
  >The term (development and operations) is an extension of __agile development environments__ that aims to enhance the process of software delivery as a whole.
  -Patrick Debois, 2009

  >[Extreme Programming](https://www.agilealliance.org/glossary/xp/#q=~(infinite~false~filters~(postType~(~'post~'aa_book~'aa_event_session~'aa_experience_report~'aa_glossary~'aa_research_paper~'aa_video)~tags~(~'xp))~searchTerm~'~sort~false~sortDirection~'asc~page~1)) paved the way for Agile development
  >[Agile Methods](https://www.jigsawacademy.com/blogs/product-management/types-of-agile-methodology/)

  - Consider this...
    - What if you could fail fast and roll back quickly?
    - What is you could test in-market instead of analyzing?
    - What if your application design allowed individual componenets to be replaced?
    - How quickly you can recover? The question is not how fast you can fail.


  - __The Agile Mainfesto__
    - __Individuals__ and __interactions__ over processes and tools
    - __Working software__ over comprehensive documentation
    - __Customer colloboration__ over contract negotiation
    - __Responding to change__ over following plan


  - _DevOps defined_:
    - Recognition that working in silos doesn't work
    - Development and operations engineer working together
    - Following lean and agile principles
    - Delivering software in a rapid and continuous manner


  - _DevOps requires_;
    - A change in culture,
    - A new application design,
    - Leveraging automation,
    - Programmable platform


  - _What DevOps is not_,
    - Not simply combining development and operations
    - Not a seperate team
    - Not a tool
    - Not one size fits all &rarr; There no one set of measurements


  - To _spread the mindset_ and _the culturel changes_ in the company;
    - __Think Differently__
      - Social Coding
      - Working in small bathes
      - Minimum Viable Product
    - __Work Differently__
      - Test Driven Development
      - Behaviour Driven Development
      - Continuous Integration
      - Continous Delivery
    - __Organize Differently__
      - Organization Impacts Design
    - __Measure Differently__
      - Measure what matters

---

## <ins>__Characteristics of DevOps__</ins>

  - __What is the goal?__
    1. Smart Experimentation
    2. Moving in Market
      - With maximum velocity and minimum risk
      - Gaining quick, valuable insights


  - __Application Evolution__
    - __Delivery__ : _Waterfall_ &rarr; _Agile_ &rarr; _DevOps_
    - __Architecture__ : _Monoliths_ &rarr; _SOA_ &rarr; _Microservices_
    - __Infrastructure__ : _Physical Servers_ &rarr; _Virtual Machines_ &rarr; _Containers_


  - __Traditional Waterfall Development__
    1. Requirements
    2. Design
    3. Code
    4. Integration
    5. Test
    6. Deploy

---

## <ins>__Social Coding Principles__</ins>

  * Open Source for internal projects
     - Discuss eith the repo owner
     - Open an __issue__ and assign it to yourself
     - __Fork__ the code and make your changes
     - Issue a __Pull Request__ to review and merge back


  * _Pair Programming_
    - Two programmers on one workstation
    - The driver is typing
    - The navigator is reviewing
    - Every 20 minutes they switches


  * _Git Repository Guidelines_
    - Create a seperate Git repository for every components (Microservices, ...)
    - Create a new branch for every Issue
    - Use Pull Requests to merge to master
    - Every Pull Request is an opportunity for code review


  * _Minimum Viable Product_
    - MVP is an experiment to test your value hypothesis and learn
    - MVP is a tool for learning


  * _Test Driven Development_
    > If it's woth building, it's worth testing. If it's not worth testing, why are you wasting your time working on it?
    -Scott Ambler

    - You write the tests first then you write the code to make the test pass
    - This keeps you focused on the purpose of the code
    - Code is no use if your client can't call it
    - Follows the path [__Red__ - __Green__ - __Refactor__](https://medium.com/@tunkhine126/red-green-refactor-42b5b643b506)
    - In order to create a DevOps CI/CD pipeline, all testing must be automated


  * _Behaviour Driven Development_
    - Great for integration testing
    - Uses a syntax both developers and steakholders can understand
    - BDD ensures the big picture is working well together
    - Document the behaviour using Gherkin syntax
      - Add acceptance criteria to every user story
      - Use Gherkin to do that
      - Indisputable definition of _done_


  * _Cloud Native Microservices_

    - Cloud native architecture is a collection of independently deployable microservices.
    ![Monlith_vs_Microservices](<Insert The Path_Here>)
    - Microservices are loosely coupled services, designed for scalability and communication with API's.

    >   __Definiton Microservices__
  ... the microservice architectural style is an approach to developing a single application as a __suite of small services__, each __running in its own prcesses__ and communicating wtih lightweight mechanisms, often an HTTP resource API (generally RestAPI). These services are __built  around business capabilities__ and __independently deployable__ by fully automated deployment machinery.
  -Martin Fowler and James Lewis



  * _Design for Failure_
    Failure is inevitable so prepare for impact.

    - Embrace failures
    - How to avoid
    - Operational concerns
    - Plan to be throttled
    - Plan to retry
      - Build microservices to communicate with each other patiently. For instance, you application should wait and try again. The key here is to wait exponantially in each try.
    - Degrade gracefully
    - Cache when appropriate
    - __Chaos Engineering__
      - Known as monkey testing
      - You deliberately kill services
      - _Netflix_ created __The Simian Army__ tools

---

## <ins>__Taylorism and Working in Silos__</ins>

  * _DevOps Way of Working_
    - Culture of teaming and collaboration
    - Agile development as a shared discipline
    - Automation relentlessly is rewarded
    - Push smaller releases faster minimizes risks and maximize learning


  * _Taylorism_
    - Adoption of command and control management
    - Organizations divided into functional silos
    - Decision-making is seperated from work


  * <ins>_Impact of Taylorism on Information Technology_</ins>
    - Project Management (Planners),
    - Architects,
    - Developers,
    - Testers,
    - Operations,
    - Security,
    all has seperated tasks.

    >Taylorism is not appropriate for IT.

    >As Steve Jobs stated "You can not hire smart people and tell them what to do". Abandon command and control.


  * _Reqired DevOps Behaviours_
    - Organizational silos and hand offs &cross;
    - Shared ownership and high collaboration &check;
    - Fear of change &cross;
    - Risk management by embracing change &check;
    - Build once, hand crafted "snowflakes" &cross;
    - Ephemeral infrastructure as code &check;
    - Manual fulfillment &cross;
    - Automated self-service &check;
    - Alarms, callbacks, and escalations &cross;
    - Feedback loops and data-driven responses &check;


  * _Infrastructure as Code_
    - Described an executible textual format
    - Configure using that description
    - Configuration Management systems make this possible
    - <ins>__Never perform configurations manually__</ins>
    - Use version control system


  * _Ephemeral Immutable Infrastructure_
    - Server drift is a major source of failure
    - Servers are cattle not pets
    - Infrastructure is transient
    - Build through parallel infrastructure


  * _Immutable Delivery via Containers_
    - Applications are packaged in containers
    - Same container that runs in production can be run locally
    - Dependencies are contained
    - No variance limits side-effects
    - Rolling updates with immediate roll-back
    * <ins>_Immutable Way of Working_</ins>
      - You never make changes to a running container
      - Make changes to the image
      - Then redeploy a new container
      - Keep images up to date not the running container


  * _Continuous Integration vs. Continuous Delivery_
    - CI/CD is not one thing
    - <font size=4>__Continuous Integration (CI)__</font>
      - Continously building, testing and merging to master
      - Developers integrate code often
      - Developers work in short-lived feature branches
      - Each check-in is verified by an automated build
      - Working in small batches &rarr;
      - Commiting regularly &rarr; Reduces the complexity of changes and merge conflicts
      - Using pull requests &rarr; Allow team members to communicate via code reviews and every changes pass through more than one set of eyes
      -  Commiting all changes daily
      - _CI Automation_
        - Build and test every pull request
        - Use CI tools that monitor version control
        - Test should run after each build
        - Never merge a pull request with failin tests
    - _Benefits of Continous Integration_
      - Faster reaction times to changes because you automated tests and this gives you faster action-reaction instincts
      - Reduced code integration risks
      - Higher code quality
      - Master branch should always be deployable.
    - <font size=4>__Continuous Delivery (CD)__</font>
      - Continously deploying to a production-like environment
      - The master branch should always be ready to deploy
      - You need a way to know if something will "break the build"
      - Deliver every change to a production-like environment
    - <font size=4>__CI/CD Pipeline__</font>
      - Automated gates that create a pipeline of checks;
        - Unit Testing
        - Code Quality Checks
        - Integration Testing
        - Security Testing
        - Vulnerability Scanning
        - Package Signing
      - Needs for CI/CD Pipeline;
        - A code repository
        - A build server (ex. GitHub Actions)
        - An Integration Server
        - An Artifact Repository (ex. Docker Images)
        - Automatic Configuration and Deployment
      - Key Principles
        - Build Quilty In
        - Work in Small Batches
        - Computers perform repetitive tasts, people solve problems
        - Relentlesly pursue continuous improvement
        - Everyone is responsible

---

## <ins>__Organizational Impacts of DevOps__</ins>

  - _Conway's Law_

    >Any organization tahat designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.
    -Melvin Conway, Datamation, 1968

  - _There is No DevOps Team_
    - A cultural transformation on an organizational scale
    - Development and operation engineers working together
    - Following lean and agile principles
    - Cross-functional teams with opennes, transparency and trust as pillars
    - Organizations need to have small, dedicated, cross-functional, self-organizing teams to successfully implement DevOps.
    - Conway’s Law implies that a company’s design results are a direct reflection of the company’s communication structure.
    - Instead of the traditional structure organized around technology, successful DevOps teams should be organized around business domains. Each team should have its own mission that aligns with a business domain.
    - DevOps is a mindset that the whole organization adopts.
    - DevOps solves problems caused by siloed teams.
    - DevOps is the practice of development and operations engineers working together during the entire software lifecycle, following lean and Agile principles that allow them to deliver high-quality results.
    - Actions without consequences can lead to apathy.
    - Allowing teams to feel the effect of their actions fosters empathy, resulting in higher-quality work.
    - The organizational objective of DevOps is to attain a shared mindset and empower everyone to deliver customer value.

  - _Measuring DevOps_
    - A baseline provides a concrete  number for comparison as you implement your DevOps changes
    - __Metric goals__ allow you to reason about these numbers and judge the success of your progress
    - _Vanity Metrics_
    - _Actionable Metrics_
      - Reduce time to market new features
      - Increase overall availability
      - Reduce the time to deploy
      - Defects detected before production
      - More efficient use of infrastructure
      - Quicker performance feedback
      - __Mean Lead Time__ &rarr; How long it takes an idea to get to production
      - __Release Frequency__
      - __Change Failure Rate__ &rarr; When you push things out how often they fail
      - __Mean Time to Failure__

  - _DevOps Culture_
    - Actively Learn Information on Your Field
    - Nothing to Be Judged for a Failure - Blameless Culture
    - Share the Responsibilities
    - Be cross-reader
    - Create A New Ideas List


---
