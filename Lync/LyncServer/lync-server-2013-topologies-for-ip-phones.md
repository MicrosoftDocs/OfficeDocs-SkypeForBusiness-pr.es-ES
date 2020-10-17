---
title: 'Lync Server 2013: topologías para teléfonos IP'
description: 'Lync Server 2013: topologías para teléfonos IP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a151a83a69e1f7e14dcbed8d8ab1038157fa839
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549136"
---
# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologías para teléfonos IP en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-21_

En este tema, se describe el proceso de conectividad y se explican las diferencias de la conexión de un teléfono IP en una red interna y en una red externa.

<div>


> [!NOTE]  
> Lync Server proporciona compatibilidad con los siguientes teléfonos IP: el Aastra 6721ip Common Area Phone, Aastra 6725ip teléfono de escritorio, HP 4110 IP Phone (teléfono de área común), HP 4120 IP Phone (teléfono de escritorio), teléfono de escritorio Polycom CX600 IP, teléfono de escritorio Polycom CX700, teléfono de área común Polycom CX500 y teléfono de conferencia Polycom CX3000 IP. De esos teléfonos, todos excepto Polycom CX700 pueden ejecutar Lync Phone Edition.



</div>

En el diagrama siguiente, se describen todos los componentes utilizados en la conectividad del dispositivo dentro del entorno corporativo.

**Topología interna**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> La figura anterior constituye una representación lógica, no una descripción física. Por ejemplo, los servicios de dominio de Active Directory (AD DS) rara vez se ubican en el mismo equipo que los componentes de Lync Server. El almacén de usuarios puede estar en el servidor back-end, o en los servidores de archivado o de supervisión. El shell de administración de Lync Server, el servidor Web y los servicios de actualización forman parte del rol de servidor front-end.



</div>

En el diagrama siguiente, se muestran los componentes utilizados cuando el dispositivo se encuentra fuera de la red corporativa.

**Topología externa**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> El servicio web de actualización de dispositivos proporciona un sitio web externo e interno, pero aquí solo se muestra uno externo.<BR>La ubicación del registrador y la dirección URL del servicio web de actualización de dispositivos para la organización deben publicarse en DNS si se habilitará el acceso externo. Además, el servidor perimetral se debe implementar y configurar correctamente para permitir las comunicaciones externas del dispositivo al entorno corporativo, y viceversa. Esto se omite en el diagrama anterior porque la implementación perimetral no es específica de la conectividad del dispositivo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

