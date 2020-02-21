---
title: 'Lync Server 2013: combinación de servidores compatibles con componentes perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e15580cdf9676f4e87cc6a9f385d2b75c16eb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Combinación de servidor compatibles para componentes perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

El servicio perimetral de acceso, el servicio perimetral de conferencia Web, el servicio perimetral A/V y el servicio Proxy XMPP se colocan en los servidores perimetrales. Los siguientes componentes perimetrales no se pueden colocar juntos ni con ningún otro rol de servidor de fea-edge-server-role-plural:

  - Servidor perimetral

  - Director (Optativo)

  - Proxy inverso

<div>


> [!IMPORTANT]  
> No es necesario dedicar el proxy inverso para servir solo Lync Server 2013. Por ejemplo, puede proporcionar servicios para publicar los servicios Web de Lync Server y proporcionar a la vez un sitio Web publicado para otro sitio web que no tenga ningún uso en Lync Server. Si ya tiene un servidor de proxy inverso en la red perimetral para admitir otros servicios, puede usarlo para Lync Server 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

