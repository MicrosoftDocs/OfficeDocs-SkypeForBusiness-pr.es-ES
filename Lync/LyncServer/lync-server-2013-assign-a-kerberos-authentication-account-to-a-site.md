---
title: 'Lync Server 2013: Asignar una cuenta de autenticación Kerberos a un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c706f9fdd8932456a9f1617e55dc9231dbd6a84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-04-18_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.

Después de crear la cuenta de Kerberos, debe asignarla a un sitio. Este es un sitio de Lync Server 2013, no un sitio de Active Directory. Puede crear varias cuentas de autenticación Kerberos por implementación, pero solo puede asignar una cuenta a un sitio. Use el procedimiento siguiente para asignar una cuenta de autenticación Kerberos creada previamente a un sitio. Para obtener detalles sobre la creación de la cuenta de Kerberos, consulte [crear una cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Para asignar una cuenta de autenticación Kerberos a un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```
        Enable-CsTopology
       ```
    
    Por ejemplo:
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Debe especificar el parámetro Cuentadeusuario con el formato Dominio\usuario. El formato usuario @ dominio. extensión no es compatible para hacer referencia a los objetos de equipo creados para la autenticación Kerberos.

    
    </div>

4.  **Opcional**: es posible que haya configurado un reemplazo de FQDN (nombre de dominio completo) para los servicios Web, según [cambie la dirección URL de los servicios web en Lync Server 2013](lync-server-2013-change-the-web-services-url.md). Si es así, también tendrá que agregar un SPN para este FQDN. Por ejemplo, si el FQDN es webservices. contoso. local, ejecutaría:
    
        setspn -S http/webservices.contoso.local kerbauth

5.     
    <div class="">
    

    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

