---
title: Implementar clientes de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Implementar clientes de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Después de migrar usuarios a Lync Server 2013, haga lo siguiente:

1.  Use el filtro de versión del cliente en el nuevo servidor de Lync Server 2013 para permitir que los clientes con las actualizaciones más recientes estén instalados para iniciar sesión.

2.  Si es necesario, establezca la configuración de directiva de grupo que se requiere para el inicio del cliente. Para obtener información detallada, consulte [configuración de directivas de inicio de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación de implementación. La configuración de esta configuración solo es necesaria si desea cambiar las directivas de inicio del cliente existentes o si desea establecer nuevas directivas de inicio del cliente. Si no tiene previsto configurar directivas de inicio del cliente o desea que las directivas de inicio del cliente heredadas permanezcan efectivas, no es necesario realizar ninguna acción.

3.  Configure otras directivas de usuario y cliente para usuarios específicos o grupos de usuarios mediante el panel de control de Lync Server 2013, el shell de administración de Lync Server 2013 o ambos. Para obtener más información, vea [configuración nueva y modificada de Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) en la documentación de planeación.

4.  Implemente la versión más reciente de los clientes de Lync Server 2013 junto con las actualizaciones acumulativas más recientes. Para obtener más información, vea [implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) en la documentación de implementación.

5.  Faculta Si su organización requiere Lync Server 2013 modo de privacidad de presencia mejorado, una vez completada la migración, defina una regla de directiva de versión de cliente para evitar que las versiones de cliente anteriores inicien sesión. A continuación, habilitar el modo de privacidad de presencia mejorado.
    
    <div>
    

    > [!IMPORTANT]  
    > No habilite el modo de privacidad de presencia mejorada de Lync 2013 hasta que todos los usuarios de un grupo de servidores determinado tengan instaladas las versiones más recientes de los clientes.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

