---
title: 'Lync Server 2013: topologías para teléfonos IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologías para teléfonos IP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-21_

Esta sección proporciona una descripción general del proceso de conectividad y explica las diferencias entre el modo en que un teléfono IP se conecta en una red interna y externa.

<div>


> [!NOTE]  
> Lync Server proporciona compatibilidad con los siguientes teléfonos IP: el Aastra 6721ip de área común, Aastra teléfono de escritorio 6725ip, teléfono IP HP 4110 (teléfono de área común), teléfono IP HP 4120 (teléfono de escritorio), teléfono IP de escritorio Polycom, teléfono IP de escritorio Polycom CX700, IP Polycom CX500 teléfono de área común y teléfono de conferencia IP Polycom CX3000. De esos teléfonos, todos excepto el Polycom CX700 pueden ejecutar Lync Phone Edition.



</div>

El siguiente diagrama describe todos los componentes implicados en la conectividad de dispositivos dentro del entorno corporativo.

**Topología interna**

![3d88893e-df57-46e3-855A-a1d24589030a] (images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855A-a1d24589030a")

<div>


> [!NOTE]  
> La figura anterior es una representación lógica, no una visión general física. Por ejemplo, los servicios de dominio de Active Directory (AD DS) rara vez se encuentran en el mismo equipo que cualquier componente de Lync Server. El almacén de usuario puede encontrarse en el servidor back-end o en los servidores de archivado y supervisión. El shell de administración de Lync Server, el servidor Web y los servicios de actualización forman parte de la función de servidor front-end.



</div>

En el siguiente diagrama se ofrece información general sobre los componentes que se utilizan cuando el dispositivo se encuentra fuera de la red corporativa.

**Topología externa**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3] (images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> El servicio Web de actualización de dispositivos proporciona un sitio web externo e interno, pero solo se muestra el externo.<BR>La ubicación del registrador y la dirección URL del servicio Web de actualización de dispositivos para la organización se deben publicar en DNS si se va a habilitar el acceso externo. Además, el servidor perimetral debe implementarse y configurarse correctamente para permitir las comunicaciones externas desde el dispositivo al entorno corporativo y viceversa. Esto se omite del diagrama anterior porque la implementación perimetral no es específica de la Conectividad del dispositivo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

