---
title: Lync Server 2013 Active Directory support
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7769bd97b29d7a206edf8b1ea5878fa30b489300
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529587"
---
# <a name="active-directory-support-in-lync-server-2013"></a>Compatibilidad de Active Directory en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-04_

Las topologías locales de los servicios de dominio de Active Directory compatibles con Lync Server 2013 son las siguientes:

  - Un solo bosque con un solo dominio

  - Un solo bosque con un solo árbol y varios dominios

  - Un solo bosque con varios árboles y espacios de nombres separados

  - Varios bosques en una topología de bosque central

  - Varios bosques en una topología de bosque de recursos

<div>


> [!NOTE]  
> Lync Server 2013 no admite dominios de etiqueta única. Por ejemplo, un bosque con un dominio raíz denominado <STRONG>contoso. local</STRONG> es compatible, pero no se admite un dominio raíz de una sola etiqueta denominada <STRONG>local</STRONG> . Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS de etiqueta única" en <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A> .



</div>

<div>


> [!NOTE]  
> Lync Server 2013 no admite el cambio de nombre de dominios. Si necesita cambiar el nombre de un dominio en el que se ha implementado Lync Server, primero debe desinstalar Lync Server, luego cambiar el nombre del dominio y, a continuación, volver a instalar Lync Server.



</div>

Para obtener más información sobre las topologías admitidas y los requisitos de las implementaciones locales, vea [requisitos, compatibilidad y topologías de servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) en la documentación referente a la planeación.

</div>

<span> </span>

</div>

</div>

</div>

