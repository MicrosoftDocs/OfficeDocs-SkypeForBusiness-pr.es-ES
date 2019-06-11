---
title: 'Lync Server 2013: Compatibilidad de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9be3bda71e44d0e739fce3a8d01db9cb84e2b9e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Compatibilidad de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-04_

Las topologías locales de los servicios de dominio de Active Directory que admite Lync Server 2013 son las siguientes:

  - Un solo bosque con un solo dominio

  - Un solo bosque con un solo árbol y varios dominios

  - Un solo bosque con varios árboles y espacios de nombres separados

  - Varios bosques en una topología de bosque central

  - Varios bosques en una topología de bosque de recursos

<div>


> [!NOTE]  
> Lync Server 2013 no admite dominios de etiqueta única. Por ejemplo, un bosque con un dominio raíz denominado <STRONG>contoso. local</STRONG> es compatible, pero no se admite un dominio raíz de una sola etiqueta denominado <STRONG>local</STRONG> . Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>de etiqueta única" en.



</div>

<div>


> [!NOTE]  
> Lync Server 2013 no permite cambiar el nombre de los dominios. Si necesita cambiar el nombre de un dominio donde se ha implementado Lync Server, primero debe desinstalar Lync Server, después cambiar el nombre del dominio y, a continuación, volver a instalar Lync Server.



</div>

Para obtener detalles sobre las topologías y los requisitos admitidos para implementaciones locales, consulte [requisitos, compatibilidad y topologías de los servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) en la documentación de planeación.

</div>

<span> </span>

</div>

</div>

</div>

