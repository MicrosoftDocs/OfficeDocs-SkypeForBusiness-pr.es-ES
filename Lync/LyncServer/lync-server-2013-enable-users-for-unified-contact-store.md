---
title: 'Lync Server 2013: habilitar usuarios para el almacenamiento de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc769241059a2536ff644e6ea7b711aaa8cd342d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Habilitar a los usuarios para el almacén de contactos unificados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada. No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Lync Server 2013. Sin embargo, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificados. Puede habilitar esta característica globalmente, por sitio, por inquilino o por individuos o grupos de individuos.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Procedimiento para habilitar usuarios para el almacén de contactos unificados

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Siga uno de estos procedimientos:
    
      - Para habilitar el almacén de contactos Unificado de forma global para todos los usuarios de Lync Server, en la línea de comandos, escriba:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificados para los usuarios de un sitio específico, en la línea de comandos, escriba:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Por ejemplo:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificados por arrendatario, en la línea de comandos, escriba:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Por ejemplo:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificados para los usuarios especificados, en la línea de comandos, escriba:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.

        
        </div>
        
        Por ejemplo:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada <EM>Usuarios habilitados para UC</EM> con el indicador UcsAllowed establecido en Verdadero. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo cual significa que Ken Myer ahora está habilitado para el almacén de contactos unificados.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

