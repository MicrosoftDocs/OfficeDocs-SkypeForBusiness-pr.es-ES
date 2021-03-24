---
title: Habilitar la calidad de la experiencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Summary: learn how to enable Quality of Experience (QoE) in Skype for Business Server.'
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095214"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="4f178-103">Habilitar la calidad de la experiencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4f178-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="4f178-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4f178-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="4f178-105">La calidad de la experiencia (QoE) registra datos numéricos que indican la calidad de los medios e información sobre los participantes, nombres de los dispositivos, controladores, direcciones IP y tipos de extremos que se usan en las llamadas y las sesiones.</span><span class="sxs-lookup"><span data-stu-id="4f178-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="4f178-106">Para más información, consulte [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="4f178-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="4f178-107">Para habilitar QoE en toda la organización o en cada uno de sus sitios, realice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="4f178-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="4f178-108">Para habilitar QoE, en primer lugar debe instalar el Servidor de supervisión y conectarlo a una base de datos back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4f178-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="4f178-109">Para más información, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="4f178-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4f178-110">Para habilitar QoE mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4f178-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4f178-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4f178-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="4f178-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4f178-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="4f178-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y en **Datos de calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="4f178-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="4f178-114">En la página **Datos de calidad de la experiencia**, haga clic en la colección adecuada de la tabla, en **Acción** y en **Habilitar QoE**.</span><span class="sxs-lookup"><span data-stu-id="4f178-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4f178-115">Habilitar QoE mediante el uso Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="4f178-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4f178-116">Puede habilitar QoE mediante Windows PowerShell y el cmdlet **Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="4f178-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="4f178-117">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f178-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4f178-118">Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="4f178-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4f178-119">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4f178-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="4f178-120">Para habilitar QoE para una sola ubicación:</span><span class="sxs-lookup"><span data-stu-id="4f178-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="4f178-121">Para habilitar QoE, defina el parámetro EnableQoE en True ($True).</span><span class="sxs-lookup"><span data-stu-id="4f178-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="4f178-122">Para deshabilitar QoE para una ubicación única:</span><span class="sxs-lookup"><span data-stu-id="4f178-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="4f178-p104">Para deshabilitar QoE, establezca el parámetro EnableQoE en False ($False). Así no se desinstala la supervisión. Se detiene la recopilación y el almacenaje de los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="4f178-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="4f178-126">Para habilitar QoE en varias ubicaciones con un comando único:</span><span class="sxs-lookup"><span data-stu-id="4f178-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="4f178-127">Este comando habilita QoE para todos los valores de configuración de QoE que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="4f178-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="4f178-128">Para obtener más información, [vea Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4f178-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f178-129">Ver también</span><span class="sxs-lookup"><span data-stu-id="4f178-129">See also</span></span>

[<span data-ttu-id="4f178-130">Planeación de la supervisión</span><span class="sxs-lookup"><span data-stu-id="4f178-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="4f178-131">Implementación de supervisión</span><span class="sxs-lookup"><span data-stu-id="4f178-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)