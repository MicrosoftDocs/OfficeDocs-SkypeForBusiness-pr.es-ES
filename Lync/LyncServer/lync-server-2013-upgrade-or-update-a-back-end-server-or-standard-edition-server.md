---
title: Actualizar o actualizar un servidor de servicios de fondo o un servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Actualizar o actualizar un servidor de servicios de fondo o un servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En este tema se explica cómo instalar una actualización en un servidor de servicios de fondo Enterprise Edition o en un servidor Standard Edition.

Si un servidor back-end está desactivado durante al menos 30 minutos mientras lo está actualizando, los usuarios pueden entrar en el modo de resistencia. Cuando la actualización se ha completado y los servidores back-end se han conectado de nuevo con los servidores front-end en el grupo, los usuarios se devuelven a la funcionalidad completa. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o un servidor Standard Edition

1.  Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.

2.  Descargue la actualización extráigala en el disco duro local.

3.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

4.  Detenga los servicios de Lync Server. En la línea de comandos, escriba:
    
        Stop-CsWindowsService

5.  Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
        net stop w3svc

6.  Cierre todas las ventanas del shell de administración de Lync Server.

7.  Instale la actualización.

8.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

9.  Detenga de nuevo los servicios de Lync Server para capturar los ensamblados de caché global de ensamblados (GAC): d. En la línea de comandos, escriba:
    
        Stop-CsWindowsService

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
        net start w3svc

11. Aplique los cambios realizados por LyncServerUpdateInstaller. exe a las bases de datos de SQL Server de una de las siguientes maneras:
    
      - Si se trata de un servidor de servicios de fondo Enterprise Edition y no hay bases de datos colocadas en este servidor, como archivar o supervisar bases de datos, escriba lo siguiente en una línea de comandos:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Si se trata de un servidor de servicios de fondo Enterprise Edition y hay bases de datos colocadas en este servidor, escriba lo siguiente en una línea de comandos:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Si se trata de un servidor Standard Edition, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

