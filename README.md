# Target-Specification

## _program used_
* _nmap_

## _what is nmap?_
#### Gordon Lyon designed Nmap (Network Mapper), a free and open-source network scanner (also known by his pseudonym Fyodor Vaskovich). Nmap is a program that sends packets and analyzes the answers to find hosts and services on a computer network.

## _how does nmap work?_
#### Nmap is easy to use, and the majority of the tools it offers are familiar to system administrators from other programs. Nmap has the advantage of combining a variety of these capabilities into a single package, rather than forcing you to switch between other network monitoring programs. You must be comfortable with command-line interfaces in order to use Nmap. Although most sophisticated users can develop scripts to automate routine operations, basic network monitoring does not require this.

## _what seperates nmap from other scanners?_
#### The best thing about Nmap is it’s free and open source and is very flexible and versatile. Nmap is often used to determine alive hosts in a network, open ports on those hosts, services running on those open ports, and version identification of that service on that port. It can also run vulnerability assessment scripts to determine if a service is vulnerable. It can be used by penetration testers to identify open ports to gather more information about a target, or can be used by a security administrator to identify open ports in their systems but are not in use. With its usefulness, the security community have long accepted that Nmap is the de-facto tool for network mapping and host identification.

## _nmap synatx_
#### Now before I dive to examples, I want to break down how Nmap syntax is usually structured, as it is good practice to have this by memory. Although in my experience, sequence of flags is not that important(there are cases they are) most of the time. In fact, for a scan to proceed, Nmap only needs a target. This format is vague and is not required, but according to documentation, Nmap follows the format:
