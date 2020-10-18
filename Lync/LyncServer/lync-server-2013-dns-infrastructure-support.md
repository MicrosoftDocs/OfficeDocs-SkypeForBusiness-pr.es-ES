---
title: 'Lync Server 2013: compatibilidad con la infraestructura de DNS'
description: 'Lync Server 2013: compatibilidad con la infraestructura de DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea65907eba13367fd92e546d62994d10907bf89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574456"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Compatibilidad con la infraestructura de DNS en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-08_

Lync Server 2013 requiere el sistema de nombres de dominio (DNS) y lo usa de las siguientes maneras:

  - Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.

  - Para permitir a los clientes detectar el servidor Standard Edition o el grupo front-end que se usa para diversas transacciones SIP.

  - Para asociar las direcciones URL simples para conferencias con los servidores que hospedan dichas conferencias.

  - Para permitir a los clientes y servidores externos conectarse a los servidores perimetrales o el proxy inverso HTTP para la mensajería instantánea o las conferencias.

  - Para permitir que los dispositivos de comunicaciones unificadas (UC) que no se hayan registrado detecten el grupo front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.

  - Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.

  - Para el equilibrio de carga de DNS.

<div>


> [!NOTE]  
> Lync Server 2013 no admite nombres de dominio internacionalizados (IDN).



</div>

<div>


> [!IMPORTANT]  
> El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). Topology Builder usa nombres de dominio completos, no nombres cortos. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio. <STRONG>Utilice únicamente caracteres estándar </STRONG> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado).



</div>

</div>

<span> </span>

</div>

</div>

</div>

