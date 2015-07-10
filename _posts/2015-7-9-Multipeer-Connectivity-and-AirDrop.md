---
layout: post
title: Multipeer Connectivity and AirDrop (iOS)
---
The Multipeer Connectivity Framework is designed to provide an abstract layer for developers to take advantage of the iPhone’s mobile ad hoc Wi-Fi, traditional infrastructure Wi-Fi,  and Bluetooth personal area networking capabilities. 
By being able to send data through ad hoc Wi-Fi networks and Bluetooth, iPhones can communicate directly with other iPhones and mac computers without first sending data to a wireless access point (like a router). 
For example, one device with only Bluetooth on can communicate with another device with only Wi-Fi on, if the two devices send data through a third device with both Wi-Fi and Bluetooth enabled.

Apple makes use of these same networking capabilities in AirDrop; a feature of iPhones and macs that allows users to send anything iPhones store on their Share sheet (ex. photos, videos, contacts, etc.) to other iPhone and mac devices, even without connecting to the internet. 
What makes AirDrop particularly powerful is its ability to take advantage of Bluetooth and Wi-Fi. AirDrop uses Bluetooth to broadcast, discover, and negotiate connections to other devices and Wi-Fi to actually transfer the data between devices.

Bluetooth uses much less power than Wi-Fi to search, broadcast, and connect to other devices, making it a very useful tool to perform these functions. 
The downside to bluetooth is that it takes significantly longer to transfer data than Wi-Fi. 
AirDrop, therefore, uses the networking capabilities of the devices it runs on to optimize performance by using the best of both worlds; searching, broadcasting, and connecting to devices through bluetooth, establishing a Wi-Fi connection with the another device, and transferring data through that Wi-Fi connection. 

While AirDrop and the MC Framework use the same underlying technology, AirDrop can only handle peer-to-peer connections, while apps running on the MC Framework have the ability to send data to multiple devices (hence ‘Multipeer’). 
AirDrop makes use of both Wi-Fi and bluetooth, so both must be enabled on two devices for those devices to communicate with each other. 
Additionally, due to the complexity and constant changing of connections in ad hoc networks, AirDrop only allow users to share data with one device at a time. 
This ensures a user’s data is transferred to the other device as fast and as safe as possible (AirDrop encrypts data, making it even safer than sending emails which would go through a wireless access point). 
This is significantly different than a multi-peer network.

A multi-peer network allows multiple users to communicate with one another all at the same time. 
This makes transferring data to devices more difficult, since devices are constantly entering and leaving the ad hoc network. 
It also makes data less safe, since data is now being transferred through multiple devices. 
It does, however, provide a network for interesting apps to take advantage of. 
FireChat, for example, uses the MC Framework to allow users to communicate with one another in a chat room solely through the ad hoc network. 
This means users can chat with multiple devices simultaneously, even without an internet connection. 
