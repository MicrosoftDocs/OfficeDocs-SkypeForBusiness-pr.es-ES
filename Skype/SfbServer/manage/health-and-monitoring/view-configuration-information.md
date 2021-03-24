---
title: Ver información de configuración de CDR en Skype Empresarial Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Summary: Learn how to use Call Detail Recording (CDR) in Skype for Business Server.'
ms.openlocfilehash: fb832a3e0fcde7500b0516fb9a9672ab228d47ae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098906"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="c8122-103">Ver información de configuración de CDR en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c8122-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="c8122-104">**Resumen:** Obtenga información sobre cómo usar la grabación de detalles de llamadas (CDR) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c8122-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="c8122-p101">El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c8122-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="c8122-107">Al instalar Skype Empresarial Server, se crea una única colección global de opciones de configuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="c8122-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="c8122-108">Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="c8122-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="c8122-109">Puede ver las opciones de configuración de CDR que se usan en su organización mediante el Panel de control de Skype Empresarial Server o el cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c8122-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c8122-110">Para ver la información de configuración de CDR mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c8122-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c8122-111">En el Panel de control de Skype Empresarial Server, haga clic **en Supervisión y archivado.**</span><span class="sxs-lookup"><span data-stu-id="c8122-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="c8122-p103">En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c8122-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8122-115">Visualización de información de configuración de CDR mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="c8122-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c8122-116">Puede ver las opciones de configuración de CDR mediante Windows PowerShell y el cmdlet Get-CsCdrConfiguration cdr.</span><span class="sxs-lookup"><span data-stu-id="c8122-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="c8122-117">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8122-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8122-118">Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="c8122-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c8122-119">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c8122-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="c8122-120">Para ver la información de configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="c8122-120">To view CDR configuration information</span></span>

- <span data-ttu-id="c8122-121">Para ver información sobre todas las opciones de configuración de CDR, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="c8122-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="c8122-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8122-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="c8122-123">Para obtener más información, vea el tema de ayuda del cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c8122-123">For more information, see the help topic for the [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
