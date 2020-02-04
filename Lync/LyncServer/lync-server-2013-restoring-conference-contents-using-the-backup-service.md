---
title: 'Lync Server 2013: Restauración de contenidos de conferencia mediante el servicio de copias de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Restauración de contenidos de conferencia mediante el servicio de copias de seguridad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Si la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end no está disponible. debe restaurar esta información para que los usuarios alojados en el grupo conserven sus datos de conferencia. Si el grupo de servidores front-end que ha perdido los datos de la Conferencia está emparejado con otro grupo de servidores front-end, puede usar el servicio de copia de seguridad para restaurar los datos.

También debe realizar esta tarea si se ha producido un error en un grupo completo y tiene que migrar por error sus usuarios a un grupo de copia de seguridad. Cuando estos usuarios no realicen una conmutación por error a su grupo original, debe usar este procedimiento para copiar el contenido de la Conferencia a su grupo original.

Supongamos que Pool1 está emparejado con Pool2, y se pierden los datos de la Conferencia en Pool1. Puede usar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar el contenido:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauración del contenido de la Conferencia puede llevar algún tiempo, dependiendo de su tamaño. Puede usar el siguiente cmdlet para comprobar el estado del proceso:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

El proceso se realiza cuando este cmdlet devuelve un valor de estado estable para el módulo de conferencia de datos.

</div>

<span> </span>

</div>

</div>

</div>

