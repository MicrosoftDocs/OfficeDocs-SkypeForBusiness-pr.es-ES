---
title: 'Lync Server 2013: Reducir la mensajería instantánea no solicitada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Reducir la mensajería instantánea no solicitada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

La aplicación inteligente de filtro de mensajes instantáneos ayuda a proteger la implementación de Microsoft Lync Server 2013 contra los virus más comunes con una degradación mínima para la experiencia del usuario. El filtro inteligente de mensajes instantáneos proporciona lo siguiente:

  - Filtrado de URL mejorado

  - Filtrado mejorado de transferencia de archivos

Use el filtro inteligente de mi para configurar filtros para bloquear mensajes instantáneos no solicitados o potencialmente dañinos de puntos de conexión desconocidos fuera del firewall de la empresa. Para configurar filtros, especifique los criterios que se van a usar para determinar qué se debe bloquear, por ejemplo, los mensajes instantáneos que contengan hipervínculos y archivos con extensiones específicas.

Antes de implementar la aplicación inteligente de filtro de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado cuando los mensajes se enrutan desde un servidor de Lync Server 2013 a otro. La manera en que se aplican estas opciones de filtrado es coherente, independientemente de si los servidores se encuentran en una sola organización o en los límites de la organización. Esta coherencia se aplica a la forma en que el aviso personalizado y los mensajes de advertencia se insertan en mensajes y se envían por servidores.

La opción de filtrado recomendada es permitir la mensajería instantánea con hipervínculos pero requerir el filtro inteligente de mensajes instantáneos para deshabilitar el vínculo al insertar un carácter de subrayado. Si elige esta opción, tendrá la opción adicional de redactar un aviso para los usuarios que aparece al principio de cada mensaje instantáneo que contiene un hipervínculo.

Una segunda opción de filtrado es permitir los mensajes instantáneos con hipervínculos no modificados. Si elige esta opción, tiene la opción adicional (recomendado) de redactar una advertencia para los usuarios que se insertan en cada mensaje.

Una tercera opción es bloquear todos los mensajes instantáneos que contienen hipervínculos. Si elige esta opción, el servidor envía una advertencia al usuario. Debes escribir esta advertencia.

</div>

<span> </span>

</div>

</div>

</div>

