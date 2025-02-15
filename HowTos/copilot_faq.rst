.. meta::
  :description: Aviatrix CoPilot FAQs
  :keywords: CoPilot,visibility


============================================================
Aviatrix CoPilot FAQs
============================================================


What is the default login for CoPilot? 
====================================================

CoPilot authenticates against the Aviatrix Controller list of local users.  

Are the traffic flow records coming from controller or gateways?  
===============================================================================

The flows are sent from the Aviatrix gateways directly to CoPilot's instance.

How do ThreatGuard firewall policies interact with existing/new firewall policies applied to the same gateways? 
==============================================================================================================

The ThreatGuard drop policies are in addition to the existing firewall policies applied to the same gateways.  

What protocol does CoPilot use to talk to its controller? 
===============================================================================

CoPilot uses REST APIs and HTTPS to communicate with its controller.

How long does it take for data to start showing in FlowIQ? 
===============================================================================

It may take about 5 minutes for flow data to appear in the CoPilot UI. 

How are updates handled? Can I configure the update process?
===============================================================================

Updates are downloaded and applied automatically. The update process runs every 60 minutes. To stop updates, you can stop the update service under Settings > Services.

What is the smallest recommended Instance/VM size?  
===============================================================================

The configuration of the instance/virtual machine that you provision for your CoPilot deployment depends on the scale and the kind of networking infrastructure you have planned according to your business requirements. Work with your performance team to determine your sizing requirements.

- For the instance/VM size, CoPilot requires:

  - 4 GB of RAM (or more)

  - 1 attached disk/volume for storage (see `CoPilot Disk (Volume) Management <https://docs.aviatrix.com/HowTos/copilot_getting_started.html#id4>`_)

  - 2 vCPUs (or more)

CoPilot supports automatic memory sizing for the ETL and datastore based on the physical memory of the instance at boot. Base images default to the automatic settings. This auto-scaling memory support became available with the release of Aviatrix CoPilot image version 1.5.1. 

Prior to CoPilot image version 1.5.1, CoPilot required a minimum of 8 vCPUs and 32 GB Memory.

Can I configure flows to be sent over private IPs? 
===============================================================================

CoPilot does not set up a private overlay between the gateways and itself. If a private communication path between the gateways and CoPilot is available, then you can use CoPilot’s private IP when you input the collector IP in the controller. 
For example, if you have an Aviatrix transit gateway, and you put CoPilot in one of the spokes, then you can use CoPilot’s private IP as the destination. 


Does CoPilot hold any user or sensitive data?  
===============================================================================

CoPilot does not hold user-identifiable or payment processing information. CoPilot does not hold credentials on the appliance’s storage. However, it is always recommended to follow security best practices for a secure CoPilot deployment. 

Can I Encrypt Volumes for CoPilot?
===============================================================================

Yes, you can encrypt disks (volumes) that you allocate to your CoPilot deployment. You enable the encryption via your cloud service provider. Refer to your cloud service provider for information about enabling disk (volume) encryption.  

How does CoPilot get its data?
===============================================================================

1.Controller APIs

  CoPilot makes API calls into the controller to retrieve information.

2.Flow records

  Aviatrix Gateways generate and export information about network traffic. Flows come directly from  Gateways to CoPilot.
  

If Controller IP changes and if copilot is associated with an old controller IP, how to login into Copilot?
============================================================================================================

If you are logged in to copilot go to Copilot UI -> Settings and click on the 'Reset controller IP' button. It will prompt you to enter the new Controller IP address and service account credentials.

If you are logged out of Copilot, please open a support ticket at `Aviatrix Support Portal <https://support.aviatrix.com>`_ for a solution.


Is FlowIQ showing realtime traffic? 
===============================================================================

Flow records are generated by the Gateways. The agent on the Gateways observes and keeps track of the flows and as soon as a particular flow ends, or if the flow expiry interval is reached, the flow record is sent to CoPilot.


Can the data retention be adjusted ? 
===============================================================================

Today you can set a threshold based on disk space available, so that you can remove the old records.


Can we provide bandwidth details of links ?
===============================================================================
If you can specify source and destination for the two endpoints of the path (gateways), you can obtain this information from FlowIQ by using filters.


Why do I get an error Failed to fetch Topology when I open the Topology page?
===============================================================================

If you get the error **Failed to fetch Topology data**, CoPilot was unable to access the data it needs for topology. If the issue persists, Contact Aviatrix Support.

How can I get my additional questions answered ?
===============================================================================

Visit Aviatrix.com and use the live chat icon to talk to a live expert.
