# Write-up Template

The reasons why I chose the web app over the virtual machine are due to the accessibility, maintenance, scalibility, cost, security and user experience. 

For accessibility, I preferred the web app because it could easily be accessed from any device with an internet connetion and a web browser. For this specific project, it seemed like the objective was to be able to make posts quickly and easily. In order to do so, the end user needs to be able to access the application with ease. 
When debugging the code for this project, the Azure web app was easier to debug because the updates and bug fixes can be deployed centrally on the server without requiring users to download and install updates as needed. Also, when updating the code for the security errors, it was much quicker for me to be able to update invalid logins with error messages allowing the programmer and the end user to easily see any issues. 

For a cost analysis, the web app is much more cost effective with the cost cut in almost half. As you can see in my screenshots folder, neither the VM or the web app had upfront costs, but the web app was much cheaper with its monthly costs at $54.75 a month, whereas the VM costs were $134.75 monthly. Even if you were to pay costs upfront for the VM, it was still more cost effective to use the web app. I also liked that you pay only for what you use, which is more cost-effective for this application that may have differing or fluctuating workloads. Also, with a VM, if you are trying to use multiple VM's and configurations, your cost only increases. 

For scalability, the Azure Virtual Machine can automatically scale by using virtual machine scale sets. While VMs can scale, it requires more manual setup and management through VM scale sets. This gives you more control over how and when to scale; however, with the Azure web app, it manages the infrastructure, scaling, and maintenance; therefore allowing me to focus more on my application code rather than server management. 

For availability, the VM has high avaialability, but that comes with confiuguration, whereas a web app has the availability built in. With the web app, there was less manual configuration. 

Since I am not a full time developer, the web app was a likely choice for me. The management and seamlessness of the web app was much easier for me to manage. Also, with this being a straightforward configuration, it did not make sense to me to deploy a virtual machine.
If I were a full time developer, and working on a larger project, I could see the need to spin up a VM, but for this project in particular, the web app seemed more cost effective and more efficient. 
