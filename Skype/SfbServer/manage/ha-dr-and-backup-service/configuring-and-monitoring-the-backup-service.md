---
title: Configurar y supervisar el servicio de copia de seguridad
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede usar los comandos del Shell de administración de Skype Empresarial Server para configurar y supervisar el servicio de copia de seguridad.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817200"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="6780d-103">Configuración y supervisión del servicio de copia de seguridad en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6780d-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="6780d-104">Puede usar los siguientes comandos del Shell de administración de Skype Empresarial Server para configurar y supervisar el servicio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6780d-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="6780d-105">Para restaurar la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end, consulte Restaurar el contenido de conferencia mediante el servicio de copia de [seguridad](#restore-conference-contents-using-the-backup-service), a continuación.</span><span class="sxs-lookup"><span data-stu-id="6780d-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="6780d-106">El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar **Get-CsBackupServiceStatus** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6780d-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="6780d-107">Para usar este cmdlet, inicie sesión como miembro de este grupo.</span><span class="sxs-lookup"><span data-stu-id="6780d-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="6780d-108">O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el uso del cmdlet **Set-CsBackupServiceConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6780d-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="6780d-109">Para ver la configuración del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6780d-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="6780d-110">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6780d-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="6780d-111">El valor predeterminado de SyncInterval es de dos minutos.</span><span class="sxs-lookup"><span data-stu-id="6780d-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="6780d-112">Para establecer el intervalo de sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6780d-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="6780d-113">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6780d-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="6780d-114">Por ejemplo, lo siguiente establece el intervalo en tres minutos.</span><span class="sxs-lookup"><span data-stu-id="6780d-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="6780d-115">Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado para el servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, puesto que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y en el objetivo del punto de recuperación (RPO).</span><span class="sxs-lookup"><span data-stu-id="6780d-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="6780d-116">Para obtener el estado del servicio de copia de seguridad para un determinado grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6780d-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="6780d-117">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6780d-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="6780d-118">El estado de la sincronización del servicio de copia de seguridad se define unidireccionalmente desde un grupo de servidores (P1) hasta su grupo de servidores de copia de seguridad (P2).</span><span class="sxs-lookup"><span data-stu-id="6780d-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="6780d-119">El estado de sincronización de P1 a P2 puede ser diferente que el de P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="6780d-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="6780d-120">Para P1 a P2, el servicio de copia de seguridad está en un estado "constante" si todos los cambios realizados en P1 se replican completamente sobre P2 dentro del intervalo de sincronización.</span><span class="sxs-lookup"><span data-stu-id="6780d-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="6780d-121">Está en el estado "final" si no hay ningún cambio más que se vaya a sincronizar de P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="6780d-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="6780d-122">Ambos estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6780d-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="6780d-123">Esto no implica que el estado devuelto permanezca tal cual después.</span><span class="sxs-lookup"><span data-stu-id="6780d-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="6780d-124">En particular, el estado "final" continuará manteniéndose solo si P1 no genera ningún cambio después de que se ejecute el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6780d-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="6780d-125">Esto es cierto en caso de que se produzca un error de P1 sobre P2 después de que P1 se sitúe en el modo de solo lectura como parte de la lógica de ejecución de **Invoke-CsPoolfailover**.</span><span class="sxs-lookup"><span data-stu-id="6780d-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="6780d-126">Para obtener información acerca de la relación de copia de seguridad de un determinado grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6780d-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="6780d-127">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6780d-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="6780d-128">Para forzar una sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6780d-128">To force a Backup Service sync</span></span>

<span data-ttu-id="6780d-129">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6780d-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="6780d-130">Restauración del contenido de conferencia mediante el servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6780d-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="6780d-131">Si la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end deja de estar disponible, debe restaurar esta información para que los usuarios que están en el grupo conserven sus datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6780d-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="6780d-132">Si el grupo de servidores front-end que ha perdido datos de conferencia está emparejado con otro grupo de servidores front-end, puede usar el servicio de copia de seguridad para restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="6780d-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="6780d-p105">También debe realizar esta tarea si se produce un error en un grupo de servidores entero y tiene que realizar la conmutación por error de sus usuarios a un servidor de copia de seguridad. Cuando estos usuarios se conmutan por error a su grupo de servidores original, también debe utilizar este procedimiento para copiar su contenido de conferencia de vuelta a su grupo de servidores original.</span><span class="sxs-lookup"><span data-stu-id="6780d-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="6780d-135">Supongamos que Grupo1 se usa junto con Grupo2 y que los datos de conferencia de Grupo1 se pierde.</span><span class="sxs-lookup"><span data-stu-id="6780d-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="6780d-136">Puede usar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar el contenido:</span><span class="sxs-lookup"><span data-stu-id="6780d-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="6780d-p107">La restauración de los contenidos de conferencia podría demorar un poco, según su tamaño. Puede utilizar el siguiente cmdlet para ver el estado del proceso:</span><span class="sxs-lookup"><span data-stu-id="6780d-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="6780d-139">El proceso finaliza cuando este cmdlet devuelve un valor de Estado parejo para el módulo de datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6780d-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
