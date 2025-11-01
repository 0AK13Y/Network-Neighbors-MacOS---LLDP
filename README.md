# Network-Neighbors-MacOS---LLDP
This will help with the install and setup of the lldpd 


Install 
## First we'll install brew
	brew install https://raw.github.com/lldpd/lldpd/master/osx/lldpd.rb
## Second we are setting brew to be a enviroment so you're not dependent on the directory to run brew 
	echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile 
	eval "$(/opt/homebrew/bin/brew shellenv)"
## Third: If you just installed brew, you won't need to run the update command but it doesn't hurt to run it just in case
	brew update
## Forth: We'll install the lldpd package and start the process
	brew install lldpd
	sudo brew services start lldpd

## How to validate the service is running 
	brew services list

##		aomit@OakleysMBPro ~ % lldpcli show neighbors
##		-------------------------------------------------------------------------------
##		LLDP neighbors:
##		-------------------------------------------------------------------------------
##		Interface:    en7, via: LLDP, RID: 2, Time: 0 day, 01:51:31
##		Chassis:     
##			ChassisID:    mac f4:e2:c6:da:8b:21
##			SysName:      oakley-sw01
##			SysDescr:     UBNT-USL8L
##			Capability:   Bridge, on
##		Port:        
##			PortID:       local Port 7
##			PortDescr:    Port 7
##			TTL:          120
##		-------------------------------------------------------------------------------


## Example response from the terminal when lldpd is running successfully 
		# aomit@OakleysMBPro ~ % brew services list
		# Name  Status User File
		# lldpd none   root 

## How to check
	 lldpcli show neighbors
	
## How to Update
	sudo port selfupdate && sudo port upgrade lldpd

	
## How to Stop the service 
	sudo brew services stop lldpd
	
