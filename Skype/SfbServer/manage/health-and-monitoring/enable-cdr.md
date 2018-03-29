---
title: Habilitar el registro detallado de llamadas en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumen: Conozca cómo habilitar detalle de llamadas (CDR) registros de grabación en Skype para Business Server 2015.'
ms.openlocfilehash: 3fe33f3cfde310b3674c125b7eb8ab1bf04f7c03
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-detail-recording-in-skype-for-business-server-2015"></a><span data-ttu-id="d2987-103">Habilitar el registro detallado de llamadas en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d2987-103">Enable call detail recording in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d2987-104">**Resumen:** Aprenda a Habilitar detalle de llamadas (CDR) registros de grabación en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d2987-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d2987-p101">El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.</span><span class="sxs-lookup"><span data-stu-id="d2987-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> 
  
<span data-ttu-id="d2987-107">Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="d2987-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2987-108">Para poder habilitar el CDR necesita configurar la supervisión y una base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d2987-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="d2987-109">Para obtener información detallada, vea [Implementación de supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="d2987-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="d2987-110">Habilitar CDR con Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="d2987-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d2987-111">Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d2987-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="d2987-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="d2987-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d2987-113">En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="d2987-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span> 
    
4. <span data-ttu-id="d2987-114">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, luego, haga clic en **Habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="d2987-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2987-115">CDR habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d2987-115">CDR is enabled by default.</span></span> 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d2987-116">Habilitación de CDR mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2987-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d2987-117">Puede habilitar a CDR mediante Windows PowerShell y el cmdlet **Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d2987-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d2987-118">Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2987-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d2987-119">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d2987-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d2987-120">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d2987-120">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="d2987-121">Para habilitar CDR para una única ubicación</span><span class="sxs-lookup"><span data-stu-id="d2987-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="d2987-122">Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).</span><span class="sxs-lookup"><span data-stu-id="d2987-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="d2987-123">Para deshabilitar CDR para una única ubicación</span><span class="sxs-lookup"><span data-stu-id="d2987-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="d2987-p104">Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False). Esto no desinstala la supervisión, sino que pausa la recopilación y el almacenamiento de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="d2987-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="d2987-127">Utilizar un único comando para habilitar CDR en varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="d2987-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="d2987-128">Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="d2987-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="d2987-129">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d2987-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2987-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2987-130">See also</span></span>

[<span data-ttu-id="d2987-131">Planeamiento para la supervisión</span><span class="sxs-lookup"><span data-stu-id="d2987-131">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="d2987-132">Implementación de la supervisión</span><span class="sxs-lookup"><span data-stu-id="d2987-132">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)