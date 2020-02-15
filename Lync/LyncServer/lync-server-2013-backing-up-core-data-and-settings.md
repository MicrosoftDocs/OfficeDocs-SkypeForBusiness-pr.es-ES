---
title: 'Lync Server 2013: copia de seguridad de los datos y la configuración principales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a6614a06ea4e5370dd944940d35a690853c171b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Copia de seguridad de los datos y la configuración principales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-23_

Los siguientes procedimientos usan los cmdlets del shell de administración de Lync Server para crear archivos de copia de seguridad para la configuración y los datos de los servicios principales. Para obtener más información acerca de las herramientas usadas en esta sección, incluidos dónde se encuentran, consulte [requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Para obtener más información sobre cómo realizar copias de seguridad de los datos de archivado y supervisión, vea [realizar copias de seguridad de bases de datos de archivado y supervisión en Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> El paso de esta sección para crear una copia de seguridad del almacén de administración central incluye la configuración y la configuración de archivado y supervisión.



</div>

Puede ejecutar los cmdlets descritos en esta sección de manera local o remota.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Para crear copias de seguridad de datos y configuración principales

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en cualquier equipo de la implementación interna.

2.  Para almacenar las copias de seguridad creadas en los pasos siguientes, cree una nueva carpeta compartida y actualice la ruta de acceso a la que hace referencia **$Backup** con la nueva carpeta compartida.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

4.  Realice una copia de seguridad del archivo de configuración del almacén de administración central. Escriba lo siguiente en la línea de comandos:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Por ejemplo:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Este paso exporta la topología, las directivas y las opciones de configuración de Lync Server a un archivo. No es necesario realizar ningún otro paso para crear una copia de seguridad de los datos de la topología.

    
    </div>

5.  Copie el archivo de configuración de la copia de seguridad del almacén de\\Administración Central en $backup.

6.  Cree una copia de seguridad de los datos del servicio de información de ubicaciones. En la línea de comandos, escriba lo siguiente:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Por ejemplo:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copie el archivo de configuración del servicio de información de ubicación con copia\\de seguridad en $backup.

8.  Realice una copia de seguridad de los datos de usuario en cada base de datos back-end de un grupo de servidores front-end y cada servidor Standard Edition. Escriba lo siguiente en la línea de comandos:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Por ejemplo:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copie el archivo de usuario de copia de seguridad\\en $backup.

10. En cada grupo que ejecuta la aplicación de grupo de respuesta, realice una copia de seguridad de la configuración del grupo de respuesta. Haga lo siguiente:
    
    1.  En la línea de comandos, escriba lo siguiente:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Por ejemplo:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copie el archivo de configuración del grupo de respuesta de la\\copia de seguridad en $backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

