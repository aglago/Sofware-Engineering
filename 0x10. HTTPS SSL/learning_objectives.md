# Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

## General
- What is HTTPS SSL 2 main roles
- What is the purpose encrypting traffic
- What SSL termination means

## Answers

- What is HTTPS SSL 2 main roles

The two main roles of HTTPS/SSL (Secure Sockets Layer) are authentication and encryption. Authentication verifies that the website you're connecting to is the legitimate site, and not a fake or imposter site. Encryption ensures that any data you send to the website is scrambled so that it can't be read by anyone else. This is important for things like online banking and shopping, where you need to be sure that your personal information is safe.

- What is the purpose encrypting traffic

The purpose of encrypting traffic is to protect the privacy and security of the information being transmitted. Without encryption, anyone who has access to the network can potentially intercept and read the traffic. This could allow them to steal sensitive information, like passwords or credit card numbers. With encryption, only the intended recipient can read the information. So, if you're using a website that requires you to log in, for example, encryption helps to keep your username and password safe from hackers. 

- What SSL termination means

"SSL termination" refers to the process of ending an SSL (Secure Sockets Layer) connection. This is usually done at the web server, where the data is decrypted and made available to the website. The purpose of SSL termination is to offload the work of encryption and decryption from the web server, which can improve performance and scalability. It also helps to prevent man-in-the-middle attacks, where a malicious actor intercepts and alters the traffic between the client and the server.