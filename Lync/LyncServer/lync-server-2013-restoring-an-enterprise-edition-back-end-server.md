---
title: Restaurar un servidor back-end Enterprise Edition
TOCTitle: Restaurar un servidor back-end Enterprise Edition
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202163(v=OCS.15)
ms:contentKeyID: 52061595
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar un servidor back-end Enterprise Edition

 

_**Última modificación del tema:** 2013-02-18_

Use el procedimiento descrito en este tema en los dos casos siguientes:

  - Se produce un error tanto en la base de datos principal como en la base de datos reflejada de un servidor back-end Enterprise Edition reflejado.

  - Se produce un error en un servidor back-end Enterprise Edition que no está reflejado.

Si tiene un servidor back-end Enterprise Edition reflejado y se produce un error solo en la base de datos principal o en la base de datos reflejada, consulte [Restaurar un servidor back-end Enterprise Edition reflejado: principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar la base de datos principal o [Restaurar un servidor back-end Enterprise Edition reflejado: reflejar](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar la base de datos reflejada.

Si se produce un error en el Almacén de administración central, consulte [Restaurar el servidor que hospeda el Almacén de administración central](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor Enterprise Edition que no es el servidor back-end, consulte [Restaurar un servidor miembro de Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

> [!TIP]  
> Se recomienda que realice una copia de la imagen del sistema antes de iniciar la restauración. Puede usar esta imagen como punto de reversión en caso de que haya errores durante la restauración. Le resultará conveniente realizar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



## Para restaurar un servidor back-end Enterprise Edition

1.  Comience con un servidor vacío o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que causó el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    

    > [!NOTE]
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.



2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que está restaurando.

3.  Instale SQL Server 2012 o SQL Server 2008 R2. Mantenga los mismos nombres de instancia que se usaron antes del error.
    

    > [!NOTE]
    > Según la implementación, el servidor back-end puede incluir varias bases de datos combinadas o independientes. Para instalar el servidor SQL Server, siga el mismo procedimiento que usó originalmente para implementar el servidor, incluidos los permisos e inicios de sesión de SQL Server.



4.  Tras instalar SQL Server, haga lo siguiente:
    
    1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.
    
    4.  Haga clic con el botón secundario en el nodo **Lync Server 2013** y, a continuación, haga clic en **Publicar topología**.
    
    5.  Siga los pasos del asistente para **Publicar la topología**. En la página **Crear bases de datos**, seleccione las bases de datos que desea volver a crear.
        

        > [!NOTE]
        > Solo se muestran las bases de datos independientes en la página <STRONG>Crear bases de datos</STRONG>.

    
    6.  Si está restaurando un servidor back-end reflejado, siga los pasos restantes del asistente hasta que aparezca el diálogo **Crear base de datos reflejada**. Seleccione la base de datos que desea instalar y complete el proceso.
    
    7.  Siga los pasos restantes del asistente y, a continuación, haga clic en **Finalizar**.
    
    > [!TIP]  
    > En lugar de ejecutar Generador de topologías, puede usar el cmdlet <strong>Install-CsDatabase</strong> para crear cada una de las bases de datos y el cmdlet <strong>Install-CsMirrorDatabase</strong> para configurar la creación de reflejo. Para obtener información detallada, vea la documentación sobre el Shell de administración de Lync Server.
    


5.  Para restaurar los datos del usuario, lleve a cabo el siguiente procedimiento:
    
    1.  Copie ExportedUserData.zip desde $Backup\\ a un directorio local.
    
    2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.
    
    3.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba lo siguiente:
        
            Stop-CsWindowsService
    
    4.  Para restaurar los datos del usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Escriba lo siguiente para reiniciar los servicios de Lync:
        
            Start-CsWindowsService

6.  Si implementó el Grupo de respuesta en este grupo de servidores, restaure los datos de configuración del Grupo de respuesta. Para obtener más información, consulte [Restaurar la configuración de grupos de respuesta](lync-server-2013-restoring-response-group-settings.md).

7.  Si desea restaurar un servidor back-end que incluye bases de datos de archivado o supervisión, restaure los datos de archivado o supervisión con una herramienta de SQL Server, como SQL Server Management Studio. Para obtener más información, consulte [Restaurar, supervisar o archivar datos](lync-server-2013-restoring-monitoring-or-archiving-data.md).

