---
title: Comprobar la coexistencia del grupo piloto con el grupo heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4952640d6f6e938b460855118163d98e001f6a77
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo piloto con el grupo heredado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Comprobar el grupo de servidores en la herramienta administrativa de Office Communications Server 2007 R2

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda sucesivamente el nodo **Bosque**, **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y después expanda el grupo de servidores o el nombre de servidor.

3.  Asegúrese de que los servicios de Office Communications Server 2007 R2 se están ejecutando en el grupo de servidores.
    
    ![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Comprobar el grupo piloto en el panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro del rol CsAdministrator, inicie sesión en el servidor front-end de Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **Topología**.

4.  Compruebe que los servidores que ha implementado existen en el grupo piloto.
    
    ![Página de topología del panel de control de Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Página de topología del panel de control de Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Comprobar que se han iniciado los servicios de Lync Server 2013

1.  En el servidor front-end de Lync Server 2013, abra el applet **servicios** del grupo **herramientas administrativas** .

2.  Compruebe que los servicios que aparecen coinciden con la lista de la siguiente imagen.
    
    ![Página de servicios que muestra los servicios de Lync iniciados](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Página de servicios que muestra los servicios de Lync iniciados")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

