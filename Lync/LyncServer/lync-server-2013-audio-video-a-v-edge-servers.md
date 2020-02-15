---
title: 'Lync Server 2013: servidores perimetrales de audio y vídeo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1262ee1a2db12569538f499731de53a9da133c98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V permite que los usuarios internos (usuarios conectados a la red de la organización) compartan audio y vídeo con usuarios externos (usuarios no conectados a la red de la organización). Además de audio y vídeo, el servicio perimetral A/V permite compartir el escritorio y transferir archivos, entre otras tareas.

El servicio perimetral A/V se administra principalmente con la configuración del servidor perimetral A/V. Estas opciones permiten administrar la cantidad máxima de ancho de banda que se asignará por puerto y por usuario, y especificar el tiempo durante el que se puede usar un token de autenticación antes de que se deba renovar. Las opciones de configuración del servidor perimetral A/V se pueden aplicar a sitios o a servidores perimetrales A/V individuales. Cuando determine qué colección de opciones tendrá prioridad, use la siguiente guía:

  - 
Las opciones configuradas en el ámbito de servicio (es decir, en un servidor individual) tienen prioridad sobre todo lo demás.

  - 
Las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones configuradas en el ámbito global. Pero las opciones del ámbito de servicio tienen prioridad sobre las opciones del ámbito de sitio.

  - 
Las opciones configuradas en el ámbito global se usarán solo si no hay opciones de servicio configuradas en el servidor individual y si no hay opciones de sitio configuradas para el sitio en el que se encuentra el servidor.

El servicio perimetral A/V solo se puede administrar con Lync Server PowerShell y los cmdlets CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Devolver información de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

