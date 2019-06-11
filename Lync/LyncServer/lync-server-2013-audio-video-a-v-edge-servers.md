---
title: 'Lync Server 2013: servidores perimetrales de audio/vídeo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V proporciona a los usuarios internos (los usuarios que han iniciado sesión en la red de la organización) una forma de compartir audio y vídeo con usuarios externos (usuarios que no han iniciado sesión en la red de su organización). Además de audio y vídeo, el servicio perimetral A/V también proporciona soporte técnico para el uso compartido del escritorio y la transferencia de archivos.

El servicio perimetral A/V se administra principalmente mediante la configuración A/V Edge; Esta configuración le permite administrar la cantidad máxima de ancho de banda que se va a asignar por puerto y por usuario, y especificar la cantidad de tiempo que se puede usar un token de autenticación antes de que se renueve ese token. La configuración del borde a/V puede aplicarse a sitios o a servidores perimetrales individuales a/V. Cuando determine qué colección de configuraciones tendrá prioridad, use la siguiente guía:

  - La configuración establecida en el ámbito del servicio (es decir, en un servidor individual) tiene prioridad sobre todo.

  - La configuración establecida en el ámbito del sitio tiene prioridad sobre la configuración establecida en el ámbito global. Sin embargo, la configuración del ámbito del servicio también reemplaza la configuración del ámbito del sitio.

  - La configuración del ámbito global se usará solo si no hay ninguna configuración de servicio establecida en el servidor individual y no hay configuración de sitio para el sitio en el que se encuentra el servidor.

El servicio perimetral de A/V solo se puede administrar con Lync Server PowerShell y los cmdlets CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Devolver información de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Crear o modificar una colección de valores de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Eliminar una colección existente de valores de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

