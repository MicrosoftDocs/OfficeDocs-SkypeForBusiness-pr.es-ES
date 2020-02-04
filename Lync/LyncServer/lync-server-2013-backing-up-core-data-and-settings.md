---
title: 'Lync Server 2013: realizar una copia de seguridad de los datos y la configuración básicos'
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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Realizar copias de seguridad de los datos y la configuración básicos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-23_

Los procedimientos siguientes usan los cmdlets del shell de administración de Lync Server para crear archivos de copia de seguridad para la configuración y los datos de los servicios básicos. Para obtener más información sobre las herramientas usadas en esta sección, incluyendo dónde se encuentran, consulte [requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Para más información sobre cómo realizar copias de seguridad del archivado y la supervisión de datos, vea [realizar copias de seguridad del archivado y la supervisión de bases de datos en Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> El paso de esta sección para realizar una copia de seguridad del almacén de administración central incluye la configuración y la configuración para archivar y supervisar.



</div>

Puede ejecutar los cmdlets descritos en esta sección de forma local o remota.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Para hacer una copia de seguridad de los datos y la configuración básicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en cualquier equipo de su implementación interna.

2.  Para almacenar las copias de seguridad que cree en los pasos siguientes, cree una nueva carpeta compartida y actualice la ruta de acceso a la que hace referencia **$backup** a la nueva carpeta compartida.

3.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

4.  Haga una copia de seguridad del archivo de configuración del almacén central de administración. En la línea de comandos, escriba:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Por ejemplo:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Este paso exporta la topología, las directivas y los parámetros de configuración de Lync Server a un archivo. No es necesario ningún otro paso para hacer una copia de seguridad de los datos de la topología.

    
    </div>

5.  Copie el archivo de configuración del almacén de administración central de la copia\\de seguridad en $backup.

6.  Haga una copia de seguridad de los datos del servicio de información. En la línea de comandos, escriba:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Por ejemplo:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copie el archivo de configuración del servicio de información de ubicación con copia\\de seguridad en $backup.

8.  Haga una copia de seguridad de los datos de usuario en todas las bases de datos back-end de un grupo de servidores front-end y de cada servidor Standard Edition. En la línea de comandos, escriba:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Por ejemplo:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copie el archivo de usuario de copia de seguridad\\en $backup.

10. En todos los grupos que ejecutan la aplicación de grupo de respuesta, realice una copia de seguridad de la configuración del grupo de respuesta. Siga este procedimiento:
    
    1.  En la línea de comandos, escriba lo siguiente:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Por ejemplo:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copie el archivo de configuración del grupo de respuesta de copia\\de seguridad en $backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

