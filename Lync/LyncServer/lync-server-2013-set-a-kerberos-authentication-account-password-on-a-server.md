---
title: 'Lync Server 2013: establecer una contraseña de cuenta de autenticación Kerberos en un servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeef318392540aaa0600a4b61f20a296df25ca5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Debe configurar una contraseña en la cuenta de Kerberos por cada sitio que tenga servidores front-end, servidores Standard Edition y directores. Puede configurar la contraseña si ejecuta el cmdlet **set-CsKerberosAccountPassword** de Windows PowerShell en un servidor del sitio (por ejemplo, un servidor front-end). Para cada sitio, debe ejecutar el cmdlet **set-CsKerberosAccountPassword** . El cmdlet configura Internet Information Services (IIS) para el servicio de servicios web y, a continuación, establece la contraseña en la cuenta de equipo en servicios de dominio de Active Directory. Un método alternativo, basado en el parámetro que se usa con el cmdlet, configura IIS en un servidor mientras usa otro servidor que se ha configurado como el origen de la contraseña de la cuenta de Kerberos.

Cuando usa el cmdlet **Set-CsKerberosAccountPassword** para establecer una contraseña, Kerberos elige como contraseña una cadena generada al azar. Este cmdlet se pone en contacto con todas las instancias de IIS en todos los sitios centrales de Lync Server 2013 a los que esta cuenta está asignada.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Para establecer una contraseña de una cuenta de autenticación de Kerberos

1.  Inicie sesión en cualquier equipo del dominio que tenga instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Por ejemplo:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Debe especificar el parámetro UserAccount con el formato dominio\nombre de usuario. No se admite el formato Usuario@Dominio.extensión para hacer referencia a los objetos de equipo creados para la autenticación de Kerberos.

    
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

