---
title: 'Lync Server 2013: Apéndice A: Usar cmdlets para implementar una aplicación de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9541e6cb63cee91a6bfd1072695fb3ce09a0134
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34843034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Apéndice A: Usar cmdlets para implementar una aplicación de sucursal con funciones de supervivencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

En este tema se describe cómo implementar una aplicación de rama superviviente con el shell de administración de Lync Server. Realice este procedimiento en el sitio central.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Para desplegar un equipo de sucursales con la supervivencia de forma remota

1.  Siga el procedimiento de [Agregar sitios de sucursal a su topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) para agregar un nuevo sitio de sucursal.

2.  Únase al sitio de la sucursal en el dominio.

3.  Agregue el grupo RTCUniversalSBATechnicians al grupo de administradores local.

4.  Reinicie el servidor e inicie sesión como miembro del grupo RTCUniversalSBATechnicians.

5.  En el shell de administración de Lync Server, escriba los siguientes comandos, sustituyendo los marcadores de posición por la información correcta para su organización:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

