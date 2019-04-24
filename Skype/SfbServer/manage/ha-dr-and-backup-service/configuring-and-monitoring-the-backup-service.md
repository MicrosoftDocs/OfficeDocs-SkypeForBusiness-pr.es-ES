---
title: Configurar y supervisar el servicio de copia de seguridad
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede usar Skype para comandos de Shell de administración de Business Server para configurar y supervisar el servicio de copia de seguridad.
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199880"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="4839e-103">Configurar y supervisar el servicio de copia de seguridad de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4839e-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="4839e-104">Puede usar el siguiente Skype para comandos de Shell de administración de Business Server para configurar y supervisar el servicio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4839e-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="4839e-105">Para restaurar la información de conferencia almacenada en el almacén de archivos de un grupo de servidores Front-End, vea [Restaurar contenidos de conferencia mediante el servicio de copia de seguridad](#restore-conference-contents-using-the-backup-service), más adelante.</span><span class="sxs-lookup"><span data-stu-id="4839e-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="4839e-106">Grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar **Get-CsBackupServiceStatus** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4839e-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="4839e-107">Para usar este cmdlet, inicie sesión como un miembro de este grupo.</span><span class="sxs-lookup"><span data-stu-id="4839e-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="4839e-108">O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el cmdlet **Set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4839e-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="4839e-109">Para ver la configuración del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4839e-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="4839e-110">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4839e-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="4839e-111">El valor predeterminado de SyncInterval es de dos minutos.</span><span class="sxs-lookup"><span data-stu-id="4839e-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="4839e-112">Para establecer el intervalo de sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4839e-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="4839e-113">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4839e-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="4839e-114">Por ejemplo, el siguiente establece el intervalo en tres minutos.</span><span class="sxs-lookup"><span data-stu-id="4839e-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="4839e-115">Aunque se puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado para el servicio de copia de seguridad, no debe hacer por lo que a menos que sea absolutamente necesario, como la sincronización de intervalo tiene un gran impacto en el rendimiento del servicio de copia de seguridad y el objetivo de punto de recuperación (RPO).</span><span class="sxs-lookup"><span data-stu-id="4839e-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="4839e-116">Para obtener el estado del servicio de copia de seguridad para un determinado grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="4839e-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="4839e-117">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4839e-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="4839e-118">El estado de sincronización del servicio de copia de seguridad se define unidirectionally desde un grupo de servidores (P1) a su grupo de copia de seguridad (P2).</span><span class="sxs-lookup"><span data-stu-id="4839e-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="4839e-119">El estado de la sincronización de P1 a P2 puede ser diferente de P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="4839e-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="4839e-120">Para P1 a P2, el servicio de copia de seguridad está en un estado "constante" si todos los cambios realizados en P1 se replican completamente a través de a P2 dentro del intervalo de sincronización.</span><span class="sxs-lookup"><span data-stu-id="4839e-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="4839e-121">No es en el estado "final" Si no hay ningún cambio para que esté sincronizada de P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="4839e-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="4839e-122">Ambos Estados indicarán una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4839e-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="4839e-123">No implica que el estado devuelto permanecerá tal cual después.</span><span class="sxs-lookup"><span data-stu-id="4839e-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="4839e-124">En particular, el estado "final" seguirá contener sólo si P1 no se genera ningún cambio después de ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4839e-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="4839e-125">Esto es así en el caso de conmutación por error P1 a P2 después de P1 se coloca en el modo de solo lectura como parte de la lógica de ejecución **Invoke-CsPoolfailover** .</span><span class="sxs-lookup"><span data-stu-id="4839e-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="4839e-126">Para obtener información acerca de la relación de copia de seguridad para un determinado grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="4839e-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="4839e-127">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4839e-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="4839e-128">Para forzar una sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4839e-128">To force a Backup Service sync</span></span>

<span data-ttu-id="4839e-129">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4839e-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="4839e-130">Restauración de contenidos de conferencia mediante el servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4839e-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="4839e-131">Si no está disponible la información de conferencia almacenada en el almacén de archivos de un grupo de servidores Front-End, debe restaurar esta información para que los usuarios alojados en el grupo de servidores mantienen sus datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4839e-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="4839e-132">Si el grupo de servidores Front-End que ha perdido datos de la conferencia se corresponde con otro grupo de servidores Front-End, puede usar el servicio de copia de seguridad para restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="4839e-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="4839e-133">También debe realizar esta tarea si ha generado un error en un grupo de servidores completa y haya se lleve a cabo a través de sus usuarios a un grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4839e-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="4839e-134">Cuando estos usuarios se no se pudo volver a través de su grupo de servidores original, debe usar este procedimiento para copiar el contenido de su conferencias así como su grupo de servidores original.</span><span class="sxs-lookup"><span data-stu-id="4839e-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="4839e-135">Se supone que grupo1 se empareja con Grupo2, y se perderán los datos de conferencia en el grupo1.</span><span class="sxs-lookup"><span data-stu-id="4839e-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="4839e-136">Puede usar el cmdlet siguiente para invocar el servicio de copia de seguridad para restaurar el contenido:</span><span class="sxs-lookup"><span data-stu-id="4839e-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="4839e-137">Restaurar el contenido de la conferencia puede tardar algún tiempo, dependiendo de su tamaño.</span><span class="sxs-lookup"><span data-stu-id="4839e-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="4839e-138">Puede usar el cmdlet siguiente para comprobar el estado del proceso:</span><span class="sxs-lookup"><span data-stu-id="4839e-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="4839e-139">El proceso se realiza cuando este cmdlet devuelve un valor de estado estable para el módulo de conferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="4839e-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
