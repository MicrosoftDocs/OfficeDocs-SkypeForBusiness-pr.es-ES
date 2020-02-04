---
title: 'Lync Server 2013: restaurar un servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ecc58dc2683cd07b83a8c57385593961c3e985
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Restaurar un servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Si se produce un error en un servidor Standard Edition que no hospeda el almacén de administración central, siga los procedimientos de esta sección. Si se produce un error en el almacén de administración central, vea [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Para restaurar un servidor Standard Edition

1.  Empiece con un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga los procedimientos de implementación de servidores de su organización para realizar este paso.

    
    </div>

2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo de administradores locales, inicie sesión en el servidor que va a restaurar.

3.  Restaure el almacén de archivos copiando el almacén de archivos adecuado de $Backup a la ubicación del almacén de archivos en el servidor y comparta la carpeta.
    
    <div>
    

    > [!IMPORTANT]  
    > La ruta de acceso y el nombre de archivo del almacén de archivos restaurado deben ser exactamente iguales a los de la copia de seguridad del almacén de archivos para que los componentes que los usan puedan acceder a ellos.

    
    </div>

4.  Ejecute el generador de topología:
    
    1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **sí** para confirmar la selección.

5.  Vaya a la carpeta o los elementos multimedia de instalación de Lync Server y, a continuación, inicie el \\asistente\\para\\la implementación de Lync Server, que se encuentra en Setup AMD64 Setup. exe. Use el Asistente para la implementación de Lync Server para hacer lo siguiente:
    
    1.  Ejecute el **paso 1: instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **paso 2: configurar o quitar los componentes de Lync Server** para instalar los roles de servidor de Lync Server.
    
    3.  Ejecute el **paso 3: solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **paso 4: iniciar servicios** para iniciar servicios en el servidor.
    
    Para obtener más información sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación del rol de servidor que va a restaurar.

6.  Restaure los datos de usuario al realizar lo siguiente:
    
    1.  Copie ExportedUserData. zip desde $Backup\\ a un directorio local.
    
    2.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba:
        
            Stop-CsWindowsService
    
    3.  Para restaurar los datos de usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Reinicie los servicios de Lync escribiendo:
        
            Start-CsWindowsService

7.  Si ha implementado el grupo de respuesta en este servidor Standard Edition, restaure los datos de configuración del grupo de respuesta. Para obtener más información, consulte [restauración de la configuración de grupo de respuesta en Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Si ha implementado una conversación persistente en este servidor Standard Edition, restaure la base de datos de chat persistente (MGC. MDF).
    
    Si usó SQL Server Backup para hacer una copia de seguridad de la base de datos de chat persistente, use procedimientos de restauración de SQL Server para restaurarla.
    
    Si usó el cmdlet Export-CsPersistentChatData para realizar una copia de seguridad, use el cmdlet Import-CsPersistentChatData para restaurarlo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

