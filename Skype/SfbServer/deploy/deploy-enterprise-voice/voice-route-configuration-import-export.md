---
title: Exportar o importar un archivo de configuración de ruta de voz de Skype para la empresa
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server mediante el uso de la Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 8f0d8f4e221cbe23ac37c4126a9d26aac46e6d53
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222475"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="f2b55-103">Exportar o importar un archivo de configuración de ruta de voz de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="f2b55-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="f2b55-104">**Resumen:** Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server mediante el uso de la Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f2b55-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="f2b55-105">Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para guardar y recuperar una instantánea de la configuración del enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="f2b55-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="f2b55-106">Al importar un archivo de configuración enrutamiento de voz (.vcfg), pero los cambios se han realizado la voz configuración de enrutamiento en el servidor mientras tanto, las páginas en el grupo de **Enrutamiento de voz** de Skype para el Panel de Control de servidor empresarial que le indicará no existe son los cambios no confirmados en enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="f2b55-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="f2b55-107">Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.</span><span class="sxs-lookup"><span data-stu-id="f2b55-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="f2b55-108">Si ha realizado los cambios no confirmados en la configuración de cualquier página dentro del grupo, los cambios se guardan en el archivo de configuración de voz exportado (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="f2b55-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="f2b55-109">Esto le permite realizar cambios en la configuración de enrutamiento durante varias sesiones antes de publicar los cambios de voz.</span><span class="sxs-lookup"><span data-stu-id="f2b55-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="f2b55-110">Para exportar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="f2b55-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="f2b55-111">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f2b55-112">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f2b55-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f2b55-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f2b55-114">En el menú **Acciones**, haga clic en **Exportar configuración**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="f2b55-115">Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="f2b55-116">Para importar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="f2b55-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="f2b55-117">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f2b55-118">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f2b55-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f2b55-119">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f2b55-120">En el menú **Acciones**, haga clic en **Importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="f2b55-121">Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="f2b55-122">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="f2b55-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2b55-123">Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2b55-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="f2b55-124">Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="f2b55-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

