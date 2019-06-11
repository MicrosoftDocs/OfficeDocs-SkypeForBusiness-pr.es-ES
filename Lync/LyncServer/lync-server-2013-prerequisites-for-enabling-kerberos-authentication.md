---
title: 'Lync Server 2013: Requisitos previos para habilitar la autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Antes de habilitar la autenticación Kerberos, asegúrese de completar todas las preparaciones de configuración y de infraestructura necesarias:

  - El esquema de Active Directory se extiende para Lync Server 2013.

  - La preparación del bosque de Active Directory se completa para Lync Server 2013.

  - La preparación del dominio de Active Directory se completa para Lync Server 2013.

  - El almacén de administración central se instaló correctamente y está disponible.

  - La topología se ha creado y publicado mediante el generador de topologías.

  - Servidores y roles que requieren servicios web definidos e implementados, incluidos los servidores front-end, los servidores Standard Edition y los directores.

  - Los servicios de información de Internet (IIS) se configuran e implementan con los servicios de rol recomendados para admitir servicios web en Lync Server 2013.

Una vez cumplidos los requisitos previos, debe estar listo para crear una o varias cuentas para que los servicios web los usen para la autenticación Kerberos de la implementación. Como mínimo, debe crear una cuenta de autenticación Kerberos para cada implementación. Sin embargo, puede crear una cuenta para cada sitio para proporcionar autenticación Kerberos local en el sitio. Solo puede especificar una cuenta de autenticación de Kerberos por sitio.

</div>

<span> </span>

</div>

</div>

</div>

