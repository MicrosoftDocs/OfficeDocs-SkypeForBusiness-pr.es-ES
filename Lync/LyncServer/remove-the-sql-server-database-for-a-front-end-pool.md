---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
TOCTitle: Quitar la base de datos de SQL Server para un grupo de servidores front-end
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49889219
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar la base de datos de SQL Server para un grupo de servidores front-end

 

_**Última modificación del tema:** 2012-10-04_

Después de quitar un Grupo de servidores front-end de Microsoft Lync Server 2010 o volver a configurar un grupo para que use una base de datos distinta, puede quitar las bases de datos de SQL Server donde se hospedaban los datos del grupo en cuestión. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, seguidamente, quitar la base de datos y los archivos de registro del servidor de base de datos.

## Para quitar la base de datos de SQL Server con el Generador de topologías

1.  En el servidor front-end de Lync Server 2013, abra el Generador de topologías y descargue la topología existente.

2.  En Generador de topologías, vaya a **Componentes compartidos** y, a continuación, a **Almacenes de SQL Server**, haga clic con el botón derecho en la instancia de SQL Server asociada al Grupo de servidores front-end quitado o reconfigurado y haga clic en **Eliminar**.

3.  Publique la topología y compruebe el estado de replicación.

## Para quitar bases de datos de usuarios y aplicaciones del servidor SQL Server

1.  Para quitar las bases de datos del servidor SQL Server, es necesario que pertenezca al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos.

2.  Abra Shell de administración de Lync Server

3.  Escriba lo siguiente para quitar la base de datos correspondiente al almacén de usuarios del grupo:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde *\<FQDN\>* es el nombre de dominio completo (FQDN) del servidor de base de datos e *\<instance\>* es la instancia de base de datos con nombre (si hay una definida).

4.  Escriba lo siguiente para quitar la base de datos correspondiente al almacén de aplicaciones del grupo:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde *\<FQDN\>* es el FQDN del servidor de base de datos e *\<instance\>* , la instancia de base de datos con nombre (si hay una definida).

5.  Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y presione **Y** (o Entrar) para continuar, o bien presione **N** y luego Entrar si desea detener el cmdlet (es decir, en caso de errores).

