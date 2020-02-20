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
ms.openlocfilehash: f45029b4818a555dd21f7bf5afef70cdca5b50e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a>Comprobar la federación y el acceso remoto de usuarios externos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-18_

Después de realizar la transición de la ruta de Federación al servidor perimetral de Lync Server 2013, debe realizar algunas pruebas funcionales para comprobar que la Federación funciona como se esperaba. Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Comprobación de conectividad de los usuarios externos y el acceso externo

  - Usuarios de al menos un dominio federado, un usuario interno en Lync Server 2013 y un usuario en Lync Server 2010. Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.

  - Compruebe que los usuarios anónimos pueden unirse a conferencias.

  - Un usuario hospedado en Lync Server 2010 con acceso de usuarios remotos (iniciando sesión en Lync Server 2010 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010. Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.

  - Un usuario hospedado en Lync Server 2013 con acceso de usuarios remotos (iniciando sesión en Lync Server 2013 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010. Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.

</div>

</div>

<span> </span>

</div>

</div>

</div>

