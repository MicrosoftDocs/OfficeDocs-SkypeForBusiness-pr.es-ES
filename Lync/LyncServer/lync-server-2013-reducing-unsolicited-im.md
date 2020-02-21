---
title: 'Lync Server 2013: reducir la mensajería instantánea no solicitada'
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
ms.openlocfilehash: 233c29df440fcd1596e1484fa6f81dd5932d16bd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Reducir la mensajería instantánea no solicitada para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

La aplicación de filtro inteligente de mensajería instantánea ayuda a proteger la implementación de Microsoft Lync Server 2013 frente a los virus más comunes con una degradación mínima para la experiencia del usuario. El filtro inteligente de mensaje instantáneo ofrece las siguientes prestaciones:

  - Mejor filtrado de direcciones URL

  - Mejor filtrado de transferencias de archivos

Use el filtro inteligente de mensaje instantáneo para configurar filtros que bloqueen los mensajes instantáneos no solicitados o potencialmente dañinos procedentes de extremos desconocidos más allá del firewall corporativo. Los filtros se configuran especificando los criterios que se van a usar para determinar lo que se va a bloquear, como mensajes instantáneos que contienen hipervínculos y archivos con extensiones específicas.

Antes de implementar la aplicación de filtro inteligente de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado cuando los mensajes se enrutan desde un servidor de 2013 de Lync Server a otro. Estas opciones de filtrado se aplican de manera coherente, independientemente de si los servidores se encuentran en una o en varias organizaciones. Esta coherencia se aplica a la forma en que los avisos y advertencias personalizados se insertan en los mensajes y se envían a través de los servidores.

La opción de filtrado recomendada es permitir los mensajes instantáneos con hipervínculos, pero obligar al filtro inteligente de mensaje instantáneo a que deshabilite el vínculo anteponiendo un carácter de subrayado. Si elige esta opción, tendrá además la oportunidad de redactar un aviso que va a aparecer al principio de cada mensaje instantáneo que contenga un hipervínculo.

La segunda opción de filtrado consiste en permitir los mensajes instantáneos con hipervínculos no modificados. Si elige esta opción, tendrá además la oportunidad de redactar una advertencia que se va a insertar en cada mensaje (opción recomendada).

La tercera opción consiste en bloquear todos los mensajes instantáneos que contengan un hipervínculo. Si elige esta opción, el servidor envía una advertencia al usuario. Debe escribir esta advertencia.

</div>

<span> </span>

</div>

</div>

</div>

