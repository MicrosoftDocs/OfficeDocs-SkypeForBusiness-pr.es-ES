---
title: Visualizar la información de configuración de CDR en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumen: Conozca cómo usar grabación de detalle llamar (CDR) en Skype para Business Server 2015.'
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a><span data-ttu-id="5d504-103">Visualizar la información de configuración de CDR en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d504-103">View CDR configuration information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d504-104">**Resumen:** Aprenda a usar grabación de detalle llamar (CDR) en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5d504-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5d504-p101">El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.</span><span class="sxs-lookup"><span data-stu-id="5d504-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="5d504-107">Al instalar Skype para Business Server 2015, una única colección global CDR de opciones de configuración se crea para usted.</span><span class="sxs-lookup"><span data-stu-id="5d504-107">When you install Skype for Business Server 2015, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="5d504-108">Los administradores también tienen la opción de crear colecciones de configuración personalizadas que se pueden aplicar a sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="5d504-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="5d504-109">Puede ver las opciones de configuración de CDR en uso en la organización mediante Skype para Panel de Control de servidor de negocios o el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5d504-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5d504-110">Para ver información de configuración de CDR mediante Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="5d504-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5d504-111">En Skype para Business Server Control Panel, haga clic en **supervisión y archivado**.</span><span class="sxs-lookup"><span data-stu-id="5d504-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="5d504-p103">En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5d504-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5d504-115">Ver la información de configuración de CDR mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d504-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5d504-116">Puede ver los valores de configuración de CDR mediante Windows PowerShell y el cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5d504-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="5d504-117">Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d504-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5d504-118">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="5d504-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5d504-119">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d504-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="5d504-120">Para ver la información de configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="5d504-120">To view CDR configuration information</span></span>

- <span data-ttu-id="5d504-121">Para ver información acerca de la configuración de configuración de CDR, escriba el comando siguiente en el Skype para negocios de Shell de administración de servidor y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="5d504-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="5d504-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d504-122">That will return information similar to this:</span></span>
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

<span data-ttu-id="5d504-123">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5d504-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

