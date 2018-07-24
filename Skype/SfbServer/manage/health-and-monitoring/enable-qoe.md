---
title: Habilitar la calidad de la experiencia en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumen: Obtenga información sobre cómo habilitar la calidad de la experiencia (QoE) en Skype para Business Server.'
ms.openlocfilehash: 37775223016a463fc7f090f82163fbf8271cd050
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993204"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="5fe29-103">Habilitar la calidad de la experiencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5fe29-103">Enable Quality of Experience in Skype for Business Server</span></span>
 
<span data-ttu-id="5fe29-104">**Resumen:** Obtenga información sobre cómo habilitar la calidad de la experiencia (QoE) en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5fe29-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>
  
<span data-ttu-id="5fe29-105">La calidad de la experiencia (QoE) registra datos numéricos que indican la calidad de los medios e información sobre los participantes, nombres de los dispositivos, controladores, direcciones IP y tipos de extremos que se usan en las llamadas y las sesiones.</span><span class="sxs-lookup"><span data-stu-id="5fe29-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="5fe29-106">Para obtener información detallada, consulte [Planning for supervisión](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="5fe29-106">For details, see [Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>
  
<span data-ttu-id="5fe29-107">Para habilitar QoE en toda la organización o en cada uno de sus sitios, realice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fe29-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fe29-108">Para habilitar QoE, en primer lugar necesita instalar el Servidor de supervisión y conectarlo a una base de datos back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5fe29-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="5fe29-109">Para obtener información detallada, vea [Implementación de supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fe29-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5fe29-110">Para habilitar QoE mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="5fe29-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5fe29-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="5fe29-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="5fe29-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="5fe29-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5fe29-113">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="5fe29-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span> 
    
4. <span data-ttu-id="5fe29-114">En la página **Datos de calidad de la experiencia**, haga clic en la colección adecuada de la tabla, en **Acción** y en **Habilitar QoE**.</span><span class="sxs-lookup"><span data-stu-id="5fe29-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5fe29-115">Habilitar QoE mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fe29-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5fe29-116">Puede habilitar QoE mediante Windows PowerShell y el cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5fe29-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="5fe29-117">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fe29-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5fe29-118">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="5fe29-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5fe29-119">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5fe29-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="5fe29-120">Para habilitar QoE para una sola ubicación:</span><span class="sxs-lookup"><span data-stu-id="5fe29-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="5fe29-121">Para habilitar QoE, defina el parámetro EnableQoE en True ($True).</span><span class="sxs-lookup"><span data-stu-id="5fe29-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="5fe29-122">Para deshabilitar QoE para una ubicación única:</span><span class="sxs-lookup"><span data-stu-id="5fe29-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="5fe29-p104">Para deshabilitar QoE, establezca el parámetro EnableQoE en False ($False). Así no se desinstala la supervisión. Se detiene la recopilación y el almacenaje de los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="5fe29-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="5fe29-126">Para habilitar QoE en varias ubicaciones con un comando único:</span><span class="sxs-lookup"><span data-stu-id="5fe29-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="5fe29-127">Este comando habilita QoE para todos los valores de configuración de QoE que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="5fe29-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="5fe29-128">Para obtener información detallada, consulte [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5fe29-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5fe29-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fe29-129">See also</span></span>

[<span data-ttu-id="5fe29-130">Planeación de la supervisión</span><span class="sxs-lookup"><span data-stu-id="5fe29-130">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="5fe29-131">Implementación de la supervisión</span><span class="sxs-lookup"><span data-stu-id="5fe29-131">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

