---
title: Implementar clientes de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331241dea4f047928913550764c995a7c6f05260
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Implementar clientes de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Después de migrar los usuarios a Lync Server 2013, haga lo siguiente:

1.  Use el filtro de versión de cliente en el nuevo servidor de Lync Server 2013 para permitir que los clientes que tengan instaladas las actualizaciones más recientes puedan iniciar sesión.

2.  Si fuera necesario, configure los valores de directivas de grupo necesarios para el arranque de clientes. Para obtener más información, consulte [configuración de directivas de arranque de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación sobre implementación. La configuración de estos valores es únicamente necesaria si desea cambiar las directivas de arranque de clientes existentes o si desea establecer directivas de arranque de clientes nuevas. Si no tiene previsto configurar directivas de arranque de clientes o si desea que las directivas de arranque de clientes heredadas no pierdan vigencia, no es necesario realizar ninguna acción.

3.  Configure otras directivas de usuario y de cliente para usuarios o grupos de usuarios específicos mediante el panel de control de Lync Server 2013, el shell de administración de Lync Server 2013 o ambos. Para obtener más información, consulte [New and changed Settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) en la documentación de planeación.

4.  Implemente la versión más reciente de los clientes de Lync Server 2013 junto con las actualizaciones acumulativas más recientes. Para obtener más información, consulte [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) en la documentación sobre implementación.

5.  Opcional Si su organización requiere el modo de privacidad de presencia mejorada de Lync Server 2013, una vez completada la migración, defina una regla de directiva de versión de cliente para impedir que las versiones de cliente anteriores inicien sesión. Posteriormente, habilite el modo de privacidad de presencia mejorada.
    
    <div>
    

    > [!IMPORTANT]  
    > No habilite el modo de privacidad de presencia mejorada de Lync 2013 hasta que todos los usuarios de un grupo de servidores determinado tengan instaladas las versiones de cliente más recientes.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

