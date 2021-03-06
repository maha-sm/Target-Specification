# Target-Specification
## _Vedio Link_
#### https://drive.google.com/file/d/14anN2NdE9RZGKNEmmk_X60P4g19YgpZj/view?usp=sharing
## _program used_
* _nmap_

## _what is nmap?_
#### Gordon Lyon designed Nmap (Network Mapper), a free and open-source network scanner (also known by his pseudonym Fyodor Vaskovich). Nmap is a program that sends packets and analyzes the answers to find hosts and services on a computer network.

## _how does nmap work?_
#### Nmap is easy to use, and the majority of the tools it offers are familiar to system administrators from other programs. Nmap has the advantage of combining a variety of these capabilities into a single package, rather than forcing you to switch between other network monitoring programs. You must be comfortable with command-line interfaces in order to use Nmap. Although most sophisticated users can develop scripts to automate routine operations, basic network monitoring does not require this.

## _what seperates nmap from other scanners?_
#### The best thing about Nmap is it’s free and open source and is very flexible and versatile. Nmap is often used to determine alive hosts in a network, open ports on those hosts, services running on those open ports, and version identification of that service on that port. It can also run vulnerability assessment scripts to determine if a service is vulnerable. It can be used by penetration testers to identify open ports to gather more information about a target, or can be used by a security administrator to identify open ports in their systems but are not in use. With its usefulness, the security community have long accepted that Nmap is the de-facto tool for network mapping and host identification.

## _nmap syntax_
#### Now before we dive to examples, we want to break down how Nmap syntax is usually structured, as it is good practice to have this by memory. Although in our experience, sequence of flags is not that important(there are cases they are) most of the time. In fact, for a scan to proceed, Nmap only needs a target. This format is vague and is not required, but according to documentation, Nmap follows the format:

