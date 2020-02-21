---
title: 'Lync Server 2013: concesión de permisos de unidad organizativa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85c43cb727b83b06d6427e2bf3b6027d78dc025e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Concesión de permisos de unidad organizativa en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-14_

Puede usar el cmdlet **Grant-CsOuPermission** para conceder permisos a objetos en unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a ellos sin ser miembros del grupo administradores del dominio. Los permisos agregados a la unidad organizativa especificada tienen los mismos permisos que el cmdlet **enable-CsAdDomain** agrega a los contenedores Computers and users durante la preparación del dominio.

Use el cmdlet **Test-CsOuPermission** para comprobar los permisos configurados mediante el cmdlet **Grant-CsOuPermission**.

Puede usar el cmdlet **Revoke-CsOuPermission** para quitar permisos que haya concedido mediante el cmdlet **Grant-CsOuPermission**.

<div>

## <a name="to-grant-ou-permissions"></a>Para conceder permisos de unidades organizativas

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio al que desea conceder permisos de unidad organizativa. Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Para comprobar permisos de unidades organizativas

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de OU que ha concedido mediante el cmdlet **Grant-CsOuPermission** . Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Para revocar permisos de unidades organizativas

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de OU concedidos por el cmdlet **Grant-CsOuPermission** . Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

