---
title: 'Lync Server 2013: Delegar permisos de instalación'
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
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegar permisos de instalación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Si no desea conceder la pertenencia al grupo administradores del dominio a usuarios o grupos que implementan Lync Server 2013, puede habilitar miembros del grupo RTCUniversalServerAdmins para que ejecuten el cmdlet **enable-CsTopology** de Windows PowerShell en servidores que ejecuten Lync Server 2013. De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins no tienen la capacidad de ejecutar este cmdlet. Puede conceder derechos y permisos de administrador para ejecutar **enable-CsTopology** en servidores que ejecuten Lync Server mediante el cmdlet **Grant-CsSetupPermission** y especificar una unidad organizativa (OU) donde se encuentran los objetos de equipo para el servidor que ejecuta Lync Server 2013.

La preparación del dominio que se realiza al instalar Lync Server no agrega automáticamente los permisos que permiten a los miembros del grupo RTCUniversalServerAdmins ejecutar el cmdlet enable-CsTopology. Eso significa que, de forma predeterminada, debe ser administrador de dominio para poder habilitar una topología. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de habilitar una topología, debe ejecutar el cmdlet Grant-CsSetupPermissions. Además, tendrá que ejecutar este cmdlet en cada contenedor de Active Directory en el que se encuentran los equipos que ejecutan Lync Server.

Tenga en cuenta que este cmdlet solo concede permisos al grupo RTCUniversalServerAdmins; el cmdlet no se puede usar para conceder permisos a otros grupos de seguridad o a usuarios individuales.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> es el cmdlet clave que permite a los miembros del grupo RTCUniversalServerAdmins configurar e implementar Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Para agregar la posibilidad de ejecutar enable-CsTopology en el grupo RTCUniversalServerAdmins

1.  Inicie sesión en un servidor como miembro del grupo administradores del dominio del dominio en el que se ejecutará el usuario delegado **enable-CsTopology**.

2.  Abra el shell de administración de Lync Server 2013. El shell de administración de Lync Server 2013 se instala automáticamente en cada servidor front-end o en cualquier equipo en el que se hayan instalado las herramientas administrativas de Lync Server 2013. Para obtener más información sobre el shell de administración de Lync Server 2013, consulte [Shell de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md) en la documentación de operaciones.

3.  Ejecute el siguiente cmdlet desde el shell de administración de Lync Server 2013:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Si la OU no es de nivel superior, debe proporcionar el nombre de dominio completo.

    
    </div>
    
    En el ejemplo siguiente, la uo es "Lync Servers", que se encuentra en el dominio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

