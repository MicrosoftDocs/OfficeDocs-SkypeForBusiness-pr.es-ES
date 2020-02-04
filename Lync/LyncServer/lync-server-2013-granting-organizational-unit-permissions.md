---
title: 'Lync Server 2013: Conceder permisos de unidad organizativa'
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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Conceder permisos de unidad organizativa en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-14_

Puede usar el cmdlet **Grant-CsOuPermission** para conceder permisos a los objetos de unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a ellos sin ser miembros del grupo administradores del dominio. Los permisos agregados a la unidad organizativa especificada son los mismos permisos que el cmdlet **enable-CsAdDomain** agrega a los contenedores de equipos y usuarios durante la preparación del dominio.

Use el cmdlet **Test-CsOuPermission** para comprobar los permisos que configuró mediante el cmdlet **Grant-CsOuPermission** .

Puede usar el cmdlet **REVOKE-CsOuPermission** para quitar los permisos que ha otorgado mediante el cmdlet **Grant-CsOuPermission** .

<div>

## <a name="to-grant-ou-permissions"></a>Para conceder permisos de Uo

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio al que desee conceder permisos de Uo. Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Para comprobar los permisos de Uo

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de Uo que ha otorgado mediante el cmdlet **Grant-CsOuPermission** . Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Para revocar permisos de Uo

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar permisos de OU que ha otorgado el cmdlet **Grant-CsOuPermission** . Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

