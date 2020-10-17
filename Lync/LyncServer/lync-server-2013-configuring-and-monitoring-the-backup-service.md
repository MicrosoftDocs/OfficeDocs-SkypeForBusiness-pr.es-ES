---
title: 'Lync Server 2013: configuración y supervisión del servicio de copia de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3df8f2208566ed89feda0a06c4cce8f699d130d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517567"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="1284b-102">Configuración y supervisión del servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1284b-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1284b-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1284b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1284b-104">Puede usar los siguientes comandos del shell de administración de Lync Server para configurar y supervisar el servicio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1284b-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1284b-105">El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar <STRONG>Get-CsBackupServiceStatus</STRONG> de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1284b-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="1284b-106">Para usar este cmdlet, inicie sesión como miembro de este grupo.</span><span class="sxs-lookup"><span data-stu-id="1284b-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="1284b-107">O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el uso del cmdlet <STRONG>Set-CsBackupServiceConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1284b-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="1284b-108">Para ver la configuración del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1284b-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="1284b-109">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1284b-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="1284b-110">El valor predeterminado de SyncInterval es de dos minutos.</span><span class="sxs-lookup"><span data-stu-id="1284b-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="1284b-111">Para establecer el intervalo de sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1284b-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="1284b-112">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1284b-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="1284b-113">Por ejemplo, lo siguiente establece el intervalo en tres minutos.</span><span class="sxs-lookup"><span data-stu-id="1284b-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1284b-114">Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado para el servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, puesto que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y en el objetivo del punto de recuperación (RPO).</span><span class="sxs-lookup"><span data-stu-id="1284b-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="1284b-115">Para obtener el estado del servicio de copia de seguridad para un determinado grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="1284b-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="1284b-116">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1284b-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="1284b-117">El estado de la sincronización del servicio de copia de seguridad se define unidireccionalmente desde un grupo de servidores (P1) hasta su grupo de servidores de copia de seguridad (P2).</span><span class="sxs-lookup"><span data-stu-id="1284b-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="1284b-118">El estado de sincronización de P1 a P2 puede ser diferente que el de P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="1284b-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="1284b-119">Para P1 a P2, el servicio de copia de seguridad está en un estado "constante" si todos los cambios realizados en P1 se replican completamente sobre P2 dentro del intervalo de sincronización.</span><span class="sxs-lookup"><span data-stu-id="1284b-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="1284b-120">Está en el estado "final" si no hay ningún cambio más que se vaya a sincronizar de P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="1284b-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="1284b-121">Ambos estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1284b-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="1284b-122">Esto no implica que el estado devuelto permanezca tal cual después.</span><span class="sxs-lookup"><span data-stu-id="1284b-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="1284b-123">En particular, el estado "final" continuará manteniéndose solo si P1 no genera ningún cambio después de que se ejecute el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1284b-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="1284b-124">Esto es cierto en caso de que se produzca un error de P1 sobre P2 después de que P1 se sitúe en el modo de solo lectura como parte de la lógica de ejecución de <STRONG>Invoke-CsPoolfailover</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1284b-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="1284b-125">Para obtener información acerca de la relación de copia de seguridad de un determinado grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="1284b-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="1284b-126">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1284b-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="1284b-127">Para forzar una sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1284b-127">To force a Backup Service sync</span></span>

<span data-ttu-id="1284b-128">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1284b-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

