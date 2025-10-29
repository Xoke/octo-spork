# notes

I like to do an updateme.sh file in a bin folder in your home folder.  Because I'm lazy

* sudo -i
* mkdir bin
* cd bin
* touch updateme.sh
* nano updateme.sh
* sudo apt update && sudo apt upgrade -y && sudo apt dist-upgrade -y && sudo apt autoremove -y
* Save and Quit
* chmod u+x updateme.sh
* ./updateme.sh

That runs all the updates, upgrades, cleans up etc.  Also do not run this on production as it doesn't stop to ask, it just does!
