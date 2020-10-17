---
title: Habilitar control remoto de llamadas
description: Habilitar el control remoto de llamadas.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8009ffc927ad3f7a4f83ad3505100f3a9d4e82d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551136"
---
# <a name="enable-remote-call-control"></a>Habilitar control remoto de llamadas

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

El control remoto de llamadas permite a los usuarios controlar sus teléfonos de central de conmutación (PBX) de escritorio con Lync Server 2013. Si implementó el control remoto de llamadas en su entorno heredado y desea migrar it Lync Server 2013, debe realizar las siguientes tareas:

1.  Instale una puerta de enlace SIP/CSTA y configúrela para que se comunique con su PBX. Debe realizar este paso al implementar el grupo piloto de Lync Server 2013.

2.  Después de combinar la topología y migrar las directivas y la configuración, configure Lync Server 2013 para enrutar las solicitudes CSTA a la puerta de enlace SIP/CSTA. Se trata de un paso manual que sigue a la migración automatizada. Para configurar el enrutamiento de solicitudes CSTA, lleve a cabo una de las siguientes acciones:
    
      - Quite las entradas de host autorizado heredado (conocidas como *entradas de servidor de confianza* en Lync Server 2013). Si va a migrar los usuarios de la implementación heredada, asegúrese de quitar todas las entradas de host autorizadas existentes que ha creado para la puerta de enlace SIP/CSTA antes de configurar las nuevas entradas de la aplicación de confianza en el grupo piloto de Lync Server 2013. Para obtener información detallada acerca de cómo quitar entradas de host autorizadas heredadas, consulte [quitar una entrada de host autorizado](remove-an-authorized-host-entry.md).
    
      - Configure una ruta estática para el control remoto de llamadas. Puede configurar una ruta estática para los grupos individuales en los que quiera usar el control remoto de llamadas, o bien configurar una ruta estática global para que la usen los grupos que no tengan una individual configurada expresamente. Para obtener más información sobre cómo configurar la ruta estática, vea [Configure a static Route for Remote Call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) en la documentación sobre implementación.
    
      - Configure una entrada de aplicación de confianza de control remoto de llamadas en cada grupo en el que quiera admitir el control remoto de llamadas. Para obtener más información sobre cómo configurar una entrada de aplicación de confianza, vea [Configure a Trusted Application entry for Remote Call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) en la documentación sobre implementación.

3.  Si ha implementado una puerta de enlace SIP/CSTA que usa el protocolo de control de transmisión (TCP) para conectarse a Lync Server 2013, defina la dirección IP de la puerta de enlace en el generador de topologías. Para obtener más información sobre cómo definir la dirección IP, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) en la documentación sobre implementación.

4.  Configure los usuarios de Lync 2013 para el control remoto de llamadas habilitando el control remoto de llamadas y asignando un identificador uniforme de recursos (URI) de servidor de línea y un URI de línea. Al migrar usuarios de la implementación heredada a Lync Server 2013, la configuración del control de llamadas remotas se migra junto con la configuración del otro usuario.

5.  Si personalizó las reglas de normalización de números de teléfono de la Libreta de direcciones en la implementación heredada, cuando finalice la migración automatizada de las directivas y las configuraciones deberá realizar algunas tareas manuales para migrar estas reglas de normalización personalizadas. Si no personalizó ninguna regla, la Libreta de direcciones se migra con el resto de la topología. Para obtener información detallada sobre cómo migrar manualmente las reglas de normalización personalizadas, consulte [Migrate Address Book](migrate-address-book.md).

</div>

<span> </span>

</div>

</div>

</div>

