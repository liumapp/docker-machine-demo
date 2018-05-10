# docker-machine-demo
Simple demo for Docker-Machine

Under MacOS

## how to use

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
    
* run : 

        ./build-image.sh
        
    to install image
    
    or you can run : 
    
         docker run busybox echo hello world
         
    for a test .          
    
* run :
        
        docker-compose up -d 
        
    to run project in docker.                                         