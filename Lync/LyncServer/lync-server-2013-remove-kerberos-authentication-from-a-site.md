---
title: 'Lync Server 2013: quitar la autenticación Kerberos de un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6546ac3e13795871461dcdd425e96e801ee19e9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>En Lync Server 2013 quitar la autenticación Kerberos de un sitio

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Si necesita quitar la autenticación Kerberos de un sitio o retirar un sitio, debe quitar la asignación de cuenta de autenticación Kerberos del sitio, usando el cmdlet **Remove-CsKerberosAccountAssignment**. Siga el procedimiento que se indica a continuación para quitar la asignación de cuenta de autenticación Kerberos, que quita la asignación de todos los equipos del sitio.

<div class=" ">


> [!WARNING]  
> Si retira permanentemente la cuenta habilitada para Kerberos, debe usar usuarios y equipos de Active Directory para eliminarla de servicios de dominio de Active Directory después de quitar la asignación. Si piensa usar el objeto en el futuro, es posible que prefiera conservar el objeto de Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Para quitar la autenticación Kerberos de un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Por ejemplo:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

