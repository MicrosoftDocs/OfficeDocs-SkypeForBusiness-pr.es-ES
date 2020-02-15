---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b84d2c11fee62b0912cc43317ed6716dd33f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-06_

Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de lync Server 2013 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que se hayan instalado los componentes principales de Lync Server 2013 (OcsCore. msi).

Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.

</div>

<span> </span>

</div>

</div>

</div>

