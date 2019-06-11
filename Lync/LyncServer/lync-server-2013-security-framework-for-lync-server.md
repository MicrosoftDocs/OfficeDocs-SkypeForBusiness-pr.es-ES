---
title: 'Lync Server 2013: marco de seguridad para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Marco de seguridad para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-08_

Esta sección proporciona una descripción general de los elementos fundamentales que forman el marco de seguridad de Microsoft Lync Server 2013. Comprender el funcionamiento conjunto de estos elementos es esencial para tomar decisiones fundamentadas sobre la seguridad de su implementación particular de Lync Server 2013.

Dichos elementos son los siguientes:

  - Los servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio de back-end de confianza para cuentas de usuario y recursos de red.

  - El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.

  - La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.

  - La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).

  - Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.

  - Windows PowerShell ofrece características de seguridad que están habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts con facilidad o sin problemas.

Estos elementos de seguridad fundamentales funcionan conjuntamente para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Lync Server 2013.

<div>

## <a name="in-this-section"></a>En esta sección

Los temas de esta sección describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su infraestructura de Lync Server.

  - [Servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Control de acceso basado en roles (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infraestructura de clave pública para Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS y MTLS para Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Cifrado para Lync Server 2013](lync-server-2013-encryption.md)

  - [Autenticación de usuarios y clientes para Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Herramientas de administración de Windows PowerShell y Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

