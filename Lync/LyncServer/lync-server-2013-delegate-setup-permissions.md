---
title: 'Lync Server 2013: Delegación de permisos de configuración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0fcf148e5e3cc4003dac97e8ef5ca9f1b2e678a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegación de permisos de instalación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Si no desea conceder la pertenencia al grupo administradores del dominio a los usuarios o grupos que están implementando Lync Server 2013, puede habilitar los miembros del grupo RTCUniversalServerAdmins para que ejecuten el cmdlet **enable-CsTopology** de Windows PowerShell en los servidores que ejecutan Lync Server 2013. De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins no pueden ejecutar este cmdlet. Para conceder derechos y permisos de administrador para ejecutar **enable-CsTopology** en servidores que ejecuten Lync Server, use el cmdlet **Grant-CsSetupPermission** y especifique una unidad organizativa (OU) en la que se encuentren los objetos de equipo del servidor que ejecuta Lync Server 2013.

La preparación del dominio que se produce al instalar Lync Server no agrega automáticamente los permisos que permiten a los miembros del grupo RTCUniversalServerAdmins ejecutar el cmdlet enable-CsTopology. Esto quiere decir que, de forma predeterminada, debe ser un administrador del dominio para poder habilitar una topología. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho para habilitar una topología, debe ejecutar el cmdlet Grant-CsSetupPermissions. Además, tendrá que ejecutar este cmdlet en cada contenedor de Active Directory que contenga equipos que ejecuten Lync Server.

Tenga en cuenta que este cmdlet solo concede permisos al grupo RTCUniversalServerAdmins; el cmdlet no se puede usar para conceder permisos a otros grupos de seguridad o a usuarios individuales.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> es el cmdlet Key que permite a los miembros del grupo RTCUniversalServerAdmins configurar e implementar Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Para conceder al grupo RTCUniversalServerAdmins la posibilidad de ejecutar Enable-CsTopology

1.  Inicie sesión en un servidor como miembro del grupo Admins. del dominio para el dominio en que el usuario delegado ejecutará **Enable-CsTopology**.

2.  Abra el shell de administración de Lync Server 2013. El shell de administración de Lync Server 2013 se instala automáticamente en cada servidor front-end o en cualquier equipo en el que se hayan instalado las herramientas administrativas de Lync Server 2013. Para obtener más información sobre el shell de administración de Lync Server 2013, consulte Shell de administración de Lync [server 2013](lync-server-2013-lync-server-management-shell.md) en la documentación de operaciones.

3.  Ejecute el siguiente cmdlet desde el shell de administración de Lync Server 2013:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Si la unidad organizativa no es de nivel superior, debe proporcionar el nombre de dominio completo.

    
    </div>
    
    En el ejemplo siguiente, la unidad organizativa es "Lync Servers" y se encuentra en el dominio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

