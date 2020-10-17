---
title: 'Lync Server 2013: requisitos previos para habilitar la autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0be98112431b9e57486bb33e0eab84eada94e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506787"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Antes de habilitar la autenticación Kerberos, asegúrese de completar todos los preparativos de configuración y la infraestructura de requisitos previos:

  - El esquema de Active Directory se ha ampliado para Lync Server 2013.

  - La preparación del bosque de Active Directory se ha completado para Lync Server 2013.

  - La preparación del dominio de Active Directory se ha completado para Lync Server 2013.

  - El almacén de administración central se ha instalado correctamente y está disponible.

  - La topología se ha creado y publicado mediante el generador de topologías.

  - Se han definido e implementado los servidores y roles que requieren servicios Web, incluidos los servidores front-end, los servidores Standard Edition y los directores.

  - Internet Information Services (IIS) está configurado e implementado con los servicios de rol recomendados para admitir servicios web en Lync Server 2013.

Una vez cumplidos los requisitos previos, debe estar preparado para crear una o más cuentas para los servicios web que se usarán para la autenticación Kerberos en su implementación. Como mínimo, es necesario crear una cuenta de autenticación Kerberos para cada implementación. Sin embargo, puede crearse una cuenta en cada sitio para proporcionar autenticación local Kerberos en el sitio. Únicamente se puede especificar una sola cuenta de autenticación Kerberos por sitio.

</div>

<span> </span>

</div>

</div>

</div>

