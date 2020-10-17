---
title: 'Lync Server 2013: marco de seguridad para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f84b7eaf3476624479d1ecb7c7bb564a4eae8ad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510447"
---
# <a name="security-framework-for-lync-server-2013"></a>Marco de seguridad para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-08_

En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad para Microsoft Lync Server 2013. Comprender cómo estos elementos funcionan juntos es esencial para tomar decisiones informadas sobre la seguridad de su implementación de Lync Server 2013 en particular.

Estos elementos son los siguientes:

  - Los Servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio back-end de confianza para las cuentas de usuario y los recursos de red.

  - El control de acceso de Role-Based (RBAC) le permite delegar tareas administrativas a la vez que mantiene altos estándares de seguridad.

  - La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.

  - TLS (Seguridad de la capa de transporte), HTTPS sobre SSL (HTTPS) y MTLS (Mutual TLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y aplicaciones compartidas punto a punto se cifran usando el protocolo de transporte seguro en tiempo real (SRTP).

  - Para la autenticación se usan los protocolos estándar de la industria, siempre que sea posible.

  - Windows PowerShell proporciona funciones de seguridad habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts fácilmente o sin darse cuenta.

Estos elementos fundamentales de seguridad funcionan en conjunto para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Lync Server 2013.

<div>

## <a name="in-this-section"></a>En esta sección

En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de la infraestructura de Lync Server.

  - [Servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Control de acceso basado en roles (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infraestructura de clave pública para Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS y MTLS para Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Cifrado para Lync Server 2013](lync-server-2013-encryption.md)

  - [Autenticación de usuario y cliente para Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Herramientas de administración de Windows PowerShell y Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

