# docker-machine-demo
Simple demo for Docker-Machine

Under MacOS

## how to use

### local demo 

Running in local machine . 

* run :

        docker-machine create --driver virtualbox  --engine-registry-mirror https://registry.docker-cn.com default
                
    * if you see the error info below :
    
           Error creating machine: Error in driver during machine creation: Error setting up host only network on machine start: The host-only adapter we just created is not visible. This is a well known VirtualBox bug. You might want to uninstall it and reinstall at least version 5.0.12 that is is supposed to fix this issue
           
        you need install the latest VirtualBox on your system           
        
        Here is the Download page : https://www.virtualbox.org/wiki/Downloads
        
    * you can also add config below : 
    
        default DNS for docker
        
            --engine-opt dns=114.114.114.114  
        
        conf the docker hub url
         
            --engine-registry-mirror https://registry.docker-cn.com 
        
        memory
        
            --virtualbox-memory 2048 
        
        cpu number
        
            --virtualbox-cpu-count 2     
            
* run :

         eval "$(docker-machine env default)"
         
    to connect default machine
    
    after the demo is done , you can run 
    
         eval $(docker-machine env -u)
         
    to disconnect default.          
    
* run : 

        ./build-image.sh
        
    to install image
    
* run :
        
        docker-compose up -d 
        
    to run project in docker(in your docker-machine).
    
* check the default ip : 

        docker-machine ip default
        
    let's assume the value is 192.168.99.100
    
* open your browser , and visit : 192.168.99.100:8080, if there is a page return with "welcome Disguess guest, are you a Girl?" , we are success .

* now , we can stop default , and ready to begine a new demo.

    docker-machine stop default

### remote demo 

Let's suppose that there is a host with a IP address of 192.168.10.10 in the LAN now .

My next demo will introduce how to deploy Docker in 192.168.10.10 through docker-machine .

 

         
                
                                             