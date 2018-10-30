---
title: 'Restaurar un servidor back-end Enterprise Edition reflejado: reflejar'
TOCTitle: 'Restaurar un servidor back-end Enterprise Edition reflejado: reflejar'
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945626(v=OCS.15)
ms:contentKeyID: 52061681
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar un servidor back-end Enterprise Edition reflejado: reflejar

 

_**Última modificación del tema:** 2013-02-19_

Si tiene un servidor back-end Enterprise Edition en una configuración reflejada y se produce un error solo en el reflejo, siga los procedimientos de esta sección. Si se produce un error tanto en la base de datos principal como en la reflejada, consulte [Restaurar un servidor back-end Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si se produce un error solo en la base de datos principal, consulte [Restaurar un servidor back-end Enterprise Edition reflejado: principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Si se produce un error en la base de datos que hospeda el Almacén de administración central, consulte [Restaurar el servidor que hospeda el Almacén de administración central](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor Enterprise Edition que no es el servidor back-end, consulte [Restaurar un servidor miembro de Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Se recomienda que realice una copia de la imagen del sistema antes de iniciar la restauración. Puede usar esta imagen como punto de reversión en caso de que haya errores durante la restauración. Le resultará conveniente realizar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.

## Para restaurar una base de datos reflejada del servidor back-end Enterprise Edition

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Desinstale la creación de reflejo. Primero, escriba el siguiente cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por ejemplo:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Haga esto para todos los tipos de base de datos de este servidor.

4.  Cree un servidor vacío o nuevo que tenga el mismo nombre de dominio completo (FQDN) (DB1.contoso.com) que el equipo que causó el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados. Este servidor funcionará como el nuevo reflejo.

5.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor nuevo.

6.  Instale SQL Server 2012 o SQL Server 2008 R2. Mantenga los mismos nombres de instancia que se usaron antes del error.

7.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

8.  Use el Generador de topologías para instalar la base de datos reflejada. Realice el siguiente procedimiento:
    
      - Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.
    
      - Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **Topología** y, a continuación, haga clic en **Instalar base de datos**.
    
      - Siga los pasos del asistente **Instalar base de datos**. En la página **Crear bases de datos**, seleccione las bases de datos que desea volver a crear.
    
      - Siga los pasos del asistente hasta que aparezca el diálogo **Crear base de datos reflejada**. Seleccione la base de datos que desea instalar y complete este proceso.
        
        > [!TIP]  
        > En lugar de ejecutar el Generador de topologías, puede usar el cmdlet <strong>Install-CsMirrorDatabase</strong> para configurar la creación de reflejo. Para obtener información detallada, vea la documentación sobre el Shell de administración de Lync Server.
        

