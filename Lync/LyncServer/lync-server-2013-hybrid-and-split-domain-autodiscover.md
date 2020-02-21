---
title: 'Lync Server 2013: híbrido y dividido-dominio-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fca0097f6ad0264755dd9d0a80a296e9ebf60b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Híbrido y dividido-dominio-detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

Un espacio de direcciones SIP compartido, también conocido como implementación de *dominio dividido* o implementación *híbrida* , es una configuración en la que los usuarios se implementan en una implementación local y en un entorno en línea. El resultado deseado es tener a un usuario, independientemente de dónde se encuentre el servidor principal (local o en línea), iniciar sesión en la implementación y ser redireccionado a la ubicación del servidor principal. Para ello, se usa la característica de detección automática de Lync Server 2013 para redirigir el usuario en línea a la topología en línea. Para ello, configure el localizador uniforme de recursos (URL) de detección automática mediante el shell de administración de Lync Server, el cmdlet **Get-CsHostingProvider** y el cmdlet **set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Movilidad para la implementación de dominio dividido

Necesitará recopilar y registrar los siguientes atributos implementados:

  - Desde el shell de administración de Lync Server, escriba
    
        Get-CsHostingProvider

  - En los resultados, encuentre el proveedor en línea que tenga el atributo **ProxyFQDN**. Por ejemplo, sipfed.online.lync.com.

  - Registre el valor de ProxyFQDN.

  - Habilite la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea.

  - Habilite la federación para el proveedor en línea. De forma predeterminada, todos los usuarios en línea están habilitados para la Federación de dominios y pueden comunicarse con todos los dominios.

  - Si va a definir dominios bloqueados y permitidos, determine los dominios que se permitirán o se bloquearán explícitamente.

  - Para la Federación en línea, debe planear las excepciones del firewall, los certificados y los registros de host DNS (A o AAAA, si usa IPv6). Asimismo, debe configurar las directivas de federación. Para obtener más información, consulte [Planning for Lync Server 2013 y Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

