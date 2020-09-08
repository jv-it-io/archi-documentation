# PLATO-DOC
Project with the documentation for PLATO

Plato Lesson learn (15/05)
--------------------------

1. Connexion with cadastre 
	- no more write between 2 DB. Use flux from Cadastre to feed.
		* Manage delta with the data in the DB
		* Service rest in front of RO Db oracle Plato (proxy to get information from cadastre) so remove what is owned by plato
		
2. Off line 
	- Complaint (V1) and Forms (eventually) 
	- Data for a user not from other user
	- Techno for offline ? 
		* webworkers (something like cron) or other techno  -> POC

3. Document Generation
	- as is : work with a soft that is not perfect (from template word) : problem pagination  
		* tymleaf project : pdf generation ?  -> can use for transform template to html 
		
4. Report data 
	- as is : excel generation 
	- use the current way but take into account that we have to connect BI (report fonctionnal) Procost (Activities) 
	- cut service : 
		*one for plato business , 
		*one for report (furur connect with DWH) : so we need a view to get information from DWH (example activities from XX/XX/XXXX) 
	- Plato outbox for sendinf data to DWH 
5. Cutting service 
	- Gateway
	- BackOffice
		- Pharmacy
		- Activities: 
			* input fill in plato and send to procost
			* input in procost
		- Apostil 
		- Judicial Case
		- Inspections
	- Reporting Monolithic (DWH)  --> *Api gateway ? just a link between the 2 app with the SSO 
		- findings
		- inspection
		- omega report 
		(- activities) 
	- µservice link with AutoControl 
		* api rest to question Api autocontrol?
		* Service to feed plato data ?  
		-> handle exception 
	- µservice cadastre (if we need) 
		
Technical issues: 
------------------
Springboot / angular 
	- For front end : 
		* Prime NG
		* Think like state machine (prez from Aymen) ? 
		* Micro Front end ? interresting for the front end of report (Shut down to replace for interface BI) 
		* switch apigateway 
		
jenkins build multi branch 
	/!\ only one artefact 
	

-----------------------------------
Business Questions: 
-------------------
1. Case if inspector want to take the work of another inspector ? re-assign pharmacy  
