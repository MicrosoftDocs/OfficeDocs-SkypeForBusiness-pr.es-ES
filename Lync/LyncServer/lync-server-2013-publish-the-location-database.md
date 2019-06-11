---
title: 'Lync Server 2013: publicar la base de datos de ubicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afc13a67ccdad3d27328107e095f1bffa66fdcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Publicar la base de datos de ubicación desde Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente hasta que no se publiquen.

Para obtener más información, consulte la documentación del shell de administración de Lync Server para el siguiente cmdlet:

  - **Publish-CsLisConfiguration**

Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC). Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN. Póngase en contacto con el proveedor de RTC para obtener más información al respecto. Puede exportar los registros de la base de datos de servicios de información de ubicación y darles formato según sea necesario.

<div>

## <a name="to-publish-the-location-database"></a>Para publicar la base de datos de ubicaciones

  - Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

  - Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

