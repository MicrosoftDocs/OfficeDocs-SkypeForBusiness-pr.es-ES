---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
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
ms.openlocfilehash: 7585970a53ffd94959653555dad8a02724ba2f03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Comprobar el grupo en la herramienta administrativa de Office Communications Server 2007 R2

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda el nodo **bosque** , expanda el nodo **servidores Standard Edition** o grupos de servidores **Enterprise** y, a continuación, expanda el nombre del servidor o grupo de servidores.

3.  Asegúrese de que los servicios de Office Communications Server 2007 R2 se están ejecutando en el grupo.
    
    ![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Comprobar la agrupación piloto en el panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro del rol CsAdministrator, inicie sesión en el servidor front-end de Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **topología**.

4.  Verifique que los servidores que ha implementado estén presentes en el grupo piloto.
    
    ![Página de topología del panel de control de Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Página de topología del panel de control de Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Comprobar que los servicios de Lync Server 2013 se han iniciado

1.  En el servidor front-end de Lync Server 2013, abra el subprograma **servicios** desde el grupo **herramientas administrativas** .

2.  Verifique que los servicios enumerados coincidan con la lista de la siguiente ilustración.
    
    ![Página de servicios que muestra los servicios de Lync iniciados](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Página de servicios que muestra los servicios de Lync iniciados")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

