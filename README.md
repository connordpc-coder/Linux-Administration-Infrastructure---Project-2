# Linux-Administration-Infrastructure-Project-2
Building a Linux administration workstation with Bash automation, SSH, networking and infrastructure management across multiple virtual machines.
VM1= last projects VM - client 
VM2= this projects VM - admin

---

## Project Planning

The initial roadmap document created shortly after my first project:

![Project Planning](Planning/Project2map.md)


Although this will be my main structure for this project, i have made some reflections and alterations that i believe will ultimately benefit the projects consistency. The main change is starting my second vm right away as appose to using my one from my other project i originally planned for that first one to be the host in the peer to peer network and my new scripts that will automate task too, leaving little for that second vm to do so Ive changed the plans for the second vm to be the more advanced machine making it more coherent and will help build good structural habits for the future.

---

## Building a Workstation &  Admin Toolkit 
The first stage of the project building the foundation of vm2's environment as well as an almost a reflection on the start of my first project and how i can make the early stages into the machine flow much quicker through writing scripts that can automate tasks like making a directory and giving it permissions or creating easy access shortcuts that make work flow feel less binary and more intuitive.

![Building a Workstation &  Admin Toolkit](Workstation/P2-start.png)
![Building a Workstation &  Admin Toolkit](Workstation/p2-setup.png)
![Building a Workstation &  Admin Toolkit](Workstation/p2-system-script.png)
![Building a Workstation &  Admin Toolkit](Workstation/p2-output-mistake.png)
![Building a Workstation &  Admin Toolkit](Workstation/p2-scorrection.png)

Started setting up the new system, before even adding directories i wanted to immediately start making a script that would get the vm up and running covering updates and upgrades needed. i applied the chmod permission to the script and installed tree not to long after as i prefer it to ls. After running the script i realized i made an error in my script typing with my autoclean command went back to correct it and reran the script to a cleaner output.



![Building a Workstation &  Admin Toolkit](Workstation/p2-script2.png)
![Building a Workstation &  Admin Toolkit](Workstation/testp2.png)
![Building a Workstation &  Admin Toolkit](Workstation/testp2.1.png)
![Building a Workstation &  Admin Toolkit](Workstation/testp2problem.png)
![Building a Workstation &  Admin Toolkit](Workstation/testp2.outcome2.png)

Second script built, felt this one answered a lot of questions id previously been looking for in terms of the extents of script writing. learning "$xxxx" as this output place holder has been most valuable because as i said it helps me gauge the extent of where you can go with automation and will make me think during some other tasks if the steps can be cut in half through a script.
Again it was encouraging to learn but when running the script the first time it didn't work when reading why, i could immediately tell it was due to how i spaced the script. I then went back in corrected it, ran it and checked if the permissions and files applied correctly which it was. Going forward this script alone will now cut a good few hours dedicated to organization down to maybe 1 hour like after this ill move the two scripts into my new toolkit directory then i can make another four or five in the space of a few minutes like infrastructure logging, admin automation, troubleshooting scenarios... with their bases covered just in need of fleshing out.



![Building a Workstation &  Admin Toolkit](Workstation/script3.png)

![Building a Workstation &  Admin Toolkit](Workstation/script3.1.png)

![Building a Workstation &  Admin Toolkit](Workstation/script3.2.png)

Used the same methodology for the directories automation and made a script that can create another script make it runnable and nanos me straight into the new file to start script writing.


![Building a Workstation &  Admin Toolkit](Toolkit/NET1.png)
![Building a Workstation &  Admin Toolkit](Toolkit/NET2.png)

Built two network based scripts one for info,ip adress, ports etc. Might go back and add the hostname but for now its okay and along with the testing script which like the other scripts ive been making provide the utility of being able to be used repeatedly. in the next part these two scripts will be instrumental with establishing the peer to peer connection and making sure its configured correctly.

![Building a Workstation &  Admin Toolkit](Toolkit/wrkstatuni.png)
![Building a Workstation &  Admin Toolkit](Toolkit/tkmove.png)

Last stage of making the this toolkit i feel is to make the directory understandable on a universal basis like a command, which meant i had to go into ~/.bashrc and add the path/line into there which now makes there scripts ive made easier to type out not having to use "./" to get it to work which is just nice to be able to do more than anything.



## Building Infrastructure
this stage was the initial premise of this project of building a peer to peer network connection. The main goal is to secure the SSH connection so i can then learn and navigate between the two machines.

![Building Infrastructure](Infrastructure/infa1.png)
![Building Infrastructure](Infrastructure/infa2.png)
![Building Infrastructure](Infrastructure/infa3.png)

