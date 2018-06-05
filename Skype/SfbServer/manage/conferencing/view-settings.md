---
title: Ver opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumen: Obtenga información sobre cómo ver los valores de configuración de Skype para Business Server 2015 de la reunión.'
ms.openlocfilehash: 1af530732df37ed78e47ee5b5d5914c00fbbd4bf
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568727"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="7bab2-103">Ver opciones de configuración de reuniones en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7bab2-103">View meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7bab2-104">**Resumen:** Obtenga información sobre cómo ver los valores de configuración de Skype para Business Server 2015 de la reunión.</span><span class="sxs-lookup"><span data-stu-id="7bab2-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7bab2-105">Puede ver opciones de configuración de la reunión mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="7bab2-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7bab2-106">Ver opciones de configuración de la reunión mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="7bab2-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="7bab2-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="7bab2-107"></span></span>

1. <span data-ttu-id="7bab2-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7bab2-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7bab2-109">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="7bab2-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7bab2-110">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="7bab2-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="7bab2-111">En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.</span><span class="sxs-lookup"><span data-stu-id="7bab2-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="7bab2-112">En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7bab2-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="7bab2-113">**Editar configuración de reunión - \<directiva\> ** se abre mostrando la configuración para la directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7bab2-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="7bab2-114">Para obtener información detallada acerca de cómo configurar la configuración, vea [crear una configuración de reunión en Skype para Business Server 2015](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7bab2-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server 2015](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7bab2-115">Ver opciones de configuración de la reunión mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="7bab2-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="7bab2-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="7bab2-116"></span></span>

<span data-ttu-id="7bab2-117">Para ver información sobre todas las configuraciones de reuniones, use el cmdlet **Get-CsMeetingConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="7bab2-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="7bab2-118">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bab2-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="7bab2-119">Para obtener más información, incluida una lista completa de los parámetros, vea [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7bab2-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

