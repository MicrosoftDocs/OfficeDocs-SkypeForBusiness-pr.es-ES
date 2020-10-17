---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 931ec2c67c8cdf0d1856cce7264ee968e3ea96f0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508427"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-06_

Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de lync Server 2013 en el equipo interno en el que se encuentra el almacén de administración central, o en cualquier equipo unido al dominio en el que se hayan instalado los componentes principales de Lync Server 2013 (OcsCore.msi).

Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.

</div>

<span> </span>

</div>

</div>

</div>

