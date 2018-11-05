---
title: Quitar la base de datos SQL Server en un servidor de supervisión
TOCTitle: Quitar la base de datos SQL Server en un servidor de supervisión
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49889534
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar la base de datos SQL Server en un servidor de supervisión

 

_**Última modificación del tema:** 2012-10-04_

Tras quitar un Microsoft Lync Server 2010 de Servidor de supervisión, podrá quitar las bases de datos de SQL Server donde se hospedaban los datos del servidor. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías, y luego quite los archivos de bases de datos y de registro del servidor de base de datos.

## Para quitar la base de datos de SQL Server con el Generador de topologías

1.  En el servidor front-end Lync Server 2013, abra el Generador de topologías.

2.  En el Generador de topologías, navegue hasta **Shared Components** y luego hasta **SQL Server Stores** , haga clic con el botón secundario en la instancia de SQL Server asociada al Servidor de supervisión quitado o reconfigurado, y haga clic en **Eliminar** .

3.  Publique la topología y compruebe el estado de replicación.

## Para quitar los archivos de bases de datos de SQL Server

1.  Para quitar las bases de datos del servidor basado en SQL Server, el usuario debe ser miembro del grupo sysadmins de SQL Server en el servidor SQL Server del que se quitarán los archivos de bases de datos.

2.  Abra Shell de administración de Lync Server.

3.  En la línea de comandos, escriba:
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde *\<FQDN\>* es el nombre de dominio completo (FQDN) del servidor de base de datos e *\<instance\>* es la instancia opcional de base de datos con nombre.

4.  Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y presione **Y** (o Entrar) para continuar, o bien presione **N** y luego Entrar si desea detener el cmdlet (es decir, en caso de errores).

