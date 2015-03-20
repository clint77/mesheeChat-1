### Introduction

All around the world internet freedoms are being eroded by governments, restricting communications. For example, [in Venezuala in 2014 the internet was turned off and modes of communcation were blocked](http://www.huffingtonpost.com/2014/02/21/venezuela-internet-_n_4832505.html). We wanted to create a secure, decentralised communications network that would enable secure conversations to take place without the internet. 

mesheeChat is a 2 week project which uses the mesh networking tool CJDNS in combination with Node.js to provide secure chat over a mesh network. We prototyped the network using Raspberry Pis and tested using Mocha and Webdriver.io.

### Process

Firstly, since we only had two weeks to build the project, we had to narrow down how we were going to provide communications without the internet. We settled on mesh networking to provide this functionaltiy. Mesh networking enables data trasfer throughout a network whereby each device in the network is connected to all others. We decided to use CJDNS to provide this functionality becaise a) it is decentralised, b) it provides secure data transfer and c) it is the most widely adopted secure mesh tool. 

Secondly, we wanted to be able to prototype how the network would work and we wanted a network which we could control in a test environment. We used Raspberry Pis to emulate the network. Each Pi was running CJDNS which enabled each Pi to connect to the other via WIFI.

Then we wanted users on the network to communicate. We selected Node.js as its async nature means that a lot of requests are able to be handled by a single node in the mesh network. We then used websockets to push the messages to devices connected to the network. 

We tested using Mocha, Chai, Webdriver.io and Should using TDD and BDD throughout the process.

### What We Learnt

- 2 weeks is a tough challenge to make a polished application
- Networking is HARD and working with all new technologies has its pitfalls documentation wise. But also there are parts of the tools we were using where the documentation is incorrect or certain things don't work. For example, with CJDNS there were multiple errors in the setup process that we came across that required clarification. We spoke to the developers over IRC to work this out. 
- Unit testing Socket.io also has its difficulties. In hindsight, feature tests provided the coverage that we needed. 
- Working with hardware provides difficulties with new software and it is problematic when it comes to debugging 
- Teamwork is necessary! We had a software team and hardware team in the first week. SCRUMs were necessary to keep on us on track. We also organised the project using Trello. 
- BE AGILE! We had repeated brickwalls that couldn't be knocked down in 2 weeks. We wanted to get mesheeChat working on mobile but CJDNS is not yet ready for mobile and the alternative options such as the OpenGarden sdk aren't yet available. We would have had to build our own mesh tool to use mobile which wasn't feasible in 2 weeks.

### TODO 

- Setup guide for CJDNS with mesheeChat
- We have started work on a rooms feature to provide rooms for people to have conversations. 
- AutoConnect - find when users are running the app and decide who hosts
- P2P would be fantastic 

### TO RUN THE APP

```sh 
git clone https://github.com/jacobmitchinson/mesheeChat
npm install 
nodemon
```
