---
title: 'Lync Server 2013: Concesión de permisos de instalación'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Concesión de permisos de instalación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-27_

Puede usar el cmdlet **Grant-CsSetupPermission** para agregar permisos de lectura, escritura, ReadSPN y WriteSPN al grupo RTCUniversalServerAdmins para una unidad organizativa (OU) específica de Active Directory. A continuación, los miembros del grupo RTCUniversalServerAdmins de esa unidad organizativa pueden instalar servidores que ejecuten Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores de dominio.

Use el cmdlet **Test-CsSetupPermission** para comprobar los permisos que configuró mediante el cmdlet **Grant-CsSetupPermission** .

Puede usar el cmdlet **REVOKE-CsSetupPermission** para quitar los permisos que ha otorgado mediante el cmdlet **Grant-CsSetupPermission** .

<div>

## <a name="to-grant-setup-permissions"></a>Para conceder permisos de configuración

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea conceder permisos de configuración. Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers). Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) completo de la uo (por ejemplo, "CN = Computers, DC = Contoso, DC = com"). En este último caso, debe especificar un DN de Uo que sea coherente con el dominio que especifique.
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Para comprobar los permisos de configuración

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de configuración que ha otorgado mediante el cmdlet **Grant-CsSetupPermission** . Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers). Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) completo de la uo (por ejemplo, "CN = Computers, DC = Contoso, DC = com"). En este último caso, debe especificar un DN de Uo que sea coherente con el dominio que especifique.
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Para revocar los permisos de configuración

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de configuración que ha otorgado el cmdlet **Grant-CsSetupPermission** . Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers). Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) completo de la uo (por ejemplo, "CN = Computers, DC = Contoso, DC = com"). En este último caso, debe especificar un DN de Uo que sea coherente con el dominio que especifique.
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

