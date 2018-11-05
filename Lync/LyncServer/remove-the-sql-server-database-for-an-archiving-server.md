---
title: Quitar la base de datos de SQL Server para un servidor de archivado
TOCTitle: Quitar la base de datos de SQL Server para un servidor de archivado
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49889224
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar la base de datos de SQL Server para un servidor de archivado

 

_**Última modificación del tema:** 2012-10-04_

Tras quitar un Servidor de archivado de  Microsoft Lync Server 2010, puede quitar las bases de datos de SQL Server donde se hospedaban los datos del grupo en cuestión. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, seguidamente, quite los archivos de registro y base de datos del servidor de base de datos.

## Para quitar la base de datos de SQL Server con el Generador de topologías

1.  En el servidor front-end Lync Server 2013, abra el Generador de topologías.

2.  En Generador de topologías, vaya a **Componentes compartidos** y, a continuación, a **Almacenes de SQL Server**, haga clic con el botón derecho en la instancia de SQL Server asociada al Servidor de archivado quitado o reconfigurado y haga clic en **Eliminar**.

3.  Publique la topología y compruebe el estado de replicación.

## Para quitar los archivos de bases de datos de SQL Server

1.  Para quitar las bases de datos del servidor SQL Server, es necesario que pertenezca al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos.

2.  Abra Shell de administración de Lync Server.

3.  En la línea de comandos, escriba:
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde *\<FQDN\>* es el nombre de dominio completo (FQDN) del servidor de base de datos e *\<instance\>* es la instancia de base de datos con nombre (si hay una definida).

4.  Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y presione **Y** (o Entrar) para continuar, o bien presione **N** y luego Entrar si desea detener el cmdlet (es decir, en caso de errores).

