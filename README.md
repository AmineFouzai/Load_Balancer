# Load_Balancer
Load Balancing Tornado Servers With Nginx

 ----------------------
# #setup
<table>
  <tr>
    <td>
    1) git clone https://github.com/MedAmineFouzai/Load_Balancer/ 
    </td>
    <tr>
    <td>
    2) cd Load_Balancer                                           
    </td>
  </tr>
  <tr>
    <td>
    3) Python server1.py                                      
    </td>
    </tr>
  <tr>
    <td>
    3) Python server2.py                                       
    </td>
    </tr>
  <tr>
    <td>
    3) Python server3.py                                       
    </td>
    </tr>
</table>

----------------------------------------


In computing, load balancing refers to the process of distributing a set of tasks over a set of resources, with the aim of making their overall processing more efficien
## #Nginx:
![Nginx](https://guides.wp-bullet.com/wp-content/uploads/2017/03/nginx-wordpress-404-redirect-homepage.png)
[Nginx](https://www.nginx.com/) acts as a single entry point which calld a reverse proxy to a distributed web application working on multiple separate servers. ... As a prerequisite, you'll need to have at least two hosts with a web server software installed and configured to see the benefit of the load balancer which is in this case our tornado servers.  

# Usage:
### on windows:
before runing any server  you have to download [Nginx](https://www.nginx.com/)  then  execute the nginx server ,configure the [nginx.conf](https://github.com/MedAmineFouzai/Load_Balancer/blob/master/nginx.conf) file or replace it with the one from the repo that contain  " include python.conf; " in the conf folder.

inside [Python.conf](https://github.com/MedAmineFouzai/Load_Balancer/blob/master/python.conf) your find somthing like this :
       
       upstream domainname {
           server localhost:1111;
           server localhost:2222;
           server localhost:3333;
        }
       server{
           listen 8000;
    
       location /give {
        proxy_pass "http://domainname/served";
      }
      }
you cane change the " domainname " to the one that your DNS is running on for serving the clients

you can add more servers listening on other Ports.
# Result:
Requesting the endpoint [http://localhost:8000/served](http://localhost:8000/served) will return the same content but served from a different process.
load balncing is very important for optimizing the use of resources available, maximize throughput, minimize response time, and avoid overload of any single resource.
 
