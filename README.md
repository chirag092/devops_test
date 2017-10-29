# devops_test

This automatation is used to setup follwoing architacture on a remote machine :

user --> apache httpd --> tomcat1 --> mysql
                          tomcat2 --> mysql
                          
    apache is loadbanlacing two tomcat petstore instances                           

-- Two instances of tomcat running on 8081 and 8082 ports
    -- We can update these ports in group_vars/all/config.yml file
    
-- To run the whole automation to setup a remote machine use below command :
 
    ansible-playbook --user ubuntu -i hosts --ask-pass site.yml -vvvv --ask-become-pass 
         
         
-- If you just want to restart apache and tomcat use follwoing command :

    ansible-playbook --user ubuntu -i hosts --ask-pass site.yml -vvvv --ask-become-pass --tags start
     
-- To Test the above setup use below url 
 
       http://{{ hostname  }}/petstore
       
       Example: 
              http://54.221.82.8/petstore
            