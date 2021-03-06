PolicyCondition Object
=============================================================

*config/PolicyCondition*
------------------------------------

- Multiple objects of this type can exist in a system.

+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| **PARAMETER NAME** | **DATA TYPE** |          **DESCRIPTION**           | **DEFAULT** |        **VALID VALUES**        |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| Name **[KEY]**     | string        | PolicyConditionName                | N/A         | N/A                            |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| ConditionType      | string        | Specifies the match criterion      | N/A         | MatchProtocol,                 |
|                    |               | this condition defines             |             | MatchDstIpPrefix,              |
|                    |               |                                    |             | MatchSrcIpPrefix               |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| IpPrefix           | string        | Used in conjunction with           | N/A         | N/A                            |
|                    |               | MaskLengthRange to specify         |             |                                |
|                    |               | the IP Prefix to match on          |             |                                |
|                    |               | when the ConditionType is          |             |                                |
|                    |               | MatchDstIpPrefix/MatchSrcIpPrefix. |             |                                |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| MaskLengthRange    | string        | Used in conjuction with            | N/A         | N/A                            |
|                    |               | IpPrefix to specify specify        |             |                                |
|                    |               | the IP Prefix to match on          |             |                                |
|                    |               | when the ConditionType is          |             |                                |
|                    |               | MatchDstIpPrefix/MatchSrcIpPrefix. |             |                                |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| PrefixSet          | string        | Name of a pre-defined prefix       |             | N/A                            |
|                    |               | set to be used as a condition      |             |                                |
|                    |               | qualifier.                         |             |                                |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+
| Protocol           | string        | Protocol to match on if            | N/A         | CONNECTED, STATIC, OSPF, BGP   |
|                    |               | the ConditionType is set to        |             |                                |
|                    |               | MatchProtocol                      |             |                                |
+--------------------+---------------+------------------------------------+-------------+--------------------------------+



*OpxFlexSwitch CURL API Supported*
------------------------------------

	- GET By Key
		 curl -X GET -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/config/PolicyCondition
	- GET By ID
		 curl -X GET http://device-management-IP:8080/public/v1/config/PolicyCondition/<uuid>
	- GET ALL
		 curl -X GET http://device-management-IP:8080/public/v1/config/PolicyConditions?CurrentMarker=<x>&Count=<y>
	- CREATE(POST)
		 curl -X POST -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/config/PolicyCondition
	- DELETE By Key
		 curl -X DELETE -i -H 'Accept:application/json' -d '{<Model Object as json data>}' http://device-management-IP:8080/public/v1/config/PolicyCondition
	- DELETE By ID
		 curl -X DELETE http://device-management-IP:8080/public/v1/config/PolicyCondition<uuid>
	- UPDATE(PATCH) By Key
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/PolicyCondition
	- UPDATE(PATCH) By ID
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/PolicyCondition<uuid>


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
		response, error = swtch.getPolicyCondition(Name=name)

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
		response, error = swtch.getPolicyConditionById(ObjectId=objectid)

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
		response, error = swtch.getAllPolicyConditions()

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
		response, error = swtch.createPolicyCondition(Name=name, ConditionType=conditiontype, IpPrefix=ipprefix, MaskLengthRange=masklengthrange, PrefixSet=prefixset, Protocol=protocol)

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
		response, error = swtch.deletePolicyCondition(Name=name)

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
		response, error = swtch.deletePolicyConditionById(ObjectId=objectid

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
		response, error = swtch.updatePolicyCondition(Name=name, ConditionType=conditiontype, IpPrefix=ipprefix, MaskLengthRange=masklengthrange, PrefixSet=prefixset, Protocol=protocol)

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
		response, error = swtch.updatePolicyConditionById(ObjectId=objectidConditionType=conditiontype, IpPrefix=ipprefix, MaskLengthRange=masklengthrange, PrefixSet=prefixset, Protocol=protocol)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'
