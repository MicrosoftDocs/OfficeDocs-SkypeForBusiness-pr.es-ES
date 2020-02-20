---
title: 'Lync Server 2013: configurar certificados para el proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d03cec1dd2397b8471788f5c4661305e7ea93e42
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Configurar certificados para el proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Todos los servidores proxy inversos requieren un certificado de servidor web para usarlos en el servicio de escucha. El certificado de servidor web debe ser emitido por una entidad de certificación (CA) pública.

Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>Para configurar un certificado de servicios web para el servidor proxy inverso

  - Debe haber configurado previamente el servidor proxy inverso, incluida la configuración del certificado de servicios web. Si no lo hizo antes de iniciar la implementación de los servidores perimetrales, use los procedimientos descritos en Configuring [Reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para crear una solicitud e instalar el certificado de servicios web y, a continuación, cree cada regla de publicación web y configúrela para usar el certificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

