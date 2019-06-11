---
title: 'Lync Server 2013: Establecer una contraseña de cuenta de autenticación Kerberos en un servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc4eefe4c1ef804b1deb06d056bfbd61ade35eb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.

Debe configurar una contraseña en la cuenta de Kerberos para cada sitio que tenga servidores front-end, servidores Standard Edition y directores. Puede configurar la contraseña ejecutando el cmdlet **set-CsKerberosAccountPassword** de Windows PowerShell en un servidor del sitio (por ejemplo, un servidor front-end). Para cada sitio, debe ejecutar el cmdlet **set-CsKerberosAccountPassword** . El cmdlet configura Internet Information Services (IIS) para el servicio Web Services y, a continuación, establece la contraseña en la cuenta de equipo en servicios de dominio de Active Directory. Un método alternativo, basado en el parámetro que se usa con el cmdlet, configura IIS en un servidor al tiempo que se usa otro servidor que se haya configurado como el origen de la contraseña de la cuenta de Kerberos.

Al usar el cmdlet **set-CsKerberosAccountPassword** para establecer una contraseña, Kerberos establece la contraseña en una cadena generada de forma aleatoria. Este cmdlet se pone en contacto con todas las instancias de IIS en todos los sitios centrales de Lync Server 2013 a los que está asignada esta cuenta.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Para establecer una contraseña para una cuenta de autenticación Kerberos

1.  Inicie sesión en cualquier equipo del dominio con el shell de administración de Lync Server instalado como miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Por ejemplo:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Debe especificar el parámetro Cuentadeusuario con el formato Dominio\usuario. El formato usuario @ dominio. extensión no es compatible para hacer referencia a los objetos de equipo creados para la autenticación Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

