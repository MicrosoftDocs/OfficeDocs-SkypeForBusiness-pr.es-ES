---
title: Exportar o importar un archivo de configuración de la ruta de voz en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: Aprenda a exportar o importar un archivo de configuración de enrutamiento de voz en Skype empresarial Server mediante el panel de control de Skype empresarial Server.'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239918"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="8d5ea-103">Exportar o importar un archivo de configuración de la ruta de voz en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="8d5ea-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="8d5ea-104">**Resumen:** Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz en Skype empresarial Server mediante el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8d5ea-105">Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para guardar y recuperar una instantánea de la configuración del enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="8d5ea-106">Al importar un archivo de configuración de enrutamiento de voz (. vcfg), pero se han realizado cambios en la configuración de enrutamiento de voz en el servidor mientras tanto, las páginas del grupo de **enrutamiento de voz** en el panel de control de Skype empresarial Server indicarán que son cambios no confirmados en el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="8d5ea-107">Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="8d5ea-108">Si ha realizado cambios no confirmados en la configuración de cualquier página del grupo, los cambios se guardan en el archivo de configuración de voz exportado (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="8d5ea-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="8d5ea-109">Esto le permite realizar cambios en la configuración del enrutamiento de voz durante varias sesiones antes de publicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="8d5ea-110">Para exportar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="8d5ea-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="8d5ea-111">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8d5ea-112">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8d5ea-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8d5ea-114">En el menú **Acciones**, haga clic en **Exportar configuración**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="8d5ea-115">Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="8d5ea-116">Para importar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="8d5ea-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="8d5ea-117">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8d5ea-118">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8d5ea-119">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8d5ea-120">En el menú **Acciones**, haga clic en **Importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="8d5ea-121">Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="8d5ea-122">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8d5ea-123">Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="8d5ea-124">Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="8d5ea-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

