---
title: 'Lync Server 2013: Conmutación por error para el grupo de servidores perimetrales para la federación XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

En su organización, hay un grupo perimetral designado como grupo para usar en la Federación XMPP. Si este grupo deja de funcionar, debe conmutar por error la Federación XMPP para usar un grupo de servidores perimetrales diferente antes de que la Federación XMPP pueda volver a funcionar.

La primera vez que instala agrupaciones de límites y habilita la Federación de XMPP, puede simplificar el proceso de recuperación ante desastres configurando registros SRV de DNS para todos los grupos de borde para la Federación de XMPP, en lugar de solo uno. Cada uno de estos registros SRV debe tener un conjunto de prioridades diferente. Todo el tráfico de Federación XMPP pasa por el grupo con el registro SRV con la prioridad más alta. Para obtener más información sobre cómo habilitar y configurar la Federación XMPP, consulte [configurar la Federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

En el procedimiento siguiente, EdgePool1 es el grupo que originalmente contenía la Federación de XMPP y EdgePool2 es el grupo que ahora hospedará la Federación XMPP.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Error en el grupo perimetral usado para la Federación XMPP

1.  Si aún no tiene otra agrupación perimetral implementada (aparte de la que actualmente está desactivada), implemente ese grupo. Para obtener más información, consulte [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  En cada servidor perimetral en el nuevo grupo de límites que ahora hospede la Federación XMPP (EdgePool2), ejecute el siguiente cmdlet:
    
        Stop-CsWindowsService

3.  Ejecute el cmdlet siguiente para redirigir la ruta de Federación de XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    En este ejemplo, Site2 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral en ese grupo.

4.  En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.

5.  Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.

7.  Inicie los servicios en todos los servidores perimetrales del grupo perimetral que ahora hospedarán la Federación de XMPP:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

