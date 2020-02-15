---
title: 'Lync Server 2013: restauración de contenidos de Conferencia mediante el servicio de copia de seguridad'
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
ms.openlocfilehash: d8fb791362718b2bce5e7c13c0cc6aab779d954f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="22da9-102">Restauración de contenidos de Conferencia mediante el servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22da9-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22da9-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="22da9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="22da9-p101">Si la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end deja de estar disponible, debe restaurar esta información de modo tal que los usuarios hospedados en el grupo de servidores conserven sus datos de conferencia. Si el grupo de servidores front-end que ha perdido datos de conferencia se usa junto con otro grupo de servidores front-end, puede utilizar el servicio de copia de seguridad para restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="22da9-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="22da9-p102">También debe realizar esta tarea si se produce un error en un grupo de servidores entero y tiene que realizar la conmutación por error de sus usuarios a un servidor de copia de seguridad. Cuando estos usuarios se conmutan por error a su grupo de servidores original, también debe utilizar este procedimiento para copiar su contenido de conferencia de vuelta a su grupo de servidores original.</span><span class="sxs-lookup"><span data-stu-id="22da9-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="22da9-109">Supongamos que Grupo1 se usa junto con Grupo2 y que los datos de conferencia de Grupo1 se pierde.</span><span class="sxs-lookup"><span data-stu-id="22da9-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="22da9-110">Puede usar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar el contenido:</span><span class="sxs-lookup"><span data-stu-id="22da9-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="22da9-p104">La restauración de los contenidos de conferencia podría demorar un poco, según su tamaño. Puede utilizar el siguiente cmdlet para ver el estado del proceso:</span><span class="sxs-lookup"><span data-stu-id="22da9-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="22da9-113">El proceso finaliza cuando este cmdlet devuelve un valor de Estado parejo para el módulo de datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="22da9-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

