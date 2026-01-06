# Practical Exercises
There are particular approaches that an experienced network engineer will take when they are doing configurations, for a medium or large customer. There are some goals:

1.	Be as efficient as possible
2.	When I make a mess of things, recover as quickly as possible
3.	Be as accurate as possible there is no room for error.

One of the ways I have achieved this, is not to write configurations at the command line. When I'm working, I'm going to open notepad++ and I'm going to write my configuration into notepad++ with a minimum of comments. When I think the configuration is correct, I'll paste it into the network appliance and test it. For example, a good configuration for a normal client's access port might be

```
# Configure technical clients
int gi0/1
 description Clients
 switchport access vlan 5
 switchport mode access
 negotiation auto
 spanning-tree portfast edge
 spanning-tree bpduguard enable
```
To configure a range of ports, I can just chnage the first line to 
```
int range gi0/1-24
```
Note that the exact syntax might change from switch to switch.

Why do this with Notepad++?

1. If I reset the switch, I lose nothing.
2. If I must configure twenty switches in a consistemnt manner, I paste 20 times!
3. This is not _automation_, but it is the first real step in _Infrastructure as Code_ for my network.
4. My equipment configuration is now recoverable, if I forget to save before resetting, or if a device fails.
5. I have records of what I have done and a good script might last a few years and be usable on multipl projects before it needs updating.
6. I have all my build documentation for the client.

I could keep going, but you get the idea.

When  you are doing my practical exercises, use this methodology. You will discover by the time you have to do the first big network assignment, that you have almost no work to do!
