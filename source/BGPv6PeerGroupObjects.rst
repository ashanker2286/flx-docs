BGPv6PeerGroup Object
=============================================================

*config/BGPv6PeerGroup*
------------------------------------

- Multiple objects of this type can exist in a system.

+-------------------------+---------------+--------------------------------+-------------+------------------+
|   **PARAMETER NAME**    | **DATA TYPE** |        **DESCRIPTION**         | **DEFAULT** | **VALID VALUES** |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| Name **[KEY]**          | string        | Name of the BGP peer group     | N/A         | N/A              |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| AdjRIBInFilter          | string        | Policy that is applied for     |             | N/A              |
|                         |               | Adj-RIB-In prefix filtering    |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| KeepaliveTime           | uint32        | Keep alive time for the BGP    |           0 | N/A              |
|                         |               | neighbor                       |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| MaxPrefixesDisconnect   | bool          | Disconnect the BGP peer        | false       | N/A              |
|                         |               | session when we receive the    |             |                  |
|                         |               | max prefixes from the neighbor |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| RouteReflectorClient    | bool          | Set/Clear BGP neighbor as a    | false       | N/A              |
|                         |               | route reflector client         |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| ConnectRetryTime        | uint32        | Connect retry time to          |           0 | N/A              |
|                         |               | connect to BGP neighbor after  |             |                  |
|                         |               | disconnect                     |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| MaxPrefixesRestartTimer | uint8         | Time to wait before we start   |           0 | N/A              |
|                         |               | BGP peer session when we       |             |                  |
|                         |               | receive max prefixes           |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| MaxPrefixesThresholdPct | uint8         | The percentage of maximum      |          80 | N/A              |
|                         |               | prefixes before we start       |             |                  |
|                         |               | logging                        |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| PeerAS                  | string        | Peer AS of the BGP neighbor    |             | N/A              |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| AddPathsMaxTx           | uint8         | Max number of additional paths |           0 | N/A              |
|                         |               | that can be transmitted to BGP |             |                  |
|                         |               | neighbor                       |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| AddPathsRx              | bool          | Receive additional paths from  | false       | N/A              |
|                         |               | BGP neighbor                   |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| Description             | string        | Description of the BGP         |             | N/A              |
|                         |               | neighbor                       |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| LocalAS                 | string        | Local AS of the BGP neighbor   |             | N/A              |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| MaxPrefixes             | uint32        | Maximum number of prefixes     |           0 | N/A              |
|                         |               | that can be received from the  |             |                  |
|                         |               | BGP neighbor                   |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| RouteReflectorClusterId | uint32        | Cluster Id of the internal     |           0 | N/A              |
|                         |               | BGP neighbor route reflector   |             |                  |
|                         |               | client                         |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| AdjRIBOutFilter         | string        | Policy that is applied for     |             | N/A              |
|                         |               | Adj-RIB-Out prefix filtering   |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| HoldTime                | uint32        | Hold time for the BGP neighbor |           0 | N/A              |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| MultiHopEnable          | bool          | Enable/Disable multi hop for   | false       | N/A              |
|                         |               | BGP neighbor                   |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| MultiHopTTL             | uint8         | TTL for multi hop BGP neighbor |           0 | N/A              |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| NextHopSelf             | bool          | Use neighbor source IP as the  | false       | N/A              |
|                         |               | next hop for IBGP neighbors    |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+
| UpdateSource            | string        | Source IP to connect to the    |             | N/A              |
|                         |               | BGP neighbor                   |             |                  |
+-------------------------+---------------+--------------------------------+-------------+------------------+



*OpxFlexSwitch CURL API Supported*
------------------------------------

	- GET By Key
		 curl -X GET -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup
	- GET By ID
		 curl -X GET http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup/<uuid>
	- GET ALL
		 curl -X GET http://device-management-IP:8080/public/v1/config/BGPv6PeerGroups?CurrentMarker=<x>&Count=<y>
	- CREATE(POST)
		 curl -X POST -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup
	- DELETE By Key
		 curl -X DELETE -i -H 'Accept:application/json' -d '{<Model Object as json data>}' http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup
	- DELETE By ID
		 curl -X DELETE http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup<uuid>
	- UPDATE(PATCH) By Key
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup
	- UPDATE(PATCH) By ID
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/BGPv6PeerGroup<uuid>


*OpxFlexSwitch SDK API Supported:*
------------------------------------



- **GET**


::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getBGPv6PeerGroup(Name=name)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **GET By ID**


::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getBGPv6PeerGroupById(ObjectId=objectid)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'




- **GET ALL**


::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getAllBGPv6PeerGroups()

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **CREATE**

::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.createBGPv6PeerGroup(Name=name, AdjRIBInFilter=adjribinfilter, KeepaliveTime=keepalivetime, MaxPrefixesDisconnect=maxprefixesdisconnect, RouteReflectorClient=routereflectorclient, ConnectRetryTime=connectretrytime, MaxPrefixesRestartTimer=maxprefixesrestarttimer, MaxPrefixesThresholdPct=maxprefixesthresholdpct, PeerAS=peeras, AddPathsMaxTx=addpathsmaxtx, AddPathsRx=addpathsrx, Description=description, LocalAS=localas, MaxPrefixes=maxprefixes, RouteReflectorClusterId=routereflectorclusterid, AdjRIBOutFilter=adjriboutfilter, HoldTime=holdtime, MultiHopEnable=multihopenable, MultiHopTTL=multihopttl, NextHopSelf=nexthopself, UpdateSource=updatesource)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **DELETE**

::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.deleteBGPv6PeerGroup(Name=name)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **DELETE By ID**

::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.deleteBGPv6PeerGroupById(ObjectId=objectid

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **UPDATE**

::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.updateBGPv6PeerGroup(Name=name, AdjRIBInFilter=adjribinfilter, KeepaliveTime=keepalivetime, MaxPrefixesDisconnect=maxprefixesdisconnect, RouteReflectorClient=routereflectorclient, ConnectRetryTime=connectretrytime, MaxPrefixesRestartTimer=maxprefixesrestarttimer, MaxPrefixesThresholdPct=maxprefixesthresholdpct, PeerAS=peeras, AddPathsMaxTx=addpathsmaxtx, AddPathsRx=addpathsrx, Description=description, LocalAS=localas, MaxPrefixes=maxprefixes, RouteReflectorClusterId=routereflectorclusterid, AdjRIBOutFilter=adjriboutfilter, HoldTime=holdtime, MultiHopEnable=multihopenable, MultiHopTTL=multihopttl, NextHopSelf=nexthopself, UpdateSource=updatesource)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **UPDATE By ID**

::

	import sys
	import os
	from opxflexswitchV2 import OpxFlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = OpxFlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.updateBGPv6PeerGroupById(ObjectId=objectidAdjRIBInFilter=adjribinfilter, KeepaliveTime=keepalivetime, MaxPrefixesDisconnect=maxprefixesdisconnect, RouteReflectorClient=routereflectorclient, ConnectRetryTime=connectretrytime, MaxPrefixesRestartTimer=maxprefixesrestarttimer, MaxPrefixesThresholdPct=maxprefixesthresholdpct, PeerAS=peeras, AddPathsMaxTx=addpathsmaxtx, AddPathsRx=addpathsrx, Description=description, LocalAS=localas, MaxPrefixes=maxprefixes, RouteReflectorClusterId=routereflectorclusterid, AdjRIBOutFilter=adjriboutfilter, HoldTime=holdtime, MultiHopEnable=multihopenable, MultiHopTTL=multihopttl, NextHopSelf=nexthopself, UpdateSource=updatesource)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'
