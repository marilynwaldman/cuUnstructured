# VirtualBox - Vagrant Setup
> Start vagrant and install guest additions

  - There are issues with Virtual Box especially with copy/paste
  - We will start our virtual machine then install guest additions so you can
    copy and paste.
    
 
###  NOTICE 
#### COPY will be (SHIFT CONTROL C)
#### PASTE will be (SHIFT CONTROL VZ)

## VAGRANT

  - Open a terminal 
  
      ![Screenshot](images/openaterminal.png) 
      
  - Make sure you are in your $HOME directory and clone vagrant
  
```bash
    cd
    git clone https://github.com/marilynwaldman/vagrant.git
```  
   
   ![Screenshot](images/cdtovagrant.png)      
  
  - Change directory to vagrant
  ```bash
    cd vagrant
    pwd
  ```
  
  - run vagrant up - this will run for a long time.  Wait until you get a 
  command line
  ```bash
    vagrant up
  ```
  
   ![Screenshot](images/vagrantup.png) 
  
  - You will see a terminal like this
    
   ![Screenshot](images/seeterminal.png) 
    
  - Go to APPS and double click on VirtualBox
        
   ![Screenshot](images/gotoapps.png) 
       
  - Shut the VM down
          
   ![Screenshot](images/close.png) 
   
   ![Screenshot](images/poweroff.png) 
   
            
  
### Install Guest Additions

  - Add an optical drive
  
  ![Screenshot](images/gotosettings.png) 
  
  - Add an optical drive
    
  ![Screenshot](images/gotosettings.png) 
  
  - Go to Settings
      
  ![Screenshot](images/selectAdvanced.png) 
      
  - Add the optical drive
        
  ![Screenshot](images/addanopticldrive.png) 
  
  - Select "Empty"
          
  ![Screenshot](images/selectempty.png) 
  
  - Restart VM
           
  ![Screenshot](images/restartvm.png) 
   
  - Go to Devices and Add Guest Additions
              
  ![Screenshot](images/devicesaddguest.png)  
  
  - Shut the vm down
                
  ![Screenshot](images/close.png) 
     
  ![Screenshot](images/poweroff.png) 
  
### Recycle vagrant  
  
  - go to your terminal and stop vagrant
  
```bash
    vagrant halt
```  
  - vagrant up
  
 ```bash
   vagrant up
 ```    
 
### Your vm will be restarted

   ![Screenshot](images/screenwithcarrot.png) 
   
   - Password is 'vagrant'
   
   ![Screenshot](images/uservagrant.png)
   
   
   - Remove message at top my clicking on the little 'x' on the top right hand side
      
   ![Screenshot](images/littlexrightside.png)   
   
   - This is your user interface
   
   ![Screenshot](images/userinterface.png)   
   
   - Click the little fish on the upper left hand side
      
   ![Screenshot](images/littlebluefishe.png)  
   
   - Click the little fish on the upper left hand side
         
   ![Screenshot](images/littlebluefish.png) 
   
   - This is your terminal
            
   ![Screenshot](images/yourterminal.png) 
   
   - Click the red button on the upper left hand side to shut your VM off
   
   ![Screenshot](images/powervmoff.png)  
   
   - Shut Vagrant down
```bash
   vagrant halt
```   

````aidl
Marilyns-MacBook-Pro:vagrant marilynwaldman$ vagrant halt
==> default: Attempting graceful shutdown of VM...
Marilyns-MacBook-Pro:vagrant marilynwaldman$ 

````
   
      
     
   
   


              
    
     