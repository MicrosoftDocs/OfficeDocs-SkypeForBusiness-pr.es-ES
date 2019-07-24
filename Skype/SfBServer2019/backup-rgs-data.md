---
title: Copia de seguridad de los datos del servicio de grupo de respuesta (RGS) en Skype empresarial Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Obtenga información sobre cómo hacer una copia de seguridad de los datos del servicio de grupo de respuesta (RGS) en Skype empresarial Server 2019.
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821337"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="eb5c9-103">Hacer una copia de seguridad de los datos del servicio de grupo de respuesta (RGS)</span><span class="sxs-lookup"><span data-stu-id="eb5c9-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="eb5c9-104">Con la actualización acumulativa de Skype empresarial Server 2019 de julio, hemos incluido la capacidad de incluir datos RGS como parte de la copia de seguridad estándar.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="eb5c9-105">Replicación de datos RGS</span><span class="sxs-lookup"><span data-stu-id="eb5c9-105">RGS data replication</span></span>

<span data-ttu-id="eb5c9-106">Siga los pasos que se indican a continuación para probar la funcionalidad de replicación de datos.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="eb5c9-107">Instale la actualización acumulativa de julio en todos los front-ends (FEs) del grupo emparejado.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="eb5c9-108">Instale la base de datos RGS en ambos miembros del grupo emparejado:</span><span class="sxs-lookup"><span data-stu-id="eb5c9-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="eb5c9-109">Ejecute el siguiente cmdlet en ambos grupos para replicar los datos RGS existentes en las tablas de copia de seguridad de modo que los datos puedan ser recogidos por RGSBackupService:</span><span class="sxs-lookup"><span data-stu-id="eb5c9-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="eb5c9-110">Habilitar RGSBackupService (esto le permitirá RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="eb5c9-111">Si este parámetro se establece en true, RGSBackupService comenzará a sincronizar los datos de RGS en los grupos emparejados (los dos grupos deben ser CU1).</span><span class="sxs-lookup"><span data-stu-id="eb5c9-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="eb5c9-112">Espere unos minutos hasta que se inicie.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="eb5c9-113">Inicialmente, el estado de RGS BackupService será NotInitialized.):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="eb5c9-114">Para comprobar BackupServiceStatus:</span><span class="sxs-lookup"><span data-stu-id="eb5c9-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="eb5c9-115">Para comprobar la replicación de datos entre grupos, use estos cmdlets (estos cmdlets solo muestran los datos del grupo de propietarios):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="eb5c9-116">Para comprobar los datos del grupo de propietarios RGS y sus datos de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="eb5c9-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="eb5c9-117">Comprobar la funcionalidad de flujo de trabajo realizando una llamada de audio al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="eb5c9-118">Conmute por error al grupo de propietarios de RGS.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="eb5c9-119">Comprobar la funcionalidad de flujo de trabajo realizando una llamada de audio al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="eb5c9-120">Failback de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-120">Failback the pool.</span></span>
1. <span data-ttu-id="eb5c9-121">Actualice los datos de RGS en el grupo de origen y realice otra conmutación por error para comprobar que los cambios se reflejan en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="eb5c9-122">RGS debe comportarse de la misma manera en que se comporta antes de la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="eb5c9-123">Le recomendamos que realice estos pasos en una gran mayoría de datos y realice tareas de recuperación y conmutación por error frecuentes.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="eb5c9-124">También se debe replicar cualquier nuevo RGS creado después de esta actualización de CU.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="eb5c9-125">Cmdlets de RGS</span><span class="sxs-lookup"><span data-stu-id="eb5c9-125">RGS cmdlets</span></span>

- <span data-ttu-id="eb5c9-126">Para comprobar BackupServiceStatus (el estado de exportación debe estar en el estado final o permanente).</span><span class="sxs-lookup"><span data-stu-id="eb5c9-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="eb5c9-127">El estado de la importación debe ser normal.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="eb5c9-128">RGSBackupservice debe estar habilitado.):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="eb5c9-129">Para sincronizar completamente los datos de RGS en el grupo de copia de seguridad (esto sincronizará los datos RGS completos del grupo de copias de seguridad):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="eb5c9-130">Para sincronizar completamente el almacén de datos RGS en el grupo de copias de seguridad (esto sincronizará los datos RGS completos en el grupo de copias de seguridad):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="eb5c9-131">Para sincronizar los datos Delta de RGS en el grupo de copia de seguridad (esto sincronizará los datos Delta en el grupo de copia de seguridad solo para RGS):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="eb5c9-132">Para sincronizar todos los datos de módulo, incluido RGS:</span><span class="sxs-lookup"><span data-stu-id="eb5c9-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="eb5c9-133">Para deshabilitar RGSBackupService (se deshabilitará RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="eb5c9-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="eb5c9-134">Si este parámetro se establece en true, RGSBackupService se deshabilitará en todos los grupos emparejados.):</span><span class="sxs-lookup"><span data-stu-id="eb5c9-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
