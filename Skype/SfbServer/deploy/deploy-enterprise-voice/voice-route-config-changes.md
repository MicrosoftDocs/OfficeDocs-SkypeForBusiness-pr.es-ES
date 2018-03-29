---
title: Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumen: Conozca cómo revisar, publicar o cancelar los cambios de configuración enrutamiento de voz de Skype para Business Server 2015 utilizando el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 4ad92cce54da403674e5da25052fd55681fd0627
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business-2015"></a><span data-ttu-id="d54c9-103">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="d54c9-103">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>
 
<span data-ttu-id="d54c9-104">**Resumen:** Aprenda a revisar, publicar o cancelar los cambios de configuración enrutamiento de voz de Skype para Business Server 2015 utilizando el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="d54c9-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="d54c9-105">Después de realizar cambios en cualquiera de las opciones de configuración de las páginas del grupo **Enrutamiento de voz**, siga este procedimiento para revisar, publicar o cancelar los cambios pendientes.</span><span class="sxs-lookup"><span data-stu-id="d54c9-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d54c9-106">Compruebe que solo modifica las opciones de configuración de Enrutamiento de voz un usuario cada vez.</span><span class="sxs-lookup"><span data-stu-id="d54c9-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d54c9-p101">Todos los cambios pendientes deben publicarse al mismo tiempo, ejecutando el comando **Confirmar todo**. No se pueden publicar los cambios pendientes de forma selectiva. Antes de publicar los cambios pendientes, ejecute el comando **Revisar cambios sin confirmar** y cancele los cambios de configuración que no desee publicar.</span><span class="sxs-lookup"><span data-stu-id="d54c9-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d54c9-110">Si sale de las páginas del grupo **Enrutamiento de voz** de confirmar los cambios pendientes, se perderán todos los cambios pendientes.</span><span class="sxs-lookup"><span data-stu-id="d54c9-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="d54c9-111">No obstante, puede exportar la configuración actual (incluidos los cambios pendientes) a un archivo de configuración de voz y, a continuación, importar y publicar la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="d54c9-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="d54c9-112">Para obtener más información, vea [exportar o importar un archivo de configuración de ruta de voz de Skype para negocios 2015](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="d54c9-112">For details, see [Export or import a voice route configuration file in Skype for Business 2015](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="d54c9-113">Para revisar, publicar o cancelar cambios de configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="d54c9-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="d54c9-114">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="d54c9-115">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="d54c9-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d54c9-116">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="d54c9-117">Realice los cambios de configuración que desee en las opciones de cada página del grupo **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="d54c9-118">Para revisar los cambios pendientes sin publicarlos, seleccione **Revisar cambios sin confirmar** en el menú **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="d54c9-119">Si desea cancelar alguno de los cambios pendientes, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d54c9-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="d54c9-120">Seleccione **Cancelar todos los cambios sin confirmar** en el menú **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="d54c9-121">Navegue hasta la pestaña de la página de **Enrutamiento de voz** que tiene los cambios pendientes que desea cancelar, seleccione el elemento con cambios pendientes, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar cambios seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="d54c9-122">Después de revisar todos los cambios pendientes y cancelar los que no desee publicar, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="d54c9-123">En el cuadro de diálogo **Configuración de voz no confirmada**, que muestra una lista de todos los cambios pendientes, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d54c9-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="d54c9-124">Cuando Skype para Panel de Control de servidor de empresa ha comprometido los cambios, aparecerá el mensaje **publicado correctamente la configuración de enrutamiento de voz** .</span><span class="sxs-lookup"><span data-stu-id="d54c9-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

