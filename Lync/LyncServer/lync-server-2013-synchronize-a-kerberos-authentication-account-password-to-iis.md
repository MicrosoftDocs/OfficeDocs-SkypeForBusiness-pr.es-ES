---
title: Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811134697ea04f1dab3637e648ff89455fca07d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-11-08_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

En un sitio, los servidores front-end, los servidores Standard Edition y los directores pueden usar una cuenta de autenticación Kerberos con fines de autenticación de solicitudes al servicio de servicios Web. Este procedimiento busca cada servidor que ejecuta servicios web en un sitio al que se le ha asignado una cuenta Kerberos y actualiza las opciones de configuración de Internet Information Services (IIS) para que usen la cuenta Kerberos. Para obtener más información, consulte [establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Para establecer y configurar una contraseña de cuenta de autenticación Kerberos

1.  Inicie sesión en un equipo de origen (como, por ejemplo, fe01.contoso.com) como miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Desde la línea de comandos del shell de administración de Lync Server, ejecute los dos comandos siguientes:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Por ejemplo:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > El nombre del equipo de origen y del equipo de destino deben ser un nombre de dominio completo (FQDN) del servidor. No puede usar el FQDN del grupo de servidores a menos que el nombre del mismo sea igual que el nombre del equipo que está usando como equipo de origen o equipo de destino.

    
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

