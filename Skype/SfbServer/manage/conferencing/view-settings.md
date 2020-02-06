---
title: Ver la configuración de la reunión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumen: Obtenga información sobre cómo ver la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818461"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1ed1f-103">Ver la configuración de la reunión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1ed1f-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1ed1f-104">**Resumen:** Obtenga información sobre cómo ver la configuración de la reunión en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="1ed1f-105">Puede ver la configuración de la reunión con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1ed1f-106">Ver la configuración de la reunión con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1ed1f-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="1ed1f-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="1ed1f-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="1ed1f-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1ed1f-109">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1ed1f-110">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="1ed1f-111">En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="1ed1f-112">En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="1ed1f-113">**Editar la configuración de \<la\> reunión:** se abre la Directiva que muestra la configuración de la Directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1ed1f-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="1ed1f-114">Para obtener más información sobre cómo configurar las opciones, consulte [crear opciones de configuración de reunión en Skype empresarial Server](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1ed1f-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1ed1f-115">Ver la configuración de la reunión mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1ed1f-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="1ed1f-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="1ed1f-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="1ed1f-117">Para ver información sobre todas las configuraciones de reuniones, use el cmdlet **Get-CsMeetingConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="1ed1f-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="1ed1f-118">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ed1f-118">This command will return information similar to the following:</span></span>
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

<span data-ttu-id="1ed1f-119">Para obtener más información, incluida una lista completa de parámetros, vea [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1ed1f-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

