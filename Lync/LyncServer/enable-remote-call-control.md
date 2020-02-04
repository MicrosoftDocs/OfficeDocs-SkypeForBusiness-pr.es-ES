---
title: Habilitar control remoto de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190f4e56a291ce48b5cd18b2dcd3e1b3461e3d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Habilitar control remoto de llamadas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

El control remoto de llamadas permite a los usuarios controlar sus teléfonos de escritorio privado de escritorio (PBX) con Lync Server 2013. Si ha implementado el control remoto de llamadas en su entorno heredado y desea migrar it Lync Server 2013, debe realizar las siguientes tareas:

1.  Instala una puerta de enlace SIP/CSTA y configúrela para comunicarse con tu PBX. Debe realizar este paso al implementar el grupo piloto de Lync Server 2013.

2.  Después de combinar su topología y migrar las directivas y la configuración, configure Lync Server 2013 para que enruten las solicitudes de CSTA a la puerta de enlace SIP/CSTA. Este paso es un paso manual que sigue la migración automática. Para configurar el enrutamiento de las solicitudes de CSTA, haga lo siguiente:
    
      - Elimine las entradas de host autorizadas heredadas (conocidas como *entradas de servidor de confianza* en Lync Server 2013). Si va a migrar usuarios de la implementación heredada, asegúrese de quitar todas las entradas de host autorizadas existentes que haya creado para la puerta de enlace SIP/CSTA antes de configurar las nuevas entradas de aplicaciones de confianza en el grupo piloto de Lync Server 2013. Para obtener más información sobre cómo quitar entradas de host heredadas, consulte [quitar una entrada de host autorizado](remove-an-authorized-host-entry.md).
    
      - Configurar una ruta estática para el control remoto de llamadas. Puede configurar una ruta estática para agrupaciones individuales que desee que admitan el control remoto de llamadas o puede configurar una ruta estática global para que cada grupo de servidores que no esté configurado con una ruta estática en el nivel de grupo use la ruta estática global. Para obtener más información sobre cómo configurar la ruta estática, vea [configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) en la documentación de implementación.
    
      - Configure una entrada de aplicación de confianza para el control remoto de llamadas en cada grupo para el que desee admitir el control remoto de llamadas. Para obtener más información sobre cómo configurar una entrada de aplicación de confianza, vea [configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) en la documentación de implementación.

3.  Si ha implementado una puerta de enlace SIP/CSTA que usa el protocolo de control de transmisión (TCP) para conectarse a Lync Server 2013, defina la dirección IP de la puerta de enlace en el generador de topología. Para obtener más información sobre cómo definir la dirección IP, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) en la documentación de implementación.

4.  Configure los usuarios de Lync 2013 para el control remoto de llamadas habilitando el control remoto de llamadas y asignando un identificador uniforme de recursos (URI) de line Server y un URI de línea. Al migrar usuarios de la implementación heredada a Lync Server 2013, se migra la configuración de control de llamada remota junto con la configuración del otro usuario.

5.  Si ha personalizado las reglas de normalización de números de teléfono de la libreta de direcciones en la implementación heredada, tendrá que realizar algunas tareas manuales una vez completada la migración automática de las directivas y la configuración para migrar las reglas de normalización personalizadas. Si no ha personalizado las reglas de normalización, la libreta de direcciones se migrará junto con el resto de la topología. Para obtener detalles sobre la migración manual de reglas de normalización, consulte [migrar la libreta de direcciones](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

