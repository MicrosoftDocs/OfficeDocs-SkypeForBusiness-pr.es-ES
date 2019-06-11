---
title: 'Lync Server 2013: configurar la Federación para un proveedor de servicios de audioconferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf49947034f995b10551985450f560bc1d3693
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Configurar la Federación para un proveedor de servicios de audioconferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-24_

Si desea usar un proveedor de servicios de audioconferencia (ACP) en su implementación híbrida (Lync Server local con Lync Online), debe configurar la Federación entre su implementación local de Lync y el socio ACP como un servidor asociado autorizado. Para configurar la federación, agregue el dominio del asociado del ACP y el servidor perimetral (también se puede denominar servidor proxy de acceso) a la lista de dominios federados para la implementación local. Luego, su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor ACP para obtener un asociado adicional de detailsYour ACP, entonces necesita agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.

  - **Cómo agregar el dominio del ACP y el servidor perimetral como un dominio federado permitido**
    
    Para agregar el dominio ACP como servidor asociado permitido (dominio federado permitido), siga los pasos que se indican en [configurar compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Para el servidor perimetral, agregue el FQDN del servidor perimetral del asociado del ACP. Puede que tenga que contactar con el asociado del ACP para obtener el FQDN del servidor perimetral, que el ACP también puede denominar servidor proxy de acceso.

  - **Proporcionar el FQDN de su grupo de servidores perimetrales al asociado del ACP**
    
    El asociado del ACP tiene que configurar la federación para agregar su dominio local como un servidor de asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.

</div>

<span> </span>

</div>

</div>

</div>

