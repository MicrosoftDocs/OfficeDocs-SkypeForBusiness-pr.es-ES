---
title: 'Lync Server 2013: configuración de directiva de grupo para Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72493338d854cc0aff63fde5eabb5d7a281fd50e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500717"
---
# <a name="group-policy-settings-for-lync-2013"></a>Configuración de directiva de grupo para Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

En versiones anteriores de Lync y Office Communicator, una plantilla administrativa independiente Communicator. adm estaba disponible para configurar las opciones de directiva de grupo de cliente. Para Lync 2013, los nuevos archivos de plantilla administrativa (archivos. ADMX y. ADML) se incluyen junto con la plantilla administrativa de directiva de grupo de Office. La disponibilidad de los archivos. ADMX y. ADML de 2013 Lync permite descargar plantillas y administrar la configuración de la Directiva de grupo de forma centralizada para todos los programas de Office y los paquetes de idioma. Para obtener más información, consulte "Office 2013 Administrative template files (ADMX, ADML)" en la documentación de Office 2013 en <https://go.microsoft.com/fwlink/p/?linkid=267516> .

<div>

## <a name="client-bootstrapping-policies"></a>Directivas de arranque de cliente

Hay varias directivas de arranque de clientes que deberán configurarse antes de que los usuarios inicien sesión por primera vez en el servidor. Como estas directivas entran en vigor antes de que el cliente inicie sesión y empiece a recibir la configuración de aprovisionamiento dentro de banda del servidor, el usuario puede usar una directiva de grupo para configurarlas. Para obtener más información, consulte [configuración de directivas de arranque de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación sobre implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

