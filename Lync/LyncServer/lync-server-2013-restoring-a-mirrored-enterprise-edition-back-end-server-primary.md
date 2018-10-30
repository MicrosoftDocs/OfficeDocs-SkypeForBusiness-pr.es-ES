---
title: "Rest. d’un serv. Princ. Enterprise Edition en miroir - Base de données prim."
TOCTitle: "Rest. d’un serv. Princ. Enterprise Edition en miroir - Base de données prim."
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945648(v=OCS.15)
ms:contentKeyID: 52061724
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar un servidor back-end Enterprise Edition reflejado: principal

 

_**Última modificación del tema:** 2013-02-17_

Siga los procedimientos descritos en esta sección si posee un servidor back-end Enterprise Edition en una configuración reflejada y se produce un error únicamente en la base de datos principal. Si el error tiene lugar tanto en la base de datos principal como en la reflejada, vea [Restaurar un servidor back-end Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si el error solo sucede en la base de datos reflejada, vea [Restaurar un servidor back-end Enterprise Edition reflejado: reflejar](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Si se produce un error en la base de datos que hospeda el Almacén de administración central, vea [Restaurar el servidor que hospeda el Almacén de administración central](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si el error se produce en un servidor miembro de Enterprise Edition diferente al servidor back-end, vea [Restaurar un servidor miembro de Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Se recomienda realizar una copia de la imagen del sistema antes de iniciar la restauración, de forma que pueda usar esta imagen como punto de reversión en caso de que haya errores durante la restauración. Es posible que desee realizar la copia de la imagen después de instalar el sistema operativo y SQL Server y restaurar o volver a inscribir los certificados.

En este tema, la base de datos principal de ejemplo tendrá el nombre de dominio completo (FQDN) BE1.contoso.com y la base de datos reflejada, BE2.contoso.com.

## Para restaurar una base de datos de servidor back-end Enterprise Edition

1.  Inicie sesión en un servidor front-end desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Fuerce una conmutación por error al reflejo en todas las bases de datos configuradas. Escriba el siguiente cmdlet por cada tipo de base de datos que haya configurado en este servidor:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Por ejemplo:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    > [!WARNING]  
    > Si ha configurado su base de datos back-end para que use la creación de reflejos sincronizados con un testigo, la conmutación por error es automática.
    


4.  Una vez terminada, realice lo siguiente:
    
      - Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.
    
      - Deshabilite la creación de reflejos en el servidor back-end: haga clic con el botón secundario en el grupo en **Grupo de servidores front-end Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General**, en **Asociaciones**, desactive la casilla **Permitir la creación de reflejos del almacén SQL Server**. Lleve esto a cabo para el archivado y supervisión, según sea necesario. Después, haga clic en **Aceptar**.
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **Topología** y, después, en **Publicar**.
    
      - Seleccione el servidor back-end (BE2.contoso.com) todavía en funcionamiento que quiere que sea el nuevo almacén de SQL. Para ello, haga clic con el botón secundario en el grupo en **Grupo de servidores front-end Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General**, en **Asociaciones**, escriba el FQDN del servidor back-end en el campo **Almacén de SQL Server** (BE2.contoso.com en nuestro ejemplo).
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **Topología** y, después, en **Publicar**.
    
      - Reinicie los servicios para que cada servidor pueda leer la nueva topología. Desde un Shell de administración de Lync Server, ejecute los siguientes cmdlets en cada servidor front-end que pertenezca a este grupo:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Desinstale la creación de reflejos. Ejecute el siguiente cmdlet desde un Shell de administración de Lync Server:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por ejemplo:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Lleve esto a cabo para todos los tipos de base de datos de este servidor.

6.  Cree un servidor totalmente nuevo que tenga el mismo FQDN (DB1.contoso.com en este ejemplo) que el equipo con el error, instale el sistema operativo y, luego, restaure o vuelva a inscribir los certificados. Este servidor funcionará como el nuevo reflejo.

7.  Inicie sesión en el nuevo servidor desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins.

8.  Instale SQL Server 2012 o SQL Server 2008 R2. Mantenga los nombres de instancias que se usaron antes del error.

9.  Inicie sesión en un servidor front-end desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins.

10. Use el Generador de topologías para instalar la base de datos reflejada. Haga lo siguiente:
    
      - Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.
    
      - Habilite la creación de reflejos en el servidor back-end: para ello, haga clic con el botón secundario en el grupo en **Grupo de servidores front-end Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General**, en **Asociaciones**, active la casilla **Permitir la creación de reflejos del almacén SQL Server**. Lleve esto a cabo también para el archivado y supervisión, según sea necesario.
        
        Después, escriba el FQDN del nuevo servidor (BE1.contoso.com en este ejemplo) en el campo **Creación de reflejo del almacén de SQL Server**. Haga clic en **Aceptar**.
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **Topología** y, después, en **Instalar base de datos**.
    
      - Siga los pasos del asistente para **Instalar base de datos**. En la página **Crear bases de datos**, seleccione las bases de datos que desea volver a crear.
    
      - Siga los pasos del asistente hasta llegar al mensaje para **crear la base de datos de reflejo**. Seleccione la base de datos que quiera instalar y finalice el proceso.