![image](https://user-images.githubusercontent.com/84526848/121815806-4418e480-cc89-11eb-91f3-466318ddc4ce.png)

## _basic scans_
#### Nmap has fairly intelligent defaults set, so you are able to just open up Nmap and run a scan without specifying anything but the target. So, why not try it out on a computer on your network. Scanning the computer running Kali isn't going to give you much of anything, so it's best to pick another computer that you own. If you already know the IP of one, awesome. If not, Nmap has a tool to get the IP addresses of the computers on your network.
![image](https://user-images.githubusercontent.com/84526848/121816157-0c12a100-cc8b-11eb-9734-277863036278.png)

#### What you'll see when Nmap finishes is a list of every devices that was reachable. Each device will have a name(if applicable), IP address, and MAC address with a manufacturer. By using the names and the hardware manufacturers, you should be able to tell what each device on your network is. Pick a computer that you own, and scan it.

![image](https://user-images.githubusercontent.com/84526848/121816219-71669200-cc8b-11eb-98cf-a3d89ac53798.png)

#### You can just write in the IP of that computer. Nmap will take a few seconds to probe the computer with packets and report back.
The report will be sort, but it will contain a list of ports with their state and which service they correspond to. It will also show that MAC address information and your IP again.
## _Useful Flags_
#### Even though the defaults do give some useful information, and you can tell which ports are open, it would still be nice to get some more data. Nmap has tons of flags that you can set to specify just how you would like it to run. There are way too many to cover in this basic guide, but you can always check out Nmap's detailed manpage for more.

## _-sS_
#### The -sS flag is the default scanning flag for Nmap. It just specifies the way that Nmap will scan. Even though it's the default, it's probably a good idea to specify it anyway.

## _-T_
#### Timing can be important. Not only does the timing of the scan determine how long scanning will take, but it can also be instrumental in triggering or not triggering firewalls and other safeguards on a target system. While Nmap offers more fine-grained timing control, it also provides a set of six pre-built timing schemes with the -T flag. These timings range from 0 through 5, with 0 being the slowest and least invasive and 5 being the fastest and most overt. -T3 is the default timing flag, but many users prefer -T4 to speed up the scan.

## _-iL_
#### You can use Nmap to scan multiple targets at once. Doing so can easily be done in-line when you run Nmap.
![image](https://user-images.githubusercontent.com/84526848/121816447-bb03ac80-cc8c-11eb-9e17-608b6b50a601.png)

 #### For a small number of targets this works, but it can quickly become cumbersome and isn't all that readily repeatable. The -iL flag imports a list of targets for Nmap to use. This way, you can save targets and repeat scans at a later date.
 #### Before running Nmap, open up your text editor of choice and enter in a couple of the IPs on your network.
 ![image](https://user-images.githubusercontent.com/84526848/121816500-159d0880-cc8d-11eb-9833-e7340fc48d2d.png)
 #### Save that file and run Nmap with the -iL flag.
 ![image](https://user-images.githubusercontent.com/84526848/121816598-978d3180-cc8d-11eb-9f2b-8d12fe4212bd.png)
 
 #### Nmap will read through the list and preform a scan on each entry.
 ## _-F_
 #### By default, Nmap will scan the 1000 most commonly used ports on a target machine. This, of course, takes time. If you know that you only need to or only want to scan the most common ports to reduce the run time of Nmap, you can use the -F flag. The -F flag tells Nmap to only scan the 100 most commonly used ports instead of the usual 1000.
 
 ![image](https://user-images.githubusercontent.com/84526848/121816666-f9e63200-cc8d-11eb-842e-ef0e7ac8b1b5.png)
 
 ## _-O_
 #### If you would like information on the operating system being run on the target machine, you can add the -O flag to tell Nmap to probe for operating system information as well. Nmap is not super accurate when it comes to operating system information, but it usually gets very close.
 
 ![image](https://user-images.githubusercontent.com/84526848/121816771-898be080-cc8e-11eb-9fac-c3ee8e86f74a.png)
 
 ## _-open_
 #### If you are only looking for which ports are open on a specific machine, you can tell Nmap to only look for open ports with the --open flag.
 ![image](https://user-images.githubusercontent.com/84526848/121816839-facb9380-cc8e-11eb-9f84-63bcef0d4d65.png)
 
 ## _-sV_
 #### Sometimes, it's useful to know what software and what versions of that software a machine is running. This is especially good for investigating your own servers. It also gives you insight into what server information others can see. Nmap's -sV allows you to get as detailed information as possible about the services running on a machine.
 ![image](https://user-images.githubusercontent.com/84526848/121816882-39614e00-cc8f-11eb-9437-cd7b61f78fd0.png)
 
 ## _-p_
 #### Occasionally, you may only want to scan select ports with Nmap. The -p flag allows you to specify specific ports for Nmap to scan. Nmap will then only scan those specified ports on the target machine.
 ![image](https://user-images.githubusercontent.com/84526848/121817053-226f2b80-cc90-11eb-9adb-b18bea1d1450.png)

#### This will take a long time, so it should not be done lightly.
## _-A_
#### By now, you've acquired a lot of flags to use. Using all of them together can be very awkward. Nmap has the -A for just this reason. It's sort of the "kitchen sink" flag that tells Nmap to aggressively gather as much information as it can.
 ![image](https://user-images.githubusercontent.com/84526848/121817162-b6d98e00-cc90-11eb-8379-9fce72a53f96.png)
 
## _Logging Output_
#### It would sure be able to store the results from Nmap. Well, you can. Nmap has yet another flag that allows you to store output in a variety of different formats. This is excellent for long scans like ones with the -p- flag. To use Nmap's logging capabilities, pass the -oN or -oX along with the name of the file. -oN logs the normal output. -oX logs the output as XML. By default, Nmap will overwrite existing logs with new ones, so be careful not to overwrite anything you don't want to.

![image](https://user-images.githubusercontent.com/84526848/121817218-120b8080-cc91-11eb-9547-4b67aa10cf0b.png)
#### You can find the full log in the text file when Nmap completes. If you want something ridiculous, try the -oS flag instead.
## _Team Members_
* Fatma Ates 18030411060
* Maha Elsayed 19030441009
