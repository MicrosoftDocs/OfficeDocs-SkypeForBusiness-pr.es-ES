---
title: Compatibilidad con infraestructura de certificados 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b17c6f53130d5f0cca96ce3b719001029398d91c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508007"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Compatibilidad con la infraestructura de certificados en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Lync Server 2013 requiere una infraestructura de clave pública (PKI) para admitir conexiones de seguridad de la capa de transporte (TLS) y TLS mutua (MTLS). De forma predeterminada, Lync Server 2013 está configurado para usar TLS para las conexiones de cliente a servidor. MTLS se usa para las conexiones entre servidores.

Los certificados MTLS deben ser emitidos por entidades de certificación (CA) de confianza para Lync Server 2013. Lync Server admite certificados que se emiten desde las siguientes entidades de certificación:

  - Certificados emitidos por una entidad de certificación interna:
    
      - La entidad de certificación del sistema operativo Windows Server 2003
    
      - La entidad de certificación del sistema operativo Windows Server 2008
    
      - La entidad de certificación del sistema operativo Windows Server 2008 R2
    
      - La entidad de certificación del sistema operativo Windows Server 2012
    
      - La entidad de certificación del sistema operativo Windows Server 2012 R2

  - Certificados emitidos por una entidad de certificación pública

La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con las demás aplicaciones y productos. Para la versión 2013, Lync Server 2013 y otros productos de servidor de Microsoft, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo Open Authorization (OAuth) para la autenticación y autorización de servidor a servidor. Para obtener más información, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre implementación o sobre operaciones.

Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008 R2 y Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 incluye soporte para certificados (pero no obligatorios) firmados con la función de hash criptográfica SHA-256. Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.

Para obtener más información sobre los requisitos de certificado, consulte [Certificate Infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) en la documentación referente a la planeación. Para obtener más información sobre el uso de caracteres comodín con certificados, consulte [compatibilidad con certificados comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) en la documentación sobre compatibilidad.

</div>

<span> </span>

</div>

</div>

</div>

