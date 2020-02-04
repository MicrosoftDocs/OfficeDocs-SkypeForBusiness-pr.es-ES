---
title: 'Lync Server 2013: estado de replicación del almacén de administración central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4212e8616916f6a2a256530a7a0b74c9811f166d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Estado de replicación del almacén de administración central en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-26_

Cuando un administrador realiza un cambio de algún tipo en Lync Server (por ejemplo, cuando un administrador crea una nueva Directiva de voz o cambia la configuración del servidor de la libreta de direcciones), el cambio se registra en el almacén central de administración. A su vez, el cambio se debe replicar a todos los equipos que ejecutan los servicios de Lync Server o los roles de servidor.

Para replicar datos, el replicador maestro (que se ejecuta en el servidor de administración central) crea una instantánea de los datos de configuración cambiados. A continuación, se envía una copia de esta instantánea a cada equipo que ejecute los roles de servidor o los servicios de Lync Server. En estos equipos, un agente de replicación recibe la instantánea y carga los datos cambiados. Después, el agente envía un mensaje al replicador maestro para informar del estado de replicación más reciente.

El cmdlet Get-CsManagementStoreReplicationStatus le permite comprobar el estado de replicación de cualquiera (o de todos) los equipos de Lync Server de su organización.

¿Quién puede ejecutar este cmdlet? De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar localmente el cmdlet Get-CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Para devolver una lista de todos los roles RBAC a los que se asignó este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>Vea también


[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

