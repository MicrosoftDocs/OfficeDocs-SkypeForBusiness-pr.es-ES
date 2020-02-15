---
title: Actualizar o actualizar un servidor back-end o un servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213a945d27c2c5d0ee2135fd0d96bbe1c29c1971
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42015363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Actualizar o actualizar un servidor back-end o un servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En este tema se explica cómo instalar una actualización en un servidor back-end de Enterprise Edition o un servidor Standard Edition.

Si un servidor back-end está inactivo al menos 30 minutos mientras se actualiza, los usuarios podrían entrar en modo de resistencia. Cuando termine la actualización y los servidores back-end se conecten de nuevo a los servidores front-end del grupo, los usuarios volverán al modo de funcionalidad total. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o un servidor Standard Edition

1.  Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.

2.  Descargue la actualización extráigala en el disco duro local.

3.  Inicie el Shell de administración de Lync Server: Haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, a continuación, en **Shell de administración de Lync Server**.

4.  Detenga los servicios de Lync Server. En la línea de comandos, escriba:
    
        Stop-CsWindowsService

5.  Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
        net stop w3svc

6.  Cierre todas las ventanas de el Shell de administración de Lync Server.

7.  Instale la actualización.

8.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

9.  Vuelva a detener los servicios de Lync Server para capturar ensamblados -d de la caché global de ensamblados (GAC). En la línea de comandos, escriba:
    
        Stop-CsWindowsService

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
        net start w3svc

11. Aplique los cambios realizados por LyncServerUpdateInstaller.exe a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:
    
      - Si este es un servidor back-end de Enterprise Edition y no hay bases de datos combinadas en este servidor, como las bases de datos de archivado o supervisión, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Si este es un servidor back-end Enterprise Edition y hay bases de datos combinadas en este servidor, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Si se trata de un servidor Standard Edition, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

