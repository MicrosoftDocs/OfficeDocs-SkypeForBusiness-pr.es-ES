---
title: 'Lync Server 2013: nueva característica de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751d8cbbb4ab7a10ca468c0156e14a45c065fd25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a>Nueva característica de tronco en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En Microsoft Lync Server 2013, se pueden definir varios troncos entre un servidor de mediación y una puerta de enlace. Microsoft Lync Server 2010 solo se permite para un tronco entre un servidor de mediación y una puerta de enlace RTC. Esta característica ofrece la flexibilidad necesaria para definir troncos adicionales. Un tronco es una asociación lógica entre el FQDN de un servidor de mediación y el puerto de escucha y el FQDN y el puerto de escucha de la puerta de enlace RTC. Esta nueva capacidad permite una definición de tronco sencilla para la resistencia (donde se pueden usar varios servidores de mediación para enrutar llamadas a la misma puerta de enlace RTC), para la interoperabilidad de PBX, en la que se pueden usar varios troncos con diferentes directivas asociadas entre y IP-PBX y un servidor de mediación, y para las configuraciones de tronco SIP donde los servidores de mediación en diferentes sitios tienen troncos SIP a la portadora a la que hace referencia el mismo FQDN de portadora.

<div>

## <a name="see-also"></a>Vea también


[Nuevas características de Enterprise Voice en Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

