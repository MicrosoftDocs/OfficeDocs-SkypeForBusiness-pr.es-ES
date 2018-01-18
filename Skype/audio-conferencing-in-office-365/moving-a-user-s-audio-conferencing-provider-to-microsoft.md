---
title: Mover el proveedor de conferencia de audio de un usuario a Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Cambie su Skype para usuarios profesionales de proveedores de conferencias de audio de terceros (ACP) a un proveedor de conferencia de acceso telefónico de Microsoft. "
ms.openlocfilehash: 79697299ce2c3e3fa398150cd300e305ef0c672a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="b5683-103">Mover el proveedor de conferencia de audio de un usuario a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5683-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="b5683-104">Para utilizar audioconferencia en Office 365 con Skype para empresas y Teams de Microsoft, los usuarios de la organización deben tener una licencia de **Conferencia de Audio** asignada a ellos y su proveedor de conferencia de audio deben establecerse a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5683-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="b5683-105">Vea [probar o comprar Audio conferencia en Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obtener más información sobre licencias y cuánto cuestan.</span><span class="sxs-lookup"><span data-stu-id="b5683-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="b5683-106">Para mover el proveedor de conferencia de audio de un usuario a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5683-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="b5683-107">Si una licencia de **Conferencia de Audio** se asigna a un usuario que no tiene un proveedor de conferencia de audio, proveedor del usuario se establecerá automáticamente en Microsoft y no tienes que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="b5683-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="b5683-108">Si el usuario ya tiene un proveedor de conferencia de audio, debe cambiar el proveedor del usuario a Microsoft después de la asignación de una licencia de **Conferencia de Audio** .</span><span class="sxs-lookup"><span data-stu-id="b5683-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="b5683-109">Para configurar Microsoft como el proveedor de conferencia de audio para un usuario que tiene una licencia de **Conferencia de Audio** asignado pero está utilizando otro proveedor de conferencia de audio, para ello:</span><span class="sxs-lookup"><span data-stu-id="b5683-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="b5683-110">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="b5683-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b5683-111">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="b5683-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b5683-112">En el **Skype para el centro de administración de negocios**, vaya a las **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="b5683-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="b5683-113">Si ve un titular le notifica que hay usuarios que tienen una **Conferencia de Audio** licencia asignada pero no tiene Microsoft establecer como su proveedor de conferencia de audio aún, haga clic en **haga clic aquí para moverlos**.</span><span class="sxs-lookup"><span data-stu-id="b5683-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="b5683-114">Si no ve la pancarta, en el **Skype para el centro de administración de negocios** , haga clic en **usuarios**y, a continuación, seleccione el filtro de **usuarios listos para moverlos a las conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="b5683-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="b5683-115">Seleccione los usuarios que desee mover y, a continuación, en el panel Acción, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b5683-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="b5683-116">Seleccione **Microsoft** en la lista **nombre de proveedor** .</span><span class="sxs-lookup"><span data-stu-id="b5683-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5683-117">Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft, cambiará la información de conferencia de audio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b5683-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="b5683-118">Si necesita mantener esta información, por favor grabarlo en algún lugar antes de cambiar el proveedor de cualquiera de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b5683-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="b5683-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b5683-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="b5683-120">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="b5683-120">What else should I know?</span></span>

- <span data-ttu-id="b5683-121">Si selecciona el usuario en la lista, puede ver la información de conferencia de audio predeterminada del usuario, pero no podrá ver la conferencia de audio PIN.</span><span class="sxs-lookup"><span data-stu-id="b5683-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="b5683-122">Puede restablecer el NIP de un usuario de conferencia de audio haciendo clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="b5683-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="b5683-123">Si desea cambiar la configuración de conferencia de audio de un usuario, puede seleccionar el usuario de la lista y haga clic en **Editar** y realice los cambios en la página de **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="b5683-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="b5683-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b5683-124">Related topics</span></span>

[<span data-ttu-id="b5683-125">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5683-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

