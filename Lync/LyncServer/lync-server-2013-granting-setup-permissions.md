---
title: 'Lync Server 2013: concesión de permisos de instalación'
description: 'Lync Server 2013: concesión de permisos de instalación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554486"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a>Concesión de permisos de instalación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-27_

Puede usar el cmdlet **Grant-CsSetupPermission** para agregar permisos de lectura, escritura, ReadSPN y WriteSPN al grupo RTCUniversalServerAdmins para una unidad organizativa (OU) de Active Directory específica. A continuación, los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa pueden instalar servidores que ejecuten Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores del dominio.

Use el cmdlet **Test-CsSetupPermission** para comprobar los permisos configurados mediante el cmdlet **Grant-CsSetupPermission** .

Puede usar el cmdlet **REVOKE-CsSetupPermission** para quitar los permisos concedidos mediante el cmdlet **Grant-CsSetupPermission** .

<div>

## <a name="to-grant-setup-permissions"></a>Para conceder permisos de configuración

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea conceder permisos de configuración. Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers). Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com"). En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Para comprobar los permisos del programa de instalación

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de configuración que ha concedido mediante el cmdlet **Grant-CsSetupPermission** . Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers). Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com"). En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Para revocar los permisos de instalación

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de instalación concedidos por el cmdlet **Grant-CsSetupPermission** . Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers). Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com"). En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

