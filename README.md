# This is the BIG hacking adventure performed by Manuel Manrique and Ricardo Rubin - Browser Exploitation Framework and phishing simulation

This project demonstrates legal and controlled browser exploitation techniques using BeEF (Browser Exploitation Framework), including:
- Browser hook deployment
- Internal reconnaissance from a hooked browser
- Basic social engineering simulation
- Mitigation with Content Security Policy (CSP) and browser hardening

**Reproducible**, fully documented in razor language (Genshin Impact Reference = Instructions for slow-process brains).

> All activities are performed on consented systems in a closed laboratory network for educational purposes only. DON'T DO CRIMES.

***Software used and versions***
BeEF (Browser Exploitation Framework)   -version 0.5.4.0                           -source Installed from GitHub release source
Kali Linux VM	                        -version Latest Rolling release (2025-xx)  
VM                                      -Spects       -processors 4       -RAM 4GB       -50GB Disk

Windows Host	                        -version Windows 11	                       -notes Browser target + Panel access
Windows VM                              -version Windows 10                        -notes Victim machine 
Ruby                                    -version 3.x (system default)	           -notes Required by BeEF 0.5.4.0
Browser Chrome/Edge	                                                               -notes Victim browser

***Installation***

Official GitHub releases page:
https://github.com/beefproject/beef/releases

***Steps Summary***
1- In your Kali VM use command 
*wget https://github.com/beefproject/beef/archive/refs/tags/v0.5.4.0.tar.gz -O beef.tar.gz* to download archive v0.5.4.0 to your computer.

2- Extract the file into ~/beef

3- Verify your Ruby Version in Kali, it should be already installed, but if not install it with 
*sudo apt install -y ruby ruby-dev bundler build-essential curl git*
and verify with *ruby -v*, once done that execute command *bundle install* to get all gems required by BeEF.

Note - When installing BeEF bundle you might encounter with two issues 
    
    1- Needed elevated privileges on the file to install
    2- Not being able to install all the gems

To solve this follow instructions:
    
    Issue 1: Use *sudo* before *bundle install* You will receive an alert saying "Don't do this or you'll die" Jk, you will receive a warning saying if root permissions are used when installing bundle non-root users will have a broken service, but we don't care about this here since we just want the VM for hosting BeEF with root user.

    Issue 2: Bundle gave me a hard time dealing with gems, so to avoid this just run ./beef, list all missing gems and run *sudo gem install* with the -version (version number) to manually install these gems and then be able to run beef.

    Issue ?: You might be asked to remove the default credentials from the config.yaml file, just do it and you'll be fine.

Once this issues are solved, just start the service with *./beef*

If you want to run BeEF as a service go to "Docs" and find the guide. 

***Attack Scenario***

To perform the attack you should refer to the Attack guide with instructions on how to replicate the attack and then, enhance it and make it work in a real life scenario.
This lab demonstrates a client-side exploitation scenario using the Browser Exploitation Framework (BeEF). By persuading the victim to click a malicious link (phishing), the attacker can execute JavaScript in the victim’s browser, gain remote control, and perform reconnaissance on internal networks.

***Hardening instructions***

Same as the attack scenario, there is a guide available to follow and replicate how to harden the defenses against this type of attack. Remember to always have the strongest shield. The effectiveness of the attack was reduced by applying browser hardening techniques such as disabling WebRTC/WebSockets, enforcing a strict Content Security Policy (CSP), and minimizing untrusted browser extensions. These layered defenses prevented BeEF from establishing command-and-control channels, immediately breaking persistence and blocking further exploitation attempts.
