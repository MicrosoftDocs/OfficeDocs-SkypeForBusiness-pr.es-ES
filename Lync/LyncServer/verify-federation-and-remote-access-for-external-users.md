---
title: Comprobar la federación y el acceso remoto de usuarios externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ad994eb7769dff067195520c2c6fde955910f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a>Comprobar la federación y el acceso remoto de usuarios externos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-18_

Después de la transición de la ruta de Federación al servidor perimetral de Lync Server 2013, debe realizar algunas pruebas funcionales para comprobar que la Federación se ejecuta según lo esperado. Las pruebas de acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos algunos de los siguientes elementos o todos ellos.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Probar la conectividad de usuarios externos y acceso externo

  - Usuarios de al menos un dominio federado, un usuario interno de Lync Server 2013 y un usuario en Lync Server 2010. Prueba la mensajería instantánea (mi), la presencia, el audio/vídeo (A/V) y el uso compartido del escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para el que se haya completado el aprovisionamiento) comunicándose con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.

  - Comprobar que los usuarios anónimos pueden unirse a conferencias.

  - Un usuario hospedado en Lync Server 2010 con acceso de usuario remoto (iniciar sesión en Lync Server 2010 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010. Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.

  - Un usuario hospedado en Lync Server 2013 con acceso de usuario remoto (iniciar sesión en Lync Server 2013 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010. Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.

</div>

</div>

<span> </span>

</div>

</div>

</div>

