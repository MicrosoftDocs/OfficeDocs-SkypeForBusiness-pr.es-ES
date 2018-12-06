---
title: Restaurar el servidor que hospeda el Almacén de administración central
TOCTitle: Restaurar el servidor que hospeda el Almacén de administración central
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202172(v=OCS.15)
ms:contentKeyID: 52061648
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar el servidor que hospeda el Almacén de administración central

 

_**Última modificación del tema:** 2013-02-21_

Una implementación de Lync Server tiene un solo Almacén de administración central, del que se replica una copia en cada servidor que ejecuta un rol de servidor Lync Server. Este tema describe cómo restaurar un servidor back‑end o Servidor Standard Edition que hospeda el Almacén de administración central.

Para encontrar el grupo en el que se ubica el Servidor de administración central, abra Generador de topologías, haga clic en **Lync Server** y busque en el panel derecho, en **Servidor de administración central**.

Si el servidor back-end que hospeda el Almacén de administración central se encuentra en una configuración reflejada y la base de datos reflejada aún funciona, se recomienda realizar una copia de seguridad de este reflejo que aún se encuentra en funcionamiento y, a continuación, llevar a cabo una restauración completa tanto en la base de datos principal como en la reflejada mediante el proceso de restauración que se detalla más abajo. Esto es necesario porque la restauración del servidor back-end requiere la modificación y publicación de la topología, lo que solo puede llevarse a cabo si la base de datos que hospeda el CMS es operativa. También tenga en cuenta que los roles de las bases de datos principal y reflejada no se pueden intercambiar si la topología no se puede publicar.


> [!NOTE]
> Si se produjo un error en el servidor back-end o en un Servidor Standard Edition que no hospeda el Almacén de administración central, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restaurar un servidor back-end Enterprise Edition</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition</A>. Si un servidor back-end que hospeda el Almacén de administración central se encuentra en una configuración reflejada y solo se produjo un error en el reflejo, consulte <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurar un servidor back-end Enterprise Edition reflejado: reflejar</A>. Si se produjo un error en cualquier otro servidor, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurar un servidor miembro de Enterprise Edition</A>.



> [!TIP]  
> Se recomienda que realice una copia de la imagen del sistema antes de iniciar la restauración. Puede usar esta imagen como punto de reversión en caso de que haya errores durante la restauración. Le resultará conveniente realizar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



## Para restaurar el almacén de administración central

1.  Comience con un servidor vacío o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que causó el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    

    > [!NOTE]
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.



2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo de administradores locales, inicie sesión en el servidor que está restaurando.

3.  Si está restaurando una Servidor Standard Edition, restaure el Almacén de archivos copiando el Almacén de archivos correspondiente de $Backup en la ubicación de Almacén de archivos en el servidor y, a continuación, comparta la carpeta.
    
    > [!IMPORTANT]  
    > La ruta de acceso y nombre de archivo del Almacén de archivos restaurado deben ser exactamente iguales a los del Almacén de archivos del que se ha hecho la copia de seguridad. De este modo, los componentes que usan los archivos podrán acceder a ellos.
    


4.  Siga uno de estos procedimientos:
    
      - Si está instalando un Servidor Standard Edition, busque el medio o la carpeta de instalación de Lync Server e inicie el Asistente para la implementación de Lync Server ubicado en \\setup\\amd64\\Setup.exe. En el Asistente para la implementación, haga clic en **Preparar el primer servidor Standard Edition** y siga los pasos para instalar el Almacén de administración central.
    
      - Si está instalando un servidor back-end Enterprise, instale SQL Server 2012 o SQL Server 2008 R2. Mantenga los mismos nombres de instancia que se usaron antes del error.
        

        > [!NOTE]
        > En función del servidor que esté restaurando y de su implementación, el servidor puede incluir varias bases de datos independientes o combinadas. Para instalar SQL Server, siga el mismo procedimiento que usó originalmente para implementar el servidor, incluidos los inicios de sesión y los permisos de SQL Server.



