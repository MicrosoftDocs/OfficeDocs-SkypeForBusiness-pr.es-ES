---
title: 'Lync Server 2013: conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54230fb489a62ed5d7a80bfe871af3bc097e35e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530897"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

En su organización, hay un grupo perimetral designada como el grupo para la federación XMPP. Si este grupo se desactiva, debe conmutar por error la federación XMPP para que use otro grupo perimetral antes de que la federación XMPP pueda volver a trabajar.

Al instalar primero los grupos perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres estableciendo registros SRV de DNS externos para todos los grupos perimetrales para la federación XMPP, en lugar de solo uno. Cada uno de estos registros SRV debe tener establecida una prioridad diferente. Todo el tráfico de la federación XMPP atraviesa el grupo con el registro SRV con la prioridad más alta. Para obtener más información sobre cómo habilitar y configurar la Federación XMPP, consulte Configuración de la [Federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

En el procedimiento siguiente, EdgePool1 es el grupo que originalmente alojó la federación XMPP y EdgePool2 es el grupo que alojará ahora la federación de XMPP.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Conmutación por error del grupo perimetral usado para la federación XMPP

1.  Si no tiene implementado otro grupo perimetral (además del que está desactivado), implemente dicha grupo. Para obtener más información, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  En cada servidor perimetral del nuevo grupo perimetral que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:
    
        Stop-CsWindowsService

3.  Ejecute el siguiente cmdlet para cambiar la ruta de la federación XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    En este ejemplo, Site2 es el sitio que contiene el grupo perimetral que alojará ahora la federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral del grupo.

4.  En el servidor DNS externo, cambie el registro de DNS A de la federación XMPP para que apunte a EdgeServer2.contoso.com.

5.  Si aún no tiene un registro SRV de DNS para la federación XMPP que resuelva al grupo perimetral que alojará ahora la federación de XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Compruebe que el grupo perimetral que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.

7.  Inicie los servicios en todos los servidores perimetrales del grupo perimetral que alojará ahora la federación XMPP:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

