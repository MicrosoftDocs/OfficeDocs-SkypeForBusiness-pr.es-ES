---
title: 'Lync Server 2013: Compatibilidad con infraestructura de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa9670761e16032abf0c205bbb740cbe1f43c4a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Compatibilidad con infraestructura de DNS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-08_

Lync Server 2013 requiere el sistema de nombres de dominio (DNS) y lo usa de las siguientes maneras:

  - Para detectar los servidores o grupos de servidores internos para las comunicaciones de servidor a servidor.

  - Para permitir que los clientes descubran el grupo de servidores front-end o el servidor Standard Edition usado para varias transacciones SIP.

  - Para asociar las direcciones URL simples a las conferencias con los servidores que hospedan esas conferencias.

  - Para permitir que los servidores y clientes externos se conecten a servidores perimetrales o al proxy inverso HTTP para mensajería instantánea (mi) o conferencias.

  - Para habilitar los dispositivos de comunicaciones unificadas (UC) que no han iniciado sesión para detectar el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos, obtener actualizaciones y enviar registros.

  - Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que introducir direcciones URL en la configuración del dispositivo de forma manual.

  - Para el equilibrio de carga de DNS.

<div>


> [!NOTE]  
> Lync Server 2013 no admite nombres de dominio internacionalizados (IDNs).



</div>

<div>


> [!IMPORTANT]  
> El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor. De forma predeterminada, el nombre de equipo en el caso de un equipo que no está unido a un dominio es un nombre corto, no un nombre de dominio completo (FQDN). El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. <STRONG>Utilice únicamente caracteres estándar</STRONG> (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado).



</div>

</div>

<span> </span>

</div>

</div>

</div>

