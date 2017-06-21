
--------------------
INFOTAVL MODULE
--------------------
Modulet bruges til at vise en besked i et popup vindue. 
Hver besked bliver kun vist én gang per bruger; 

--------------------
INSTALLATION
--------------------

1: Installation

1.  Opret tabel i postgres:

	CREATE TABLE mtuserdata.infotavl_beskeder
		(
		  message character varying,
		  id serial NOT NULL,
		  expire_date date,
		  link character varying,
		  title character varying,
		  users_id character varying[],
		  CONSTRAINT infotavl_beskeder_pkey PRIMARY KEY (id)
		)
	
    ret tabelnavn hvis det er nødvendigt	

    

2: Registrere modulet     
   <module name="infotavl" dir="custom/infotavl" permissionlevel="public" />
   
   ret placering hvis det er nødvendigt.

3: Registrere tool
	<tool displayname="infotavl" module="infotavl" name="infotavl"/>
   
--------------------
DEPENDENCIES
--------------------
Popup er lavet ved brug af bootstrap biblioteket: http://getbootstrap.com/javascript/#modals

Hvis man har ét andet modul der bruger bootstrap på siden, skal man huske at "require" bootstrap.js kun én gang.

<file type="script" name="/modules/infotavl/css/bootstrap/js/bootstrap.min.js" priority="6"/>

Den øverste linje skal udkommenteres i ét af modulerne. 

