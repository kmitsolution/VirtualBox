
### Prerequisite
<ul>
  <li> Virtualization should be enabled on your machine</li>
  <li> <a href="https://www.virtualbox.org/wiki/Downloads" >Download </a> and Install Virutal Box </li>
  </ul>
  
### Install Vagrant Software  
<ul>
  <li> Goto https://www.vagrantup.com/ </li>
  <li> Click on Download button </li>
  <li> After Download, Install Vagrant and it needs a restart of computer . </li>
</ul>

### Find the vagrant image
<ul>
  <li> Goto https://www.vagrantup.com/ </li>
  <li> Click on FindBoxes </li>
  <li> Search any vagrant image ( for example ubuntu/trusty64) </li>
  <li> Create a directory where you want to create the vagrantfile (C:\test) </li>
  <li> Run following commands on C:\test dir <br />
        vagrant init ubuntu/trusty64 <br/>
        vagrant up
  </li>
  <li>  Virtual machine should be created and in Running state in Virutal box </li>
  <li> To access Virtual machine run <br />    vagrant ssh </li>
  </ul>
  
### Vagrant file configuration
In vagrantfile we can change the configuration of virtual machine

  #### to set the VM OS
  config.vm.box= <<OS>>
  
  #### To set provider
  config.vm.provider- "virtualbox"
  
  ####  how host see your network
  config.vm.network
  
  how you access files from your computer
  config.vm.synced_folder 
  
  #### Setup start up script

  config.vm.provision

#### Vagrant Commands
 <ul> 
   <li> <b> To initialize the vagrant image </b> vagrant init <<box>> </li>
   <li><b> Start VM </b> vagrant up </li>
   <li> <b> Delete a Virtual Machine </b> vagrant destory </li>
   <li> <b> Suspend Virtual Machine </b> vagrant suspend </li>
   <li> <b> Resume VM </b> vagrant resume </li>
   <li> <b> Reload vm after configuration change </b> vagrant reload</li>
   <li> <b> Switch to VM </b> vagrant ssh</li>

  </ul>   

 ### Change the memory in vagrantfile from 1024 to 2048

    Vagrant.configure("2") do |config|
      config.vm.box = "centos/7"

       config.vm.provider "virtualbox" do |vb|
         # display the virtualbox gui when booting the machine
         vb.gui = true

         # customize the amount of memory on the vm:
         vb.memory = "2048"
       end

  <b>Save the file and run vagrant reload and you will see the memory of vm is changed </b>

### Setup the network forward port
  <b> install nginx </b>
  
      sudo yum install epel-release
      sudo yum install nginx
      sudo systemctl start nginx
      sudo systemctl enable nginx
      config.vm.network "forwarded_port", guest: 80, host:84
  
    
