1.INTRODUCTION
	
A package is known for installing & maintaining softwares for the Linux-based computers.It include a manifest of dependencies, or lists of programs and versions that must be satisfied for the packaged software to run correctly on a given computer.

2.TYPES OF PACKAGE MANAGEMENT SYSTEMS -
	
There are diffrent package management systems for the diffrent distribution of the Linux.Some of these package management system are listed as following:
		
1.DPKG: The base package manager for Debian-based distributions.
		
2.Apt: A front-end for the DPKG system, found in Debian-based distributions, such as Ubuntu, Linux Mint, and Elementary OS.
		
3.Apt-get: A more feature-rich front-end for the DPKG system, found in Debian-based distributions.
		
4.RPM: The base package manager found in Red Hat-based distributions, such as Red Hat Enterprise Linux, CentOS, and Fedora.
		
5.Yum: A front-end for the RPM system, found in Red Hat-based distributions.
		
6.Dnf: A more feature-rich front-end for the RPM system.
		
7.ZYpp: Found in SUSE and OpenSUSE.
		
8.Pacman: The package manager for Arch Linux-based distributions.

3.COMMANDS FOR PACKAGE MANAGEMENT -
	
Instead of concentrating on all of the linux distributions we will focus on the package management for the Red Hat Linux based distribution.In Red Hat-based distribution,the ``YUM`` is package management system for nstalling, updating, removing, and managing software packages.
	
The general syntax for the package management commands is ``yum -option command package_name``.
	
Following are the commands listed for the Package Management :
		
1. `yum install package_name` => Using this command we can install that particular package on our system.
			Example, if we entered the command ``yum install httpd``,then the package `httpd` will be installed and it will ask us for the installation of dependency for the particular package,if we click `y` then all its dependency will be installed.
		
2. `yum info package_name` => This command will give information related to that particular package i.e it basically show the description.
			
	Example, if we entered the command ``yum info httpd``,then following information will be displayed .
				
				Installed Packages
				Name        : httpd
				Arch        : x86_64
				Version     : 2.4.6
				Release     : 97.el7.centos
				Size        : 9.4 M
				Repo        : installed
				From repo   : updates
				Summary     : Apache HTTP Server
				URL         : http://httpd.apache.org/
				License     : ASL 2.0
				Description : The Apache HTTP Server is a powerful, efficient, and extensible web server.
		
3. `yum remove package_name` => This will remove the given package along with its dependency.

4. `yum history` => Command to display what has happened in past transactions with the index.
		
5. `yum history undo <id>`=> To undo specific action with entered id.

6. `yum provides  /var/www/html` => it provides from where the package maybe installed.
		
7. `yum search keyword` => it searches package metadata for given keyword.
		
8. `yum repolists` => it lists down the repositories.
	
The main configuration file for YUM is at ``/etc/yum.conf,`` and all the repos are at ``/etc/yum.repos.d.``

4.ABOUT RPM -
	
RPM is also known as package management tool for Red Hat-based distribution.It can also perform package management operations like install,verify,earase,uninstall but it cannot resolve dependency like the package management tool `YUM`. 	

5.YUM REPOSITORY -
	
It is used for  for getting, installing, deleting, querying, and managing Red Hat Enterprise Linux RPM software packages from official Red Hat software repositories, as well as other third-party repositories.
	
