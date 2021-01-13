---
title: Ver las opciones de configuración de reuniones en Skype Empresarial Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumen: obtenga información sobre cómo ver las opciones de configuración de reuniones en Skype Empresarial Server.'
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827930"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1024b-103">Ver las opciones de configuración de reuniones en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1024b-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1024b-104">**Resumen:** Obtenga información sobre cómo ver las opciones de configuración de reuniones en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1024b-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="1024b-105">Puede ver las opciones de configuración de reuniones con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1024b-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1024b-106">Ver las opciones de configuración de reuniones mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1024b-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="1024b-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="1024b-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="1024b-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1024b-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1024b-109">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1024b-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1024b-110">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Configuración **de reunión.**</span><span class="sxs-lookup"><span data-stu-id="1024b-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="1024b-111">En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.</span><span class="sxs-lookup"><span data-stu-id="1024b-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="1024b-112">En **Editar filtro de archivos,** active la casilla **Mostrar** detalles.</span><span class="sxs-lookup"><span data-stu-id="1024b-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="1024b-113">**Editar configuración \<policy\> de reunión:** se abre mostrando la configuración de la directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1024b-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="1024b-114">Para obtener más información sobre cómo configurar las opciones, consulte Crear opciones de configuración de reuniones [en Skype Empresarial Server.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1024b-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1024b-115">Ver las opciones de configuración de reuniones mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1024b-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="1024b-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="1024b-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="1024b-117">Para ver información sobre todas las opciones de configuración de reuniones, use el cmdlet **Get-CsMeetingConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="1024b-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="1024b-118">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1024b-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="1024b-119">Para obtener más información, incluida una lista completa de parámetros, vea [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1024b-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

