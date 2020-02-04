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

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="84744-102">Restauración de contenidos de conferencia mediante el servicio de copias de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84744-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84744-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="84744-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="84744-104">Si la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end no está disponible.</span><span class="sxs-lookup"><span data-stu-id="84744-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="84744-105">debe restaurar esta información para que los usuarios alojados en el grupo conserven sus datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="84744-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="84744-106">Si el grupo de servidores front-end que ha perdido los datos de la Conferencia está emparejado con otro grupo de servidores front-end, puede usar el servicio de copia de seguridad para restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="84744-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="84744-107">También debe realizar esta tarea si se ha producido un error en un grupo completo y tiene que migrar por error sus usuarios a un grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="84744-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="84744-108">Cuando estos usuarios no realicen una conmutación por error a su grupo original, debe usar este procedimiento para copiar el contenido de la Conferencia a su grupo original.</span><span class="sxs-lookup"><span data-stu-id="84744-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="84744-109">Supongamos que Pool1 está emparejado con Pool2, y se pierden los datos de la Conferencia en Pool1.</span><span class="sxs-lookup"><span data-stu-id="84744-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="84744-110">Puede usar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar el contenido:</span><span class="sxs-lookup"><span data-stu-id="84744-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="84744-111">La restauración del contenido de la Conferencia puede llevar algún tiempo, dependiendo de su tamaño.</span><span class="sxs-lookup"><span data-stu-id="84744-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="84744-112">Puede usar el siguiente cmdlet para comprobar el estado del proceso:</span><span class="sxs-lookup"><span data-stu-id="84744-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="84744-113">El proceso se realiza cuando este cmdlet devuelve un valor de estado estable para el módulo de conferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="84744-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