5.  Desde un servidor front-end, Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

6.  Vuelva a crear el Almacén de administración central. En la línea de comandos, escriba:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por ejemplo:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Defina el punto de control de Servicios de dominio de Active Directory para el Almacén de administración central. En la línea de comandos, escriba:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por ejemplo:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    

    > [!NOTE]
    > Si pierde el punto de conexión, puede volver a ejecutar este cmdlet.



8.  Importe los datos de Almacén de administración central de $Backup. En la línea de comandos, escriba:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Por ejemplo:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Habilite los cambios que acaba de realizar. En la línea de comandos, escriba:
    
        Enable-CsTopology
    

    > [!NOTE]
    > Una vez habilitada la topología, podrá encontrar el documento de topología en la base de datos.



10. Si está restaurando un Servidor back-end de Enterprise Edition que también hospedaba el CMS, o si necesita volver a crear un reflejo del CMS, siga este paso. De lo contrario, salte al paso 11.
    
    Haga lo siguiente para instalar las bases de datos independientes:
    
    1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.
    
    4.  Haga clic con el botón secundario en el nodo **Lync Server 2013** y, a continuación, haga clic en **Instalar base de datos**.
    
    5.  Siga el asistente **Instalar base de datos**. Si está restaurando una base de datos que no es el Almacén de administración central de este servidor, en la página **Crear bases de datos**, seleccione las bases de datos que quiere volver a crear.
        

        > [!NOTE]
        > En la página <STRONG>Crear bases de datos</STRONG> solo se muestran bases de datos independientes. Las bases de datos combinadas se crean cuando ejecuta el Asistente para la implementación de Lync Server.

    
    6.  Si está restaurando un servidor back-end reflejado, siga los pasos restantes del asistente hasta que aparezca el diálogo Crear base de datos reflejada. Seleccione la base de datos que desea instalar y complete el proceso.
    
    7.  Siga los pasos restantes del asistente y, a continuación, haga clic en **Finalizar**.
    
    > [!TIP]  
    > En lugar de ejecutar Generador de topologías, puede usar el cmdlet <strong>Install-CsDatabase</strong> para crear cada una de las bases de datos y el cmdlet <strong>Install-CsMirrorDatabase</strong> para configurar la creación de reflejo. Para obtener detalles, consulte <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</a>.
    


11. Si está restaurando un Servidor Standard Edition, vaya al medio o la carpeta de instalación de Lync Server e inicie el Asistente para la implementación de Lync Server ubicado en \\setup\\amd64\\Setup.exe. Use el Asistente para la implementación de Lync Server para hacer lo siguiente:
    
    1.  Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **Paso 2: Instalar o desinstalar componentes de Lync Server** para instalar los roles de servidor de Lync Server.
    
    3.  Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.
    
    Para obtener información detallada sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación correspondiente al rol de servidor que esté restaurando.

12. Para restaurar los datos del usuario, siga el siguiente procedimiento:
    
    1.  Copie ExportedUserData.zip desde $Backup\\ a un directorio local.
    
    2.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba lo siguiente:
        
            Stop-CsWindowsService
    
    3.  Para restaurar los datos del usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Escriba lo siguiente para reiniciar los servicios de Lync:
        
            Start-CsWindowsService

13. Restaure los datos de información de ubicación en el Almacén de administración central. En la línea de comandos, escriba:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Por ejemplo:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Si implementó Grupo de respuesta en este grupo de servidores o Servidor Standard Edition, restaure los datos de configuración de Grupo de respuesta. Para obtener más información, consulte [Restaurar la configuración de grupos de respuesta](lync-server-2013-restoring-response-group-settings.md).

15. Si está restaurando un servidor back-end que incluye bases de datos de supervisión o archivado, restaure los datos de supervisión o archivado usando una herramienta de administración de SQL Server, como SQL Server Management Studio. Para obtener detalles, consulte [Restaurar, supervisar o archivar datos](lync-server-2013-restoring-monitoring-or-archiving-data.md).

