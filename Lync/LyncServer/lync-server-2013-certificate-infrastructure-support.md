---
title: 'Lync Server 2013: Compatibilidad con infraestructura de certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13e04e2e6746dac9c40eaa6df0c3b33d52c6a547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Compatibilidad con infraestructura de certificados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Lync Server 2013 requiere una infraestructura de clave pública (PKI) para admitir conexiones de seguridad de nivel de transporte (TLS) y TLS Mutual (MTLS). De forma predeterminada, Lync Server 2013 está configurado para usar TLS para las conexiones entre clientes y servidores. MTLS se usa para las conexiones entre servidores.

Los certificados MTLS deben ser emitidos por entidades de certificación (CA) de confianza para Lync Server 2013. Lync Server admite certificados emitidos por las siguientes CA:

  - Certificados emitidos por una entidad de certificación interna:
    
      - La entidad de certificación del sistema operativo Windows Server 2003
    
      - La entidad de certificación del sistema operativo Windows Server 2008
    
      - La entidad de certificación del sistema operativo Windows Server 2008 R2
    
      - La entidad de certificación del sistema operativo Windows Server 2012
    
      - La entidad de certificación del sistema operativo Windows Server 2012 R2

  - Certificados emitidos por una entidad de certificación pública

La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con otras aplicaciones y productos. Para la versión 2013, Lync Server 2013 y otros productos de Microsoft Server, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo de autorización abierta (OAuth) para la autenticación y la autorización de servidor a servidor. Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación o en la documentación de operaciones.

Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008 R2 y Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 incluye compatibilidad con certificados (pero no obligatorios) firmados con SHA-256 función hash criptográfica. Para admitir el acceso externo mediante SHA-256, un certificado externo es emitido por una entidad de certificación pública con SHA-256.

Para obtener más información sobre los requisitos de certificado, consulte [requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) en la documentación de planeación. Para obtener más información sobre el uso de caracteres comodín con certificados, consulte [compatibilidad de certificados comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) en la documentación de soporte técnico.

</div>

<span> </span>

</div>

</div>

</div>

