---
title: "Mover servidor de administración central de Lync Server 2010 a Lync Server 2013"
TOCTitle: "Dépl. du serv. de gest. centralisée Lync Server 2010 vers Lync Server 2013"
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49889027
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover el servidor de administración central de Lync Server 2010 a Lync Server 2013

 

_**Última modificación del tema:** 2013-11-25_

Tras migrar desde el Lync Server 2010 a Lync Server 2013, tiene que mover el Lync Server 2010Servidor de administración central al Lync Server 2013Servidor front-end o grupo de servidores para poder quitar el servidor de Lync Server 2010 heredado.

El Servidor de administración central es un sistema de réplica múltiple/maestro único, en donde la copia de lectura/escritura de la base de datos se almacena en el Servidor front-end que contiene el Servidor de administración central. Todos los equipos de la topología, incluido el Servidor front-end que contiene el Servidor de administración central, tienen instalada en el equipo una copia de solo lectura de los datos del Almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) durante la instalación e implementación. La base de datos local recibe actualizaciones de réplicas por medio del agente de replicador de réplicas de Lync Server que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el Servidor de administración central y la réplica local es el XDS, el cual está conformado por los archivos xds.mdf y xds.ldf. Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en Servicios de dominio de Active Directory. Todas las herramientas que utilizan el Servidor de administración central para administrar y configurar Lync Server usan el SCP para ubicar el Almacén de administración central.

Tras migrar correctamente el Servidor de administración central, debe quitar las bases de datos del Servidor de administración central del Servidor front-end original. Para obtener información acerca de la eliminación de las bases de datos de Servidor de administración central, vea [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md).

Usa el cmdlet Windows PowerShell**Move-CsManagementServer** en el Shell de administración de Lync Server para mover la base de datos desde la base de datos de SQL Server de Lync Server 2010 a la base de datos de SQL Server de Lync Server 2013 y, a continuación, actualiza el SCP para que señale a la ubicación de Lync Server 2013Servidor de administración central.

## Preparación de Lync Server 2013Servidores front-end para mover el Servidor de administración central

Use los procedimientos de esta sección para preparar el Lync Server 2013Servidores front-end para mover el Lync Server 2010Servidor de administración central.

## Para preparar un Grupo de servidores front-end Enterprise Edition

1.  En el Lync Server 2013 Enterprise Edition Grupo de servidores front-end donde desea reubicar el Servidor de administración central: inicie sesión en el equipo donde el Shell de administración de Lync Server está instalado como miembro del grupo **RTCUniversalServerAdmins**. También debe tener permisos y derechos de usuario de sysadmin de la base de datos de SQL Server en la base de datos donde desea instalar el Almacén de administración central.

2.  Abra el Shell de administración de Lync Server.

3.  Para crear el nuevo Almacén de administración central en la base de datos de SQL Server de Lync Server 2013, en el Shell de administración de Lync Server, escriba:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Confirme que el estado del servicio **Lync Server Front-End** esté en **Iniciado**

## Para preparar un Servidor front-end Standard Edition

1.  En el Lync Server 2013 Standard Edition Servidor front-end donde desea reubicar el Servidor de administración central: inicie sesión en el equipo donde el Shell de administración de Lync Server está instalado como miembro del grupo **RTCUniversalServerAdmins**.

2.  Abra Asistente para la implementación de Lync Server.

3.  En la Asistente para la implementación de Lync Server, haga clic en **Preparar el primer servidor Standard Edition**.

4.  En la página **Ejecutar comandos**, SQL Server Express está instalado como el Servidor de administración central. Se crean las reglas de firewall necesarias. Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en **Finalizar**.
    

    > [!NOTE]
    > Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo.



5.  Para crear el nuevo Almacén de administración central en el Lync Server 2013 Standard Edition Servidor front-end, en el Shell de administración de Lync Server, escriba:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Confirme que el estado del servicio **Lync Server Front-End** esté en **Iniciado**

## Para mover el Lync Server 2010Servidor de administración central a Lync Server 2013

1.  En el servidor Lync Server 2013 que será el Servidor de administración central: inicie sesión en el equipo donde el Shell de administración de Lync Server está instalado como miembro del grupo **RTCUniversalServerAdmins**. También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server.

2.  Abra Shell de administración de Lync Server.

3.  En el Shell de administración de Lync Server, escriba:
    
        Enable-CsTopology
    
    > [!WARNING]  
    > Si <code>Enable-CsTopology</code> no se ejecuta correctamente, solucione el problema evitando que el comando se complete antes de continuar. Si <strong>Enable-CsTopology</strong> no se ejecuta correctamente, se producirá un error en la migración que puede dejar a la topología sin ningún Almacén de administración central.
    


4.  En el Lync Server 2013Servidor front-end o Grupo de servidores front-end, en el Shell de administración de Lync Server, escriba:
    
        Move-CsManagementServer

5.  El Shell de administración de Lync Server muestra los servidores, almacenes de archivos, almacenes de bases de datos y puntos de conexión de servicio del estado actual y el estado propuesto. Lea la información cuidadosamente y confirme que se trata del origen y el destino deseados. Escriba **S** para continuar o **N** para detener la migración.

6.  Revise las advertencias o los errores generados por el comando **Move-CsManagementServer** y resuélvalos.

7.  En el servidor de Lync Server 2013, abra la Asistente para la implementación de Lync Server.

8.  En Asistente para la implementación de Lync Server, haga clic en **Instalar o actualizar el sistema Lync Server**, en **Paso 2: Instalar o desinstalar componentes de Lync Server**, en **Siguiente**, revise el resumen y, a continuación, haga clic en **Finalizar**.

9.  En el servidor de Lync Server 2010, abra la Asistente para la implementación de Lync Server.

10. En Asistente para la implementación de Lync Server, haga clic en **Instalar o actualizar el sistema Lync Server**, en **Paso 2: Instalar o desinstalar componentes de Lync Server**, en **Siguiente**, revise el resumen y, a continuación, haga clic en **Finalizar**.

11. Reinicie el servidor de Lync Server 2013. Esto es necesario debido un cambio de pertenencia a grupos para acceder a la base de datos de Servidor de administración central.

12. Para confirmar que se está efectuando la replicación con el nuevo Almacén de administración central, en el Shell de administración de Lync Server, escriba:
    
        Get-CsManagementStoreReplicationStatus
    

    > [!NOTE]
    > Es posible que la replicación necesite bastante tiempo para actualizar todas las réplicas.



## Para quitar archivos de Lync Server 2010Almacén de administración central después de un movimiento

1.  En el servidor Lync Server 2010: inicie sesión en el equipo donde el Shell de administración de Lync Server está instalado como miembro del grupo **RTCUniversalServerAdmins**. También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server.

2.  Abra Shell de administración de Lync Server
    
    > [!WARNING]  
    > No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y esté estable. Si quita los archivos antes de completar la replicación, se interrumpirá el proceso de replicación y el Servidor de administración central migrado quedará en un estado desconocido. Utilice el cmdlet <strong>Get-CsManagementStoreReplicationStatus</strong> para confirmar el estado de la replicación.
    


3.  Para quitar los archivos de base de datos de Almacén de administración central del Lync Server 2010Servidor de administración central, escriba:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Por ejemplo:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Donde el *\<FQDN of SQL Server\>* es el servidor back-end de Lync Server 2010 en una implementación de Enterprise Edition o el FQDN del servidor Standard Edition.

