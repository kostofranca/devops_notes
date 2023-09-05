[//]: # (<details><summary><font size=4></font></summary></details>)


# What I Have Learned So Far

[//]: # (<details>)
  <summary><font size=4>General Knowladge</font></summary>

### SSH
  SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.

  SSH also refers to the suite of utilities that implement the SSH protocol. Secure Shell provides strong password authentication and public key authentication, as well as encrypted data communications between two computers connecting over an open network, such as the internet.

  In addition to providing strong encryption, SSH is widely used by network administrators to manage systems and applications remotely, enabling them to log in to another computer over a network, execute commands and move files from one computer to another.

### This Section Inclued Some Terms That You Will Face Frequently

* [**HELM**](https://www.freecodecamp.org/news/what-is-a-helm-chart-tutorial-for-kubernetes-beginners/)

* [What is a **.yaml** File and Where to Use It?](https://medium.com/codex/docker-compose-explained-3954baf495ec)

* **Hash Code** &rarr; A hash function is any function that can be used to map data of arbitrary size to fixed-size values.The values returned by a hash function are called hash values, hash codes, digests, or simply hashes.

* <font size=3>__How to Send E-mails Using Linux Terminal__</font>

    * [Source Video](https://www.youtube.com/watch?v=uNss377DK88&t=51s)  

      **__Installation and Configuration Commands__**
      <font size=1>After seting up an _Ubuntu_ Server run the below commands and complete the configuration steps</font>

        - `apt update`
        - `apt upgrade`
        - `apt install sudo`
        - `sudo apt-get install nano`
        - `sudo apt-get install postfix`  

        <font size=2>In the process of installation you will see some prompt to be configured;

          1. General Type of Mail Configuration
            - <ins>2. Internet Site</ins> &rarr; This is the default one. Just type `2` and press enter.
          2. System Mail Name
            - Put your domain name: `example.domain.com` Does' not matter what you put
          3. `cat /etc/postfix/main.cf` &rarr; The essential configuration file for postfix.</font>

        - `nano /etc/postfix/sasl/sasl_passwd` &rarr; To give the credentials below
          - `[smtp.gmail.com]:587 kasim.erbay@innovance.com.tr:<External_App_Password>`
        - `postmap /etc/postfix/sasl/sasl_passwd` &rarr; to create `.db` file
        - `chown root:root /etc/postfix/sasl/sasl_passwd /etc/postfix/sasl/sasl_passwd.db` &rarr; For security reasons
        - `chmod 0600 /etc/postfix/sasl/sasl_passwd /etc/postfix/sasl/sasl_passwd.db` &rarr; For security reasons
        - `nano /etc/postfix/main.cf` &rarr; Change `relayhost = [smtp.gmail.com]:587` and copy paste the following lines at the end of the file
          - ```
            smtp_sasl_auth_enable = yes
            smtp_sasl_security_options = noanonymous
            smtp_sasl_password_maps = hash:/etc/postfix/sasl/sasl_passwd
            smtp_tls_security_level = encrypt
            smtp_tls_CAfile = /etc/ssl/certs/ca-certificates.crt
            ```
        - `ls /etc/ssl/certs/ca-certificates.crt` &rarr; Check the certificate if exists
        - `apt install systemctl`
        - `systemctl restart postfix` &rarr; To see if any error occurs. Should go to next line.

        >From now on we could be able to send mails from terminal

        - `sendmail <MAIL_ADDRESS_TO_BE_SENT>`
          - `Subject: <SOME_SUBJECT>`
          - `<TEXT_HERE>`
          - `Ctrl + d`
        -

[//]: # (</details>)

<details>
  <summary><font size=4>Vim</font></summary>

### What is Vim?

Vim is a text editor for Unix that comes with Linux, BSD, and macOS. It is known to be fast and powerful, partly because it is a small program that can run in a terminal (although it has a graphical interface). It is mainly because it can be managed entirely without menus or a mouse with a keyboard.

* [What is Vim and It's Power?](https://www.loginradius.com/blog/engineering/vim-getting-started/)
* You should learn [Vim](https://www.openvim.com/).

</details>

<details>
  <summary><font size=4>Git and GitHub</font></summary>

### What is Git and GitHub?

Git is an open-source, version control tool created in 2005 by developers working on the Linux operating system; GitHub is a company founded in 2008 that makes tools which integrate with git. You do not need GitHub to use git, but you cannot use GitHub without using git. There are many other alternatives to GitHub, such as GitLab, BitBucket, and “host-your-own” solutions such as gogs and gittea. All of these are referred to in git-speak as “remotes”, and all are completely optional. You do not need to use a remote to use git, but it will make sharing your code with others easier.

<font size=4>**Useful Links for Learning Git and GitHub**</font>

* [Reading Material About Basic Git Commands](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
* [GitHub - Git](https://learngitbranching.js.org "GitHub")
* [Git Best Practices](https://sethrobertson.github.io/GitBestPractices/)


<font size=4>**Quick Git Tutorial**</font>

  \* Following the below commands below shows a quick tour for creating and using Git and GitHub locally and remotely

* ``mkdir <Project_File>`` &rarr; Create a directory in current working direcory
* ``touch README.md`` &rarr; Create a README file

> At this point you have a directory called `Project_File` which includes `README.md` file. We used Linux Bash Commands to handle above commands.

>For more information please learn linux commands. [Learning Linux commands](https://www.hostinger.com/tutorials/linux-commands) will boost your Git experience and the tools we will examine later.

* ``git init`` &rarr; Convert your directory to a Git repository
* ``git add README.md`` &rarr; Add your editted file/s to the [Staging Environment](https://www.geeksforgeeks.org/staging-in-git/)
* ``git commit`` &rarr; Let Git keeps track of your staged files
  - If you use ``git commit -m "<YOUR_COMMIT_MESSAGE>"``, you will write your commit messages directly instead of Vim editor

>Do not forget to use `git add <FILE_NAME>` command before you commit

Till now, we just made some changes locally. To use GitHub remotely, we will connect our local repository to remote repository with the following command;

* ``git remote add origin <GitHub_PAGE_LINK>`` &rarr; Connect our local repository to remote repository
  - Till now, we just made some changes locally. This command connects our local repository to remote one.

  - Be carefull ! You need to sign up to GitHub for this step. <GitHub_PAGE_LINK> are provided by GitHub itself.

* ``git remote -v`` &rarr; Check which GitHub account you are connected to.

  - This command should give an output like below. Otherwise go and check some stackoverflow pages for salvation.

  ``
  origin  https://github.com/<USER_NAME>/<REPOSITORY_NAME>.git (fetch)
  ``
  ``
  origin  https://github.com/<USER_NAME>/<REPOSITORY_NAME>.git (push)
  ``

>You might be wondering what that __origin__ word means in the command above. What happens is that when you clone a remote repository to your local machine, Git creates an alias for you. In nearly all cases this alias is called __origin__.

* ``git push origin master`` &rarr;  Send your local commits to GitHub and Voila! You are a Git master now. Not the branch one!

---
NOTE: You could first create a GitHub repository and then __clone__ it. After that you would be at the same page
with us for now. To __clone__;

* ``git clone <GitHub_Link>`` &rarr; Clone an existing GitHub repository to your local machine.
---
* ``git branch`` &rarr; Lists all the existed branches. If master branch is the only branch, the output should be like below;
  - ``
  C:\Users\...\<Project_File>>git branch
  ``
  ``* master``

* ``git branch <GIT_BRANCH_NAME>`` &rarr; Create a new branch called `<GIT_BRANCH_NAME>`

* ``git checkout <GIT_BRANCH_NAME>`` &rarr; Change your current working branch to `<GIT_BRANCH_NAME>`
  - ``git checkout -b <GIT_BRANCH_NAME>`` &rarr; Create a branch if not exists

* ``git push origin <GIT_BRANCH_NAME>`` &rarr; Send your changes on `<GIT_BRANCH_NAME>` to remote

* ``git branch -D <GIT_BRANCH_NAME>`` &rarr; Delete your current working branch locally

* ``git push origin --delete <GIT_BRANCH_NAME>`` &rarr; Delete your branch remotely

>Keep that in mind! You can not delete a branch without having checked out otherwise look the below image:
![Cutting the stick you hold](https://github.com/kasimerbay/Innovance-Internship/blob/master/1210-1240955295Hn8Q.jpg)
---

* ``git merge <GIT_BRANCH_NAME>`` &rarr; Pile up your commits on `<GIT_BRANCH_NAME>` and combines your current branch

* ``git pull origin master`` &rarr; Move your remote files and changes to your local

* ``git rebase <GIT_BRANCH_NAME>`` &rarr; Comming Soon...
  - Reading the official Git manual it states that rebase “reapplies commits on top o another base branch” , whereas merge “joins two or more development histories together”  In other words, the key difference between merge and rebase is that while merge preserves history as it happened, rebase rewrites it.

* `` git HEAD^`` &rarr; Move your `HEAD` file upward in the commitment tree.

* ``git branch -f master HEAD~3`` &rarr; Sends the HEAD to 3 commits above

</details>

<details>
  <summary><font size=4>Linux Network Layers</font></summary>

### Resources to Summarize Linux Network Layers


* <https://tldp.org/LDP/intro-linux/html/sect_10_01.html>
* <https://linux-kernel-labs.github.io/refs/heads/master/labs/networking.html>
* <https://www.linux.com/topic/networking/practical-networking-linux-admins-tcpip/>
* <https://www.geeksforgeeks.org/tcp-ip-model/?ref=lbp>

### Frequently Used Terms

* A _protocol_ is, simply put, a set of rules for communication.
  - In order to get data over the network, for instance an E-mail from your computer
	to some computer at the other end of the world, lots of different hard- and software
	needs to work together.

	All these pieces of hardware and the different software programs speak different languages.
	Imagine your E-mail program: it is able to talk to the computer operating system, through a
	specific protocol, but it is not able to talk to the computer hardware. We need a special
	program in the operating system that performs this function. In turn, the computer needs to
	be able to communicate with the telephone line or other Internet hookup method. And behind the
	scenes, network connection hardware needs to be able to communicate in order to pass your
	E-mail from one appliance to the other, all the way to the destination computer.

	All these different types of communication protocols are classified in 7 layers, which are
	known as _the Open Systems Interconnection Reference Model_, **the OSI Model** for short.

* ``hostname`` &rarr; this displays the hostname of your machine.
* ``ifconfig`` &rarr; this gives us the IP address of the device.
* ``netstat -a`` &rarr; this lists all the ports being used.

* The unique combination of IP address and Port number together are termed as **Socket**.
---
# The OSI Model's Layers

1. **Physical Layer**
  * The physical layer refers to your networking hardware: **Ethernet** and **wi-fi interfaces**, **cabling**, **switches**, whatever gadgets it takes to move your bits and the electricity to operate them.  

    <ins><font size=4>**The Functions of Physical Layer**</font></ins>
      - _Bit Synchronization_
        The physical layer provides the synchronization of the bits by providing a clock. This clock controls both sender and receiver thus providing synchronization at bit level.

        <ins>Note</ins>:
          CP, the clock pulse is the vibration of a quartz crystal located inside a computer for synchronizing the timing of hardware components.

      - _Bit Rate Control_
        The Physical layer also defines the transmission rate i.e. the number of bits sent per second.

      - _Physical Topologies_
        Physical layer specifies the way in which the different, devices/nodes are arranged in a network i.e. bus, star, or mesh topology.

      - _Transmission Mode_
        Physical layer also defines the way in which the data flows between the two connected devices. The various transmission modes possible are Simplex, half-duplex and full-duplex.

2. **Data Link Layer**
  * The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer. When a packet arrives in a network, it is the responsibility of DLL to transmit it to the Host using its MAC address.

    <ins><font size=4>**The Functions of Data Link Layer**</font></ins>
      - _Framing_
        Framing is a function of the data link layer. It provides a way for a sender to transmit a set of bits that are meaningful to the receiver. This can be accomplished by attaching special bit patterns to the beginning and end of the frame.

      - _Physical Addressing_
        After creating frames, the Data link layer adds physical addresses (MAC address) of the sender and/or receiver in the header of each frame.

      - _Error Control_
        Data link layer provides the mechanism of error control in which it detects and retransmits damaged or lost frames.

      - _Flow Control_
        The data rate must be constant on both sides else the data may get corrupted thus, flow control coordinates the amount of data that can be sent before receiving acknowledgement.

      - _Access Control_
        When a single communication channel is shared by multiple devices, the MAC sub-layer of the data link layer helps to determine which device has control over the channel at a given time.

3. **Network layer**
  * The network layer works for the transmission of data from one host to the other located in different networks. It also takes care of packet routing i.e. selection of the shortest path to transmit the packet, from the number of routes available. The sender & receiver’s IP addresses are placed in the header by the network layer

    <ins><font size=4>**The Functions of Network Layer**</font></ins>
      - _Routing_
        The network layer protocols determine which route is suitable from source to destination. This function of the network layer is known as routing.
      - _Logical Addressing_
        In order to identify each device on internetwork uniquely, the network layer defines an addressing scheme. The sender & receiver’s IP addresses are placed in the header by the network layer. Such an address distinguishes each device uniquely and universally.
      <ins>Note</ins>:
        Network layer is implemented by networking devices such as routers.


4. **Transport Layer**
  * The transport layer provides services to the application layer and takes services from the network layer. The data in the transport layer is referred to as Segments. It is responsible for the End to End Delivery of the complete message. The transport layer also provides the acknowledgement of the successful data transmission and re-transmits the data if an error is found.

    <ins><font size=4>**The Functions of Transport Layer**</font></ins>
      - _Segmentation and Reassembly_
        This layer accepts the message from the (session) layer, and breaks the message into smaller units. Each of the segments produced has a header associated with it. The transport layer at the destination station reassembles the message.

      - _Service Point Addressing_
        In order to deliver the message to the correct process, the transport layer header includes a type of address called service point address or port address. Thus by specifying this address, the transport layer makes sure that the message is delivered to the correct process.

    <ins><font size=4>**The Services Provided by The Transport Layer**</font></ins>
      - _Connection-Oriented Service_:
        It is a three-phase process that includes;
          – Connection Establishment
          – Data Transfer
          – Termination / disconnection

          In this type of transmission, the receiving device sends an acknowledgement, back to the source after a packet or group of packets is received. This type of transmission is reliable and secure.

      - _Connectionless Service_:
        It is a one-phase process and includes Data Transfer. In this type of transmission, the receiver does not acknowledge receipt of a packet. This approach allows for much faster communication between devices. Connection-oriented service is more reliable than connectionless Service.

        <ins>Note</ins>:
            Data in the Transport Layer is called as Segments.

        <ins>Note</ins>:
        Transport layer is operated by the Operating System. It is a part of the OS and communicates with the Application Layer by making system calls. <ins>Transport Layer is called as Heart of OSI model</ins>.

>TCP operates in the transport layer, along with its friend UDP, the User Datagram Protocol. TCP is more complex; it performs error-checking, and it tries very hard to deliver your packets. There is a lot of back-and-forth communication with TCP as it transmits and verifies transmission, and when packets get lost it resends them. UDP is simpler and has less overhead. It sends out datagrams once, and UDP neither knows nor cares if they reach their destination.
 TCP is for ensuring that data is transferred completely and in order. If a file transfers with even one byte missing it’s no good. UDP is good for lightweight stateless transfers such NTP and DNS queries, and is efficient for streaming media. If your music or video has a blip or two it doesn’t render the whole stream unusable.

5. **Session Layer**
  * This layer is responsible for the establishment of connection, maintenance of sessions, authentication, and also ensures security.

    <ins><font size=4>**The Functions of The Session Layer**</font></ins>
      - _Session Establishment, Maintenance, and Termination_
        The layer allows the two processes to establish, use and terminate a connection.

      - _Synchronization_
        This layer allows a process to add checkpoints which are considered synchronization points into the data. These synchronization points help to identify the error so that the data is re-synchronized properly, and ends of the messages are not cut prematurely and data loss is avoided.

      - _Dialog Controller_
        The session layer allows two systems to start communication with each other in half-duplex or full-duplex.

6. **Presentation Layer**
  * The presentation layer is also called the Translation layer. The data from the application layer is extracted here and manipulated as per the required format to transmit over the network.

    <ins><font size=4>**The Functions of The Session Layer**</font></ins>
        - _Translation_
          For example, ASCII to EBCDIC.

        - _Encryption/ Decryption_
          Data encryption translates the data into another form or code. The encrypted data is known as the ciphertext and the decrypted data is known as plain text. A key value is used for encrypting as well as decrypting data.

        - _Compression_
          Reduces the number of bits that need to be transmitted on the network.
7. **Application Layer**
  * This layer also serves as a window for the application services to access the network and for displaying the received information to the user.
    - The application layer includes the network protocols you use every day: SSH, TLS/SSL, HTTP, IMAP, SMTP, DNS, DHCP, streaming media protocols, and tons more.

<font size=4>**Basic Dynamic of The Layer System**</font>
    Each layer can only use the functionality of the layer below; each layer can only export functionality to the layer above. In other words: layers communicate only with adjacent layers. Let's take the example of your E-mail message again: you enter it through the application layer. In your computer, it travels down the transport and network layer. Your computer puts it on the network through the network access layer. That is also the layer that will move the message around the world. At the destination, the receiving computer will accept the message through it's own network layer, and will display it to the recepient using the transport and application layer.

><font size=3>OSI model acts as a reference model and is not implemented on the Internet because of its late invention. The current model being used is _**the TCP/IP Model**_.</font>

><font size=3><ins>TCP/IP MODEL</ins></font>
  It was designed and developed by Department of Defense (DoD) in 1960s and is based on standard protocols. It stands for Transmission Control Protocol/Internet Protocol. _The TCP/IP model is a concise version of the OSI Model_.


### The TCP/IP MODEL'S LAYERS <font size=0.5>(on the behalf of the receiver)</font>

1. **Network Access Layer**
  * This layer corresponds to the combination of Data Link Layer and Physical Layer of the OSI model. It looks out for hardware addressing and the protocols present in this layer allows for the physical transmission of data.

2. **Internet Layer**
  * This layer parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network.

    <ins><font size=4>**The Main Protocols Residing at Internet Layer**</font></ins>
        - _IP_
          stands for Internet Protocol and it is responsible for delivering packets from the source host to the destination host by looking at the IP addresses in the packet headers.

          IP has 2 versions:
          IPv4 and IPv6. IPv4 is the one that most of the websites are using currently. But IPv6 is growing as the number of IPv4 addresses are limited in number when compared to the number of users.
          - ICMP
            stands for Internet Control Message Protocol. It is encapsulated within IP datagrams and is responsible for providing hosts with information about network problems.

          - ARP
            stands for Address Resolution Protocol. Its job is to find the hardware address of a host from a known IP address.    

              ARP has several types:
              1. Reverse ARP,
              2. Proxy ARP,
              3. Gratuitous ARP,
              4. Inverse ARP

3. **Host To Host Layer**
  * This layer is analogous to the transport layer of the OSI model. It is responsible for end-to-end communication and error-free delivery of data. It shields the upper-layer applications from the complexities of data.

    <ins><font size=4>**The Two Main Protocols Present in Host To Host Layer**</font></ins>

      - _Transmission Control Protocol (TCP)
        It is known to provide reliable and error-free communication between end systems. It performs sequencing and segmentation of data. It also has acknowledgment feature and controls the flow of the data through flow control mechanism. It is a very effective protocol but has a lot of overhead due to such features. Increased overhead leads to increased cost.

      - _User Datagram Protocol (UDP)_
        On the other hand does not provide any such features. It is the go-to protocol if your application does not require reliable transport as it is very cost-effective. Unlike TCP, which is connection-oriented protocol, UDP is connectionless.

4. **Application Layer**
  * This layer performs the functions of top three layers of the OSI model: Application, Presentation and Session Layer. It is responsible for node-to-node communication and controls user-interface specifications.  

    <ins><font size=4>**Some of The Protocols Present in Application Layer**</font></ins>
        * HTTP,
        * HTTPS,
        * FTP,
        * TFTP,
        * Telnet,
        * SSH,
        * SMTP,
        * SNMP,
        * NTP,
        * DNS,
        * DHCP,
        * NFS,
        * X Window,
        * LPD

    _HTTP and HTTPS_
      HTTP stands for Hypertext transfer protocol. It is used by the World Wide Web to manage communications between web browsers and servers. HTTPS stands for HTTP-Secure. It is a combination of HTTP with SSL(Secure Socket Layer). It is efficient in cases where the browser need to fill out forms, sign in, authenticate and carry out bank transactions.

		_SSH_
      SSH stands for Secure Shell. It is a terminal emulations software similar to Telnet. The reason SSH is more preferred is because of its ability to maintain the encrypted connection. It sets up a secure session over a TCP/IP connection.

    _NTP_
      NTP stands for Network Time Protocol. It is used to synchronize the clocks on our computer to one standard time source. It is very useful in situations like bank transactions. Assume the following situation without the presence of NTP. Suppose you carry out a transaction, where your computer reads the time at 2:30 PM while the server records it at 2:28 PM. The server can crash very badly if it’s out of sync.

</details>

<details>
  <summary><font size=4>Docker</font></summary>

<font size=4>**Useful Links for Learning Docker**</font>

* [Nana Docker Tutorials](https://youtube.com/playlist?list=PLy7NrYWoggjzfAHlUusx2wuDwfCrmJYcs)
* [thenewboston](https://youtube.com/playlist?list=PL6gx4Cwl9DGBkvpSIgwchk0glHLz7CQ-7) - <font size=0.5>**Personal Favourite**</font>

>Container is layers of linux base image, application image with configuration


**Docker Pros**
  1. A way to package applications awith all the necessary dependencies and configs
  2. Portable artifact easily shared and moved around
  3. Makes development and deployement more efficient
  4. alpnine -> Smaller Data is enough for you to take action.

**Before Containers**
  1. Each developer needs to install the application specific version
  2. Installation process different on each OS environments
  3. Many steps where something go wrong
  4. Textual guide of deployement
  5. Configuration on the server needed
  6. External dependencies on the server OS

**After Container**
 * No need to download any package. Everything contained in the container environment linux based OS

<font size=4>**Quick Docker Tutorial**</font>
<font size=0.5>* This document is just to provide a quick orientation for Docker. Please go and do a research or watch the video tutorials given above </font>
* `docker info` &rarr; Prompts system information and Server connection to Docker Hub

* `docker system prune --all` &rarr; Deletes all the containers whether it is up or down

* `docker container exec -it <CONTAINER_ID> sh or "bin/bash"` &rarr; Runs the image to create a container with interactive Bash session

* `docker container exec -it <CONTAINER_ID> sh (bin/bash)` &rarr; Run the container with a interactive Bash session

* `docker image rm $(docker images -q -f dangling=true)` &rarr; Delete unused and untagged containers

* `docker container run -it --name <CONTAINER_NAME> <IMAGE_NAME>` &rarr; Run `<CONTAINER_NAME>` with interactive Bash session using `<IMAGE_NAME>`

* `docker container ls -a` &rarr; Lists all containers

* `docker container inspect <CONTAINER_ID>` &rarr; Displays detailed information on one or more containers

* `docker container pause <CONTAINER_ID>` &rarr; Pause a running container

* `docker container unpause <CONTAINER_ID>` &rarr; Unpause a running container

* `docker container stop <CONTAINER_NAME>/<CONTAINER_ID>` &rarr; Stops a running container. Can be started again with
  - `docker start <CONTAINER_NAME>`

* `docker pull <REPOSITORY_NAME>/<IMAGE_NAME>:<IMAGE_TAG>` &rarr; Pull your image to your local

* `docker start <IMAGE_NAME>` &rarr; Start your image as a container

* ``docker run -d -p <YOUR_DEVICE_PORT>:<CONTAINER_PORT> --name <CONTAINER_NAME> <IAMGE_NAME>
`` &rarr; Start your container in deteached mode with `-d`  and give custom ports with `-p`

* `docker ps` &rarr; Lists running containers

* `docker ps -aq` &rarr; Lists all container Id's

* `docker images` &rarr; Lists images

* `docker image inspect <IMAGE_ID>` &rarr; Display detailed information on images

* `docker network ls` &rarr; Lists networks

* `docker logs <CONTAINER_ID> | tail` &rarr; Displays logs from the last entry
  - `docker logs <CONTAINER_ID> -f` &rarr; You can add dashes to see streaming logs

* `docker rm <CONTAINER_NAME>` &rarr; Remove specified container

* `docker rmi <IMAGE_NAME>` &rarr; Remove specified image

<font size=3>**Docker Compose**</font>
<font size=1>You can use compose to build and manage multiple services in Docker containers. </font>

* `docker compose -d -f <FILE_NAME>.yaml up` &rarr; Get the multiple services up with `docker compose`
  - `docker compose -d -f <FILE_NAME>.yaml down` &rarr; Stops the containers included inside the .yaml file.     

  <ins>NOTE</ins>: When `docker compose` command runs, it creates a docker network and all the included services runs inside this network. After running `docker compose ... down` the network is deleted automatically.

> Here is a [example](https://github.com/kasimerbay/Innovance-Internship/blob/master/default.yaml) docker compose file (.yaml). Using this file makes managing and configuring containers easier.

* `docker network create <NETWORK_NAME>` &rarr; Create a network called `<NETWORK_NAME>`

* ` docker run -d -p <YOUR_DEVICE_PORT>:<CONTAINER_PORT> -e environmental_settings -net <NETWORK_NAME> -name <CONTAINER_NAME> <IMAGE_NAME>` &rarr;

* `docker build -t <IMAGE_NAME>:<VERSION_STATUS>` &rarr; Create an image file from a Dockerfile

>Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. Using docker build users can create an automated build that executes several command-line instructions in succession. This page describes the commands you can use in a Dockerfile. When you are done reading this page, refer to the Dockerfile [Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) for a tip-oriented guide.

<font size=2.5>**Docker Volume Types**</font> - Given to the `docker run` with `-v` tag
1. Host Volume
2. Anonymous Volume
3. Named Volume &rarr; Let the docker manage files we provide

</details>

<details>
  <summary><font size=4>Jenkins</font></summary>

<font size=4>**Useful Links for Learning Jenkins**</font>
  - <https://www.jenkins.io/doc/book/>
  |  <font size=0.5>This link includes all the necessary processes to use Jenkins</font>
  - <https://www.youtube.com/watch?v=pMO26j2OUME&list=PLy7NrYWoggjw_LIiDK1LXdNN82uYuuuiC>

### Frequently Used Terms

* [What is Java Servlet?](https://stackoverflow.com/questions/7213541/what-is-java-servlet)
  A servlet at its very core is a java class; which can handle HTTP requests. Typically the internal nitty-gritty of reading a HTTP request and response over the wire is taken care of by the containers like Tomcat. This is done so that as a server side developer you can focus on what to do with the HTTP request and responses and not bother about dealing with code that deals with networking etc. The container will take care of things like wrapping the whole thing in a HTTP response object and send it over to the client (say a browser).

  Now the next logical question to ask is who decides what is a container supposed to do? And the answer is; In Java world at least It is guided (note I did not use the word controlled) by specifications. For example Servlet specifications (See resource 2) dictates what a servlet must be able to do. So if you can write an implementation for the specification, congratulations you just created a container (Technically containers like Tomcat also implement other specifications and do tricky stuff like custom class loaders etc but you get the idea).

  Assuming you have a container, your servlets are now java classes whose lifecycle will be maintained by the container but their reaction to incoming HTTP requests will be decided by you. You do that by writing what-you-want-to-do in the pre-defined methods like init(), doGet(), doPost() etc. Look at Resource 3.

  Here is a fun exercise for you. Create a simple servlet like in Resource 3 and write a few System.out.println() statements in it's constructor method (Yes you can have a constructor of a servlet), init(), doGet(), doPost() methods and run the servlet in tomcat. See the console logs and tomcat logs.

<ins><font size=4>Important Notes</font></ins>
* Be Careful with Command Line Parameters. Jenkins ignores command line parameters it doesn’t understand instead of producing an error. Be careful when using command line parameters and make sure you have the correct spelling. For example, the parameter needed for defining the Jenkins administrative user is --argumentsRealm and not --argumentRealm.

</details>

[//]: # (the Last Code I Run -- docker run -p8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts)

---

### My QA Session and Usefull Project Ideas

  1. Can I create my own Version Control System?
    - [Answer](https://ericsink.com/entries/time_space_tradeoffs.html)
  2. Chat Application Using Raspberry Pi
    - To understand the network layers
  3. Can I create a crypto currency network with Docker?
    - ?????
