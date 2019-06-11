---
title: 'Lync Server 2013: Configurar certificados para el proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Configurar certificados para el proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Cada servidor proxy inverso requiere un certificado de servidor web para que lo use el servicio de escucha. El certificado de servidor Web debe ser emitido por una entidad de certificación (CA) pública.

Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>Para configurar un certificado de servicios web para el proxy inverso

  - Ya debe haber configurado su proxy inverso, incluyendo la configuración del certificado de servicios Web. Si no lo hizo antes de iniciar la implementación de los servidores perimetrales, use los procedimientos de [configuración de los servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para crear solicitudes e instalar el certificado de servicios web y, después, cree cada regla de publicación web y Configúrelo para usar el certificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

