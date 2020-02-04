---
title: 'Lync Server 2013: Comprobar la conectividad de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1f8a9bbda54c596a9ccae8451b15ce7300bffd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Comprobar la conectividad de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La validación de la conectividad de los usuarios externos requiere garantizar la conectividad de los usuarios con el servidor y el puerto del servicio perimetral de acceso.

Un recurso muy útil para confirmar la configuración y la capacidad de conectar, enviar y recibir los mensajes correctos para los escenarios que requiere el acceso de usuarios externos es el analizador de conectividad<http://www.testocsconnectivity.com>remota (). El sitio es administrado y mantenido por el soporte técnico de Microsoft. Para comunicarse con el analizador de conectividad remota, abra el sitio web en un explorador y siga las instrucciones para seleccionar el escenario.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Probar la conectividad de usuarios externos y acceso externo

Las pruebas para el acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos cualquiera de los siguientes elementos:

  - Usuarios de al menos un dominio federado y prueba la mensajería instantánea, la presencia, A/V y el uso compartido del escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para el que se ha completado el aprovisionamiento).

  - Usuarios anónimos.

  - Los usuarios de su organización que hayan iniciado sesión en Lync de forma remota, pero no utilicen VPN.

Estas pruebas determinan si su servidor perimetral es:

  - Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.
    
      - Ejemplo: Telnet sip.contoso.com 443
    
      - Realice la prueba anterior en los puertos que está usando en el servidor perimetral o en el grupo de servidores perimetrales dependiendo de su implementación.

  - Logre una resolución de DNS externa precisa.
    
      - Desde fuera de la red haga ping a cada uno de los FQDN externos de su grupo perimetral o perimetral. Incluso si se produce un error en la ping, verá las direcciones IP, que puede comparar con las que ha asignado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

