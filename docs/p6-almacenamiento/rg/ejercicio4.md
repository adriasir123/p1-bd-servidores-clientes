# Ejercicio 4

Queremos limpiar nuestro fichero tnsnames.ora. Averiguad cuales de sus entradas se están usando en algún enlace de la base de datos.

Para limpiar un archivo tnsnames.ora, puede seguir los siguientes pasos:

1- Primero realizarenmos una copia de seguridad del archivo tnsnames.ora original antes de realizar cualquier cambio.

2- Seguidamente analizamos cada entrada en el archivo y verifique si está siendo utilizada actualmente. Para hacer esto ejecutamos el siguiente comando:

```shell
oracle@oracle:~$ lsnrctl status

LSNRCTL for Linux: Version 19.0.0.0.0 - Production on 26-JAN-2023 01:24:42

Copyright (c) 1991, 2019, Oracle.  All rights reserved.

Connecting to (DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=0.0.0.0)(PORT=1521)))
STATUS of the LISTENER
------------------------
Alias                     LISTENER
Version                   TNSLSNR for Linux: Version 19.0.0.0.0 - Production
Start Date                17-JAN-2023 20:40:57
Uptime                    8 days 4 hr. 43 min. 44 sec
Trace Level               off
Security                  ON: Local OS Authentication
SNMP                      OFF
Listener Parameter File   /opt/oracle/product/19c/dbhome_1/network/admin/listener.ora
Listener Log File         /opt/oracle/diag/tnslsnr/oracle/listener/alert/log.xml
Listening Endpoints Summary...
  (DESCRIPTION=(ADDRESS=(PROTOCOL=tcp)(HOST=0.0.0.0)(PORT=1521)))
  (DESCRIPTION=(ADDRESS=(PROTOCOL=ipc)(KEY=EXTPROC1521)))
  (DESCRIPTION=(ADDRESS=(PROTOCOL=tcps)(HOST=oracle)(PORT=5500))(Security=(my_wallet_directory=/opt/oracle/admin/ORCLCDB/xdb_wallet))(Presentation=HTTP)(Session=RAW))
Services Summary...
Service "ORCLCDB" has 1 instance(s).
  Instance "ORCLCDB", status READY, has 1 handler(s) for this service...
Service "ORCLCDBXDB" has 1 instance(s).
  Instance "ORCLCDB", status READY, has 1 handler(s) for this service...
Service "PSQLU" has 1 instance(s).
  Instance "PSQLU", status UNKNOWN, has 1 handler(s) for this service...
Service "ec44a9570a350f2ae0530101007f64cf" has 1 instance(s).
  Instance "ORCLCDB", status READY, has 1 handler(s) for this service...
Service "orclpdb1" has 1 instance(s).
  Instance "ORCLCDB", status READY, has 1 handler(s) for this service...
The command completed successfully
```

3- Abrimos  el archivo tnsnames.ora en un editor de texto.

```shell
oracle@oracle:/opt/oracle/product/19c/dbhome_1$ nano network/admin/tnsnames.ora 

# tnsnames.ora Network Configuration File: /opt/oracle/product/19c/dbhome_1/network/admin/tnsnames.ora
# Generated by Oracle configuration tools.

ORCLCDB =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracle)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = ORCLCDB)
    )
  )

LISTENER_ORCLCDB =
  (ADDRESS = (PROTOCOL = TCP)(HOST = oracle)(PORT = 1521))

PSQLU  =
  (DESCRIPTION=
    (ADDRESS=(PROTOCOL=tcp)(HOST=localhost)(PORT=1521))
    (CONNECT_DATA=(SID=PSQLU))
    (HS=OK)
  )
```

4- Eliminamos las entradas que no estén siendo utilizadas, en nuestro caso eliminaríamos las entradas de LISTERNER_ORCLCDB y PSQLU:

```shell
oracle@oracle:/opt/oracle/product/19c/dbhome_1$ nano network/admin/tnsnames.ora 

# tnsnames.ora Network Configuration File: /opt/oracle/product/19c/dbhome_1/network/admin/tnsnames.ora
# Generated by Oracle configuration tools.

ORCLCDB =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracle)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = ORCLCDB)
    )
  )
```

5- Verificamos que no haya errores después de limpiar el archivo tnsnames.ora ejecutando una prueba de conexión a la base de datos:

```shell
oracle2@oracle2:~$ tnsping ORCLCDB

TNS Ping Utility for Linux: Version 19.0.0.0.0 - Production on 01-FEB-2023 01:48:22

Copyright (c) 1991, 2019, Oracle.  All rights reserved.

Used parameter files:
/opt/oracle/product/19c/dbhome_1/network/admin/sqlnet.ora

Used TNSNAMES adapter to resolve the alias
Attempting to contact (DESCRIPTION = (ADDRESS = (PROTOCOL = TCP)(HOST = oracle)(PORT = 1521)) (CONNECT_DATA = (SERVER = DEDICATED) (SERVICE_NAME = ORCLCDB)))
OK (120 msec)
```

Hay que tener en cuenta que el archivo tnsnames.ora es un archivo de configuración crítico para la conexión a la base de datos Oracle, por lo que es importante ser cuidadoso al realizar cambios en él.