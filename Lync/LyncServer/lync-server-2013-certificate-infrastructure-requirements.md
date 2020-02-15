---
title: Requisitos de infraestructura de certificados 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b64f06d9ca879236c0842554c1779fb7bbc1cbe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestructura de certificados para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-23_

Lync Server 2013 requiere una infraestructura de clave pública (PKI) para admitir conexiones TLS y TLS mutua (MTLS).

Lync Server usa certificados para los propósitos siguientes:

  - Conexiones TLS entre clientes y servidores

  - Conexiones MTLS entre servidores

  - Federación mediante la detección automática basada en DNS de los socios

  - Acceso de usuarios remotos a la mensajería instantánea (IM)

  - Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias

  - Solicitudes móviles mediante detección automática de servicios web

Para Lync Server, se aplican los siguientes requisitos comunes:

  - Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).

  - Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).

  - Todos los certificados deben estar firmados con un algoritmo de firma compatible con el sistema operativo. Lync Server 2013 admite el conjunto de tamaños de compendio SHA-1 y SHA-2 (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo. Para compatibilidad con sistemas operativos, [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)consulte.
    
    <div>
    

    > [!NOTE]  
    > No se admite el uso del algoritmo de firma RSASSA-PSS, lo que puede producir errores en los problemas de inicio de sesión y desvío de llamadas, entre otros.

    
    </div>

  - La inscripción automática se admite para los servidores internos que ejecutan Lync Server.

  - La inscripción automática no es compatible con los servidores perimetrales de Lync Server.

  - Cuando envíe una solicitud de certificado web a una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecute Windows Server 2003 con SP2 o Windows XP.
    
    Tenga en cuenta que aunque KB922706 ofrece soporte técnico para resolver problemas relacionados con los certificados web de inscripción de una inscripción web de los servicios de certificados de Windows Server 2003, no permite el uso de Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado desde una entidad de certificación de Windows Server 2003.

  - Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomiendan longitudes de clave de 2048 y posteriores.

  - El algoritmo de síntesis predeterminada, o firma de hash, es RSA. También se\_admiten los\_algoritmos de P256\_ECDH, ECDH P384 y P521 ECDH. 

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos de certificado para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Requisitos de certificado para el servidor de chat persistente en Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Requisitos de certificados para movilidad en Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

