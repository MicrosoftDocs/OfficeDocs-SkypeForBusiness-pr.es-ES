---
title: Validar la replicación de las opciones de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698686dd217bf16457e4c3f4ebe6867566dcf49d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>Validar la replicación de las opciones de configuración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de Lync Server 2013 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo de dominio Unido en el que estén instalados los componentes básicos de lync Server 2013.

Los resultados iniciales pueden indicar que el estado es "false" en lugar de "true" para la replicación. En ese caso, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y deje que se complete la replicación antes de volver a ejecutar el cmdlet **Get-CsManagementStoreReplicationStatus** .

</div>

<span> </span>

</div>

</div>

</div>

