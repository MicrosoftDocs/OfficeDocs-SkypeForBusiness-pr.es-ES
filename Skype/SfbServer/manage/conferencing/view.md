---
title: Ver directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumen: Conozca cómo ver las directivas de la conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: 4d91a04456f7c9d877e58caed1d576edc0f80b41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="fd91e-103">Ver directivas de conferencia en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd91e-103">View conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fd91e-104">**Resumen:** Aprenda a ver las directivas de la conferencia de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fd91e-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fd91e-105">Puede ver las directivas de la conferencia utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="fd91e-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fd91e-106">Ver directivas de conferencia utilizando Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="fd91e-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="fd91e-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="fd91e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="fd91e-108">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="fd91e-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fd91e-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="fd91e-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="fd91e-110">En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.</span><span class="sxs-lookup"><span data-stu-id="fd91e-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="fd91e-111">En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="fd91e-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="fd91e-112">**Editar directiva de conferencia - \<directiva\> ** se abre mostrando la configuración para la directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fd91e-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="fd91e-113">Para obtener más información acerca de cómo configurar las opciones, consulte [crear directivas de conferencia en Skype para Business Server 2015](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fd91e-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server 2015](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fd91e-114">Ver directivas de conferencia utilizando Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="fd91e-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="fd91e-115">Para ver las directivas de conferencia, use el cmdlet **Get-CsConferencingPolicy**:</span><span class="sxs-lookup"><span data-stu-id="fd91e-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="fd91e-116">El cmdlet devuelve información como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd91e-116">The cmdlet returns information such as the following:</span></span>
  
```
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

```

<span data-ttu-id="fd91e-117">Para obtener más información, incluida una descripción de la sintaxis completa y lista de parámetros, vea [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fd91e-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

