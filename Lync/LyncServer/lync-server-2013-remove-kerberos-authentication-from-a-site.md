---
title: 'Lync Server 2013: Quitar la autenticación Kerberos de un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f030083bc49822f1d41e297388f6ca7dbf66d397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Quitar la autenticación Kerberos de un sitio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.

Si necesita quitar la autenticación Kerberos de un sitio o retirar un sitio, debe quitar la asignación de cuenta de autenticación Kerberos del sitio mediante el cmdlet **Remove-CsKerberosAccountAssignment** . Use el siguiente procedimiento para quitar la asignación de cuenta de autenticación Kerberos, que quita la asignación de todos los equipos del sitio.

<div class=" ">


> [!WARNING]  
> Si va a retirar permanentemente la cuenta habilitada para Kerberos, debe usar usuarios y equipos de Active Directory para eliminarla de los servicios de dominio de Active Directory después de quitar la asignación. Si tiene previsto usar el objeto en el futuro, es posible que desee mantener el objeto de Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Para quitar la autenticación Kerberos de un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    Por ejemplo:
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```
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

