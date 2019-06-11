---
title: 'Lync Server 2013: configuración de directiva de grupo para Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e075af74fd081e49daad0768a33c9769e8a633bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Configuración de directiva de grupo para Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

En versiones anteriores de Lync y Office Communicator, una plantilla administrativa independiente de Communicator. adm estaba disponible para configurar las opciones de directiva de grupo de cliente. Para Lync 2013, se incluyen nuevos archivos de plantilla administrativa (archivos. ADMX y. ADML) junto con la plantilla administrativa de la Directiva de grupo de Office. La disponibilidad de los archivos. ADMX y. ADML de 2013 Lync permite descargar plantillas y administrar de forma centralizada la configuración de la Directiva de grupo para todos los paquetes de idioma y programas de Office. Para obtener más información, consulte "archivos de plantilla administrativa (ADMX, ADML) de Office 2013" en la <http://go.microsoft.com/fwlink/p/?linkid=267516>documentación de Office 2013 en.

<div>

## <a name="client-bootstrapping-policies"></a>Directivas de inicio del cliente

Hay varias directivas de inicio del cliente que debe configurar antes de que los usuarios inicien sesión en el servidor por primera vez. Debido a que estas directivas surten efecto antes de que el cliente inicie sesión y empiece a recibir la configuración de aprovisionamiento en banda del servidor, puede usar la Directiva de grupo para configurarlas. Para obtener más información, vea [configuración de directivas de inicio de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación de implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

