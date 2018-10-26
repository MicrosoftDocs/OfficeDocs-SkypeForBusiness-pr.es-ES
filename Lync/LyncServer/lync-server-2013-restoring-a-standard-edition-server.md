---
title: Restaurar un servidor Standard Edition
TOCTitle: Restaurar un servidor Standard Edition
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202190(v=OCS.15)
ms:contentKeyID: 52061765
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar un servidor Standard Edition

 

_**Última modificación del tema:** 2013-02-21_

Si se produce un error en un servidor Standard Edition que no hospeda el Almacén de administración central, siga los procedimientos de esta sección. Si se produce un error en Almacén de administración central, consulte [Restaurar el servidor que hospeda el Almacén de administración central](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

> [!TIP]  
> Se recomienda realizar una copia de la imagen del sistema antes de iniciar la restauración, de forma que pueda usar esta imagen como punto de reversión en caso de que haya errores durante la restauración. Es posible que desee realizar la copia de la imagen después de instalar el sistema operativo y SQL Server y restaurar o volver a inscribir los certificados.



## Para restaurar un servidor Standard Edition

1.  Comience con un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que causó el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    

    > [!NOTE]
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.



2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo Administradores local, inicie sesión en el servidor que está restaurando.

3.  Restaure Almacén de archivos copiando el Almacén de archivos correspondiente de $Backup en la ubicación del Almacén de archivos en el servidor y comparta la carpeta.
    
    > [!IMPORTANT]  
    > La ruta de acceso y nombre de archivo del Almacén de archivos restaurado deben ser exactamente iguales a los del Almacén de archivos del que se ha hecho la copia de seguridad. De este modo, los componentes que usan los archivos podrán acceder a ellos.
    


4.  Ejecute Generador de topologías:
    
    1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente** y, a continuación, haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.

5.  Vaya a la carpeta o medios de instalación de Lync Server e inicie el Asistente para la implementación de Lync Server, que está en \\setup\\amd64\\Setup.exe. Siga el Asistente para la implementación de Lync Server para hacer lo siguiente:
    
    1.  Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **Paso 2: Instalar o desinstalar componentes de Lync Server** para instalar los roles de servidor de Lync Server.
    
    3.  Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.
    
    Para obtener información detallada sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación correspondiente al rol de servidor que esté restaurando.

6.  Para restaurar los datos del usuario, haga lo siguiente:
    
    1.  Copie ExportedUserData.zip desde $Backup\\ a un directorio local.
    
    2.  Para poder restaurar los datos del usuario, debe detener los servicios de Lync. Para ello, escriba lo siguiente:
        
            Stop-CsWindowsService
    
    3.  Para restaurar los datos del usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Escriba lo siguiente para reiniciar el servicio de Lync:
        
            Start-CsWindowsService

7.  Si implementó Grupo de respuesta en este Servidor Standard Edition, restaure los datos de configuración de Grupo de respuesta. Para obtener información detallada, consulte [Restaurar la configuración de grupos de respuesta](lync-server-2013-restoring-response-group-settings.md).

8.  Si ha implementado el chat persistente en este servidor Standard Edition, restaure la base de datos de chat persistente (mgc.mdf).
    
    En caso de que haya usado la copia de seguridad de SQL Server para hacer la copia de seguridad de la base de datos de chat persistente, use los procedimientos de restauración de SQL Server correspondientes para restaurarla.
    
    Si ha usado el cmdlet Export-CsPersistentChatData para hacer la copia de seguridad, use el cmdlet Import-CsPersistentChatData para restaurarla.

