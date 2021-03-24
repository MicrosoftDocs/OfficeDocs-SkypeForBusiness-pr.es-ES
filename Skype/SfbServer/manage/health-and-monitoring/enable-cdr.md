---
title: Habilitar el registro detallado de llamadas en Skype Empresarial Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumen: obtenga información sobre cómo habilitar registros de registro detallado de llamadas (CDR) en Skype Empresarial Server.'
ms.openlocfilehash: e2f652eeef77c336fb34be07c123f1ef026d458c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095234"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="cdd07-103">Habilitar el registro detallado de llamadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cdd07-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="cdd07-104">**Resumen:** Obtenga información sobre cómo habilitar registros de registro detallado de llamadas (CDR) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdd07-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="cdd07-p101">El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.</span><span class="sxs-lookup"><span data-stu-id="cdd07-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="cdd07-107">Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="cdd07-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="cdd07-108">Para poder habilitar el CDR debe configurar la supervisión y una base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="cdd07-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="cdd07-109">Para obtener más información, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="cdd07-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="cdd07-110">Para habilitar CDR con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cdd07-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="cdd07-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdd07-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="cdd07-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdd07-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="cdd07-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, en **Registro detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="cdd07-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="cdd07-114">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, a continuación, haga clic en **Habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="cdd07-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cdd07-115">CDR habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cdd07-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cdd07-116">Habilitar CDR mediante el uso Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="cdd07-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cdd07-117">Puede habilitar CDR mediante Windows PowerShell y el cmdlet **Set-CsCdrConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="cdd07-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="cdd07-118">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdd07-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cdd07-119">Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="cdd07-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="cdd07-120">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdd07-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="cdd07-121">Para habilitar CDR para una única ubicación</span><span class="sxs-lookup"><span data-stu-id="cdd07-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="cdd07-122">Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).</span><span class="sxs-lookup"><span data-stu-id="cdd07-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="cdd07-123">Para deshabilitar CDR para una única ubicación</span><span class="sxs-lookup"><span data-stu-id="cdd07-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="cdd07-124">Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False).</span><span class="sxs-lookup"><span data-stu-id="cdd07-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="cdd07-125">Deshabilitar CDR no desinstala la supervisión.</span><span class="sxs-lookup"><span data-stu-id="cdd07-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="cdd07-126">Pausa la recopilación y el almacenamiento de datos CDR.</span><span class="sxs-lookup"><span data-stu-id="cdd07-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="cdd07-127">Utilizar un único comando para habilitar CDR en varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="cdd07-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="cdd07-128">Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="cdd07-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="cdd07-129">Para obtener más información, vea el tema de ayuda del cmdlet [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cdd07-129">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdd07-130">Ver también</span><span class="sxs-lookup"><span data-stu-id="cdd07-130">See also</span></span>

[<span data-ttu-id="cdd07-131">Planeación de la supervisión</span><span class="sxs-lookup"><span data-stu-id="cdd07-131">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="cdd07-132">Implementación de supervisión</span><span class="sxs-lookup"><span data-stu-id="cdd07-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)