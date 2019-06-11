---
title: 'Lync Server 2013: Habilitar usuarios para el almacenamiento de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ece699d8c5b43e09323708c075687bfe81146e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada. No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Lync Server 2013. Pero, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificado. Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Para habilitar usuarios para el almacén de contactos unificado

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Siga uno de estos pasos:
    
      - Para habilitar el almacén de contactos unificado globalmente para todos los usuarios de Lync Server, en la línea de comandos, escriba:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en la línea de comandos, escriba:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Por ejemplo:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificado por inquilino, en la línea de comandos, escriba:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Por ejemplo:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificado para usuarios específicos, en la línea de comandos, escriba:
        
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
        > En el ejemplo anterior, el primer comando crea una directiva por usuario denominada <EM>Usuarios habilitados para UCS</EM> con el indicador UcsAllowed establecido en True. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo que significa que Ken Myer ahora está habilitado para el almacén de contactos unificado.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

