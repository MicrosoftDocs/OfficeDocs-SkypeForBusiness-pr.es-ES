---
title: Exportar o importar un archivo de configuración de enrutamiento de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: Conozca cómo exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server 2015 mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 8b676ac6417c172402c231401ea9284fccbb8d97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a><span data-ttu-id="57c2f-103">Exportar o importar un archivo de configuración de enrutamiento de voz en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="57c2f-103">Export or import a voice route configuration file in Skype for Business 2015</span></span>
 
<span data-ttu-id="57c2f-104">**Resumen:** Aprenda a exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server 2015 mediante el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="57c2f-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="57c2f-105">Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para guardar y recuperar una instantánea de la configuración del enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="57c2f-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="57c2f-106">Cuando importa un archivo de configuración de enrutamiento voz (.vcfg), pero los cambios realizados a la voz configuración de enrutamiento en el servidor mientras tanto, las páginas en el grupo de **Enrutamiento de voz** de Skype para el Panel de Control de servidor de negocios indicará existe son cambios no confirmados para el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="57c2f-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="57c2f-107">Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.</span><span class="sxs-lookup"><span data-stu-id="57c2f-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="57c2f-108">Si los cambios no confirmados realizados en la configuración de cualquier página dentro del grupo, los cambios se guardan en el archivo de configuración exportado voz (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="57c2f-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="57c2f-109">Esto permite realizar cambios en la configuración de enrutamiento durante varias sesiones antes de publicar los cambios de voz.</span><span class="sxs-lookup"><span data-stu-id="57c2f-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="57c2f-110">Para exportar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="57c2f-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="57c2f-111">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="57c2f-112">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="57c2f-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="57c2f-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="57c2f-114">En el menú **Acciones**, haga clic en **Exportar configuración**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="57c2f-115">Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="57c2f-116">Para importar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="57c2f-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="57c2f-117">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="57c2f-118">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="57c2f-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="57c2f-119">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="57c2f-120">En el menú **Acciones**, haga clic en **Importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="57c2f-121">Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="57c2f-122">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57c2f-123">Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="57c2f-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="57c2f-124">Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="57c2f-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

