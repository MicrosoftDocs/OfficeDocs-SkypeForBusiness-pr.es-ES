---
title: Ver directivas de conferencia en Skype empresarial Server
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumen: Aprenda a ver directivas de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 2273e694ce2f34c8d395f87f207de85b409e18af
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818451"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="6a23a-103">Ver directivas de conferencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6a23a-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6a23a-104">**Resumen:** Obtenga información sobre cómo ver directivas de conferencia en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6a23a-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="6a23a-105">Puede ver las directivas de conferencia con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6a23a-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6a23a-106">Ver directivas de conferencia con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6a23a-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6a23a-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="6a23a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6a23a-108">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6a23a-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6a23a-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="6a23a-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="6a23a-110">En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.</span><span class="sxs-lookup"><span data-stu-id="6a23a-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="6a23a-111">En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="6a23a-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="6a23a-112">\*\*Editar Directiva de conferencia \<:\> \*\* se abre la Directiva y se muestra la configuración de la Directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6a23a-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="6a23a-113">Para obtener más información sobre cómo configurar las opciones, consulte [crear directivas de conferencia en Skype empresarial Server](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6a23a-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6a23a-114">Ver directivas de conferencia con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6a23a-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6a23a-115">Para ver las directivas de conferencia, use el cmdlet **Get-CsConferencingPolicy**:</span><span class="sxs-lookup"><span data-stu-id="6a23a-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="6a23a-116">El cmdlet devuelve información como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a23a-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

<span data-ttu-id="6a23a-117">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, vea [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6a23a-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