Started getting the part Im most excited for going, originally i got the two VM's up and running used ip addr and my network script expected to be able to pull each ip from each other's but i was quite wrong. Because i was on oracles private network i had to make an adaption in each of the VM's network settings to make a host only connection between the pair, then i went back into the vm found the new line in ip addr and pinged each ip's on the others which worked great. Think this was a great first start, having to go outside of the vms to impact something in my machines felt odd as always feel like if you want something to work in Linux you have to do it yourself from the ground up but its good to know for the future.


![Building Infrastructure](Infrastructure/key2.png)
![Building Infrastructure](Infrastructure/key3.png)
![Building Infrastructure](Infrastructure/key4.png)
![Building Infrastructure](Infrastructure/key5.png)

After establishing that the VMs were connected, Ive now moved onto some admin basics of generating keys make that host and client connection with my vm from my last project and being able to log in to my first projects vm through this projects vm which is going to mainly the be the administrator of the two. From there i was able to get the SSH going being able to access vm1 being the @linuxpro user learned how come in and out of the sessions and then i wanted to do a light exercise of securely copying my toolkit Ive made this project into vm1 which worked great, Ive not done the same as i did in my other vm like creating a path and editing bashrc to make it work better, it was just a proof of concept.Overall  really enjoyed doing this its circling back to the theory ideas i learned very early on before project building and using them in a real and constructive way.

![Building Infrastructure](Infrastructure/EA.png)
![Building Infrastructure](Infrastructure/EA2.png)
![Building Infrastructure](Infrastructure/EA3.png)
![Building Infrastructure](Infrastructure/EA4.png)
![Building Infrastructure](Infrastructure/EA5.png)

Did more information relaying from each machine and found and error when i transferred my toolkit over to VM1 and it duplicated the whole directory with the name of VM1's user. No harm came of it though i just removed it and also made a basic easy access to save me from retyping the ssh command which ill now be doing quite regularly gas an okay purpose for now but I'll probably repurpose it later when it comes to fully automating peer to peer tasks. As for relaying i used the ssh command to relay some commands and then scripts from my toolkit that i just moved over and they both worked great and then i went into VM1 and used ssh to my current project VM be reassure the connect works both ways.


tried to make a script wrapper to be able to easily access any script i wanted in my toolkit directory in VM1, wasn't as easy as i thought it would be as the ssh and the path i created in VM1 interact weirdly do im pushing it back to the automation stage or troubleshooting.



![Building Infrastructure](Infrastructure/FW1.png)
![Building Infrastructure](Infrastructure/FW2.png)
![Building Infrastructure](Infrastructure/FW3.png)

Started making firewall rules while making sure the admins (current VM) channel remained available. Got a basic understanding of it how to add and remove rules and read it in general 

![Building Infrastructure](Infrastructure/H1.png)
![Building Infrastructure](Infrastructure/H2.png)
![Building Infrastructure](Infrastructure/H3.png)
![Building Infrastructure](Infrastructure/H4.png)

Getting comfortable with SSH and being able to investigate user privileges. With the user privileges it was just a quick test to get a general understanding before moving into the next stage of administration and automation were it will be much more prevalent when configuring what and what not a user can't do. As for the SSH configuration ive made it simple to access VM1 by making a small script that allows the machine to understand what i mean when i write vm1 than the user and ip when connecting to SSH and building wrapper scripts like what id been struggling with recently.

![Building Infrastructure](Infrastructure/L1.png)
![Building Infrastructure](Infrastructure/L2.png)

just a basic demonstration of what logging in my ssh now looks like, i recall in my first project understanding the logs function because it was similar to investigative work i do at work anyway but when id actually see activity that id really be able to understand it a bit better which i can say i do now being able to pull login failure and filter then to understand and be able to investigate in Linux. 


##  Automation & Administration
this stage focuses on using that toolkit to manage the completed environment through automation. reducing that manual admin work while maintaining a consistent workflow.

![Automation & Administration](Automation/scroutput.png)
![Automation & Administration](Automation/scroutput3.png.jpeg)
![Automation & Administration](Automation/scroutput2.png)

building a new administrative script, starting to use things like pipes to filter and control what i want outputted. the process was trail and error using ideas i may have used before but not used together, so i took a good few times correcting each line the script couldn't understand until i got updating status to give that one line direct answer and it felt rewarding to finally get exact output i wanted and its definitely something to learn from going forward with my script outputs. Going forward a majority of this stages work is going to be and expansion on ideas from my toolkit introduction but again working on honing ideas down to make them easily readable and manageable in a problem solving situation 

## Troubleshooting 
creating real world scenarios that reflect common infrastructure and Linux administration problems.

## Project Reflection
