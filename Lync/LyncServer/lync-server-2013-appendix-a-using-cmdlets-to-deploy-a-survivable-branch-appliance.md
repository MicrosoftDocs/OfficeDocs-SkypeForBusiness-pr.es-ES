---
title: 'Lync Server 2013: Apéndice A: usar cmdlets para implementar una aplicación de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb77c4f22122694d928489f7d61beaa9cbae9355
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Apéndice A: uso de cmdlets para implementar una aplicación de sucursal con funciones de supervivencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

En este tema se describe cómo implementar una aplicación de sucursal con funciones de supervivencia mediante el shell de administración de Lync Server. Realice este procedimiento en el sitio central.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Para implementar una aplicación de sucursal con funciones de supervivencia de forma remota

1.  Siga el procedimiento descrito en [Add Branch sites to your Topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) para agregar un nuevo sitio de sucursal.

2.  Unir el sitio de sucursal al dominio.

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

