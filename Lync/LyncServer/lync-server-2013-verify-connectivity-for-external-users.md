---
title: 'Lync Server 2013: comprobar la conectividad de usuarios externos'
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
ms.openlocfilehash: 89f1721967ec693556fecd12d31f45b9b3d108d4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Comprobar la conectividad de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La validación de la conectividad para los usuarios externos requiere garantizar la conectividad de los usuarios al servidor y el puerto para el servicio perimetral de acceso.

Un recurso valioso para confirmar la configuración y la capacidad de conectarse, enviar y recibir mensajes correctos para los escenarios que requiere el acceso de usuarios externos es el sitio analizador de conectividad remota<http://www.testocsconnectivity.com>(). El sitio es administrado y mantenido por el soporte técnico de Microsoft. Para acceder al analizador de conectividad remota, abra el sitio web en un explorador y siga las instrucciones para seleccionar el escenario.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Comprobación de conectividad de los usuarios externos y el acceso externo

Las pruebas para el acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos todos o algunos de los siguientes elementos:

  - Usuarios de al menos un dominio federado y probar la mensajería instantánea, la presencia, el uso compartido de escritorio y A/V.

  - Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para los que se haya completado el aprovisionamiento).

  - Usuarios anónimos.

  - Usuarios de la organización que han iniciado sesión en Lync de forma remota, pero que no usan VPN.

Estas pruebas determinan si el servidor perimetral es:

  - Escucha en los puertos necesarios mediante el uso de un cliente de Telnet desde fuera de la red.
    
      - Ejemplo: Telnet sip.contoso.com 443
    
      - Realice la prueba anterior en los puertos que usa en el servidor perimetral o en el grupo de servidores perimetrales en función de la implementación.

  - Realizar una resolución de DNS externa precisa.
    
      - Desde fuera de la red haga ping a cada uno de los FQDN externos del grupo perimetral o perimetral. Incluso si se produce un error en el comando ping, verá las direcciones IP, que puede comparar con las que ha asignado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

