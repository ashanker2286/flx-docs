AlarmState Object
=============================================================

*state/Alarm*
------------------------------------

- Multiple objects of this type can exist in a system.

+----------------------+---------------+--------------------------------+-------------+------------------+
|  **PARAMETER NAME**  | **DATA TYPE** |        **DESCRIPTION**         | **DEFAULT** | **VALID VALUES** |
+----------------------+---------------+--------------------------------+-------------+------------------+
| EventName **[KEY]**  | string        | Alarm event name picked up     | N/A         | N/A              |
|                      |               | from events.json               |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| OwnerId **[KEY]**    | int32         | Alarm owner daemon Id picked   | N/A         | N/A              |
|                      |               | up from events.json            |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| OwnerName **[KEY]**  | string        | Alarm owner daemon name picked | N/A         | N/A              |
|                      |               | up from events.json            |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| EventId **[KEY]**    | int32         | Alarm event id picked up from  | N/A         | N/A              |
|                      |               | events.json                    |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| SrcObjName **[KEY]** | string        | Alarm event name picked up     | N/A         | N/A              |
|                      |               | from events.json               |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| ResolutionReason     | string        | Cleared/Disabled               | N/A         | N/A              |
+----------------------+---------------+--------------------------------+-------------+------------------+
| SrcObjUUID           | string        | Fault Object UUID              | N/A         | N/A              |
+----------------------+---------------+--------------------------------+-------------+------------------+
| OccuranceTime        | string        | Timestamp at which fault       | N/A         | N/A              |
|                      |               | occured                        |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| ResolutionTime       | string        | Resolution Time stamp          | N/A         | N/A              |
+----------------------+---------------+--------------------------------+-------------+------------------+
| Severity             | string        | Alarm Severity                 | N/A         | N/A              |
+----------------------+---------------+--------------------------------+-------------+------------------+
| Description          | string        | Description explaining the     | N/A         | N/A              |
|                      |               | fault                          |             |                  |
+----------------------+---------------+--------------------------------+-------------+------------------+
| SrcObjKey            | string        | Fault Object Key               | N/A         | N/A              |
+----------------------+---------------+--------------------------------+-------------+------------------+



*OpxFlexSwitch CURL API Supported*
------------------------------------

	- GET By Key
		 curl -X GET -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/state/Alarm
	- GET ALL
		 curl -X GET http://device-management-IP:8080/public/v1/state/Alarms?CurrentMarker=<x>&Count=<y>
	- GET By ID
		 curl -X GET http://device-management-IP:8080/public/v1/config/AlarmState/<uuid>


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
		response, error = swtch.getAlarmState(EventName=eventname, OwnerId=ownerid, OwnerName=ownername, EventId=eventid, SrcObjName=srcobjname)

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
		response, error = swtch.getAlarmStateById(ObjectId=objectid)

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
		response, error = swtch.getAllAlarmStates()

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


