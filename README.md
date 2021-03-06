# Docker, Node, MongoDB, Opentracing with jaeger 

### Standalone  
* How to build (run from standalone folder)  
`docker build -t zhenik/hello-node .` 
 
* How to run    
`docker run -d -p1234:1234 zhenik/hello-node`

### Compose-with-mongo  
*Notice: mongo port 27017 is not exposed. Mongodb accessible only inside docker container.  
* How to run(run from standalone folder. detached mode)  
`docker-compose up -d`   


### Compose-with-tracing  

API  
[Opentracing](https://github.com/opentracing/opentracing-javascript/)  
Impl  
[Jaeger](https://github.com/jaegertracing/jaeger-client-node)  

Hot to run  
- run jaeger + ui img   
`docker run -d -p5775:5775/udp -p6831:6831/udp -p6832:6832/udp   -p5778:5778 -p16686:16686 -p14268:14268 jaegertracing/all-in-one:latest`
- with http run node (run from compose-with-tracing)  
`node server3.js`  
 
- with express refTo [RisingStack](https://github.com/RisingStack/jaeger-node) 
`node server4.js`

- Go to [jaeger](http://localhost:16686/search) on host:16686


### Compose-NODE-REACT  
check [https://github.com/NikitaZhevnitskiy/web-assignment1](https://github.com/NikitaZhevnitskiy/web-assignment1) 