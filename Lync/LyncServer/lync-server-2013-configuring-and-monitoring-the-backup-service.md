---
title: 'Lync Server 2013: Configurar y supervisar el servicio de copia de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="c3abf-102">Configurar y supervisar el servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3abf-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3abf-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3abf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c3abf-104">Puede usar los siguientes comandos de Shell de administración de Lync Server para configurar y supervisar el servicio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3abf-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3abf-105">El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar <STRONG>Get-CsBackupServiceStatus</STRONG> de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c3abf-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="c3abf-106">Para usar este cmdlet, inicia sesión como miembro de este grupo.</span><span class="sxs-lookup"><span data-stu-id="c3abf-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="c3abf-107">O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el cmdlet <STRONG>set-CsBackupServiceConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c3abf-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="c3abf-108">Para ver la configuración del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="c3abf-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="c3abf-109">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3abf-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="c3abf-110">El valor predeterminado de SyncInterval es de dos minutos.</span><span class="sxs-lookup"><span data-stu-id="c3abf-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="c3abf-111">Para establecer el intervalo de sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="c3abf-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="c3abf-112">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3abf-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="c3abf-113">Por ejemplo, la siguiente establece el intervalo en tres minutos.</span><span class="sxs-lookup"><span data-stu-id="c3abf-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3abf-114">Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado del servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, ya que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y el objetivo de punto de recuperación (RPO).</span><span class="sxs-lookup"><span data-stu-id="c3abf-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="c3abf-115">Para obtener el estado del servicio de copia de seguridad de un grupo en particular</span><span class="sxs-lookup"><span data-stu-id="c3abf-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="c3abf-116">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3abf-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="c3abf-117">El estado de sincronización del servicio de copia de seguridad se define de forma unidireccional desde un grupo (P1) a su grupo de copia de seguridad (P2).</span><span class="sxs-lookup"><span data-stu-id="c3abf-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="c3abf-118">El estado de sincronización de P1 a P2 puede ser diferente del de P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="c3abf-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="c3abf-119">Para P1 a P2, el servicio de copia de seguridad se encuentra en estado "estable" si todos los cambios realizados en P1 se replican por completo a P2 dentro del intervalo de sincronización.</span><span class="sxs-lookup"><span data-stu-id="c3abf-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="c3abf-120">Está en el estado "final" si no hay más cambios para sincronizar de P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="c3abf-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="c3abf-121">Ambos Estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3abf-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="c3abf-122">No implica que el estado devuelto permanecerá como está después.</span><span class="sxs-lookup"><span data-stu-id="c3abf-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="c3abf-123">En concreto, el estado "final" seguirá teniendo solo si P1 no genera ningún cambio después de que se ejecute el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3abf-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="c3abf-124">Esto es cierto en el caso de que se produzca un error P1 a través de la P2 después de poner P1 en modo de solo lectura como parte de la lógica de ejecución <STRONG>Invoke-CsPoolfailover</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c3abf-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="c3abf-125">Para obtener información sobre la relación de copia de seguridad de un grupo de servidores determinado</span><span class="sxs-lookup"><span data-stu-id="c3abf-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="c3abf-126">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3abf-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="c3abf-127">Para forzar la sincronización del servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="c3abf-127">To force a Backup Service sync</span></span>

<span data-ttu-id="c3abf-128">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3abf-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

