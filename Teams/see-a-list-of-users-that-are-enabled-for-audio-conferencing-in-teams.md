---
title: Ver una lista de los usuarios que están habilitados para conferencias de Audio en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo ver una lista de los usuarios de la organización que están habilitados para las conferencias de acceso telefónico desde dentro de Microsoft Teams. '
ms.openlocfilehash: 9bbdd5fd8536554c942db19c8c9f5ac41789c461
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884450"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="63c11-103">Ver una lista de los usuarios que están habilitados para conferencias de Audio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63c11-103">See a list of users that are enabled for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="63c11-104">Después de haber habilitado a los usuarios de Microsoft Teams en su organización para conferencias de Audio, puede ver la lista de los usuarios que han sido habilitados.</span><span class="sxs-lookup"><span data-stu-id="63c11-104">After you have enabled Microsoft Teams users in your organization for Audio Conferencing, you can view the list of those users who have been enabled.</span></span> <span data-ttu-id="63c11-105">Cuando examine la lista, también verá para cada usuario en la lista el tipo de proveedor de conferencias de audio que están usando, el número de teléfono de acceso telefónico predeterminada para el usuario, y si su organización no está habilitada para los identificadores de conferencia dinámico, la conferencia estática identificadores para las reuniones de conferencia de audio que organizan.</span><span class="sxs-lookup"><span data-stu-id="63c11-105">When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a><span data-ttu-id="63c11-106">Ver una lista de los usuarios</span><span class="sxs-lookup"><span data-stu-id="63c11-106">Viewing a list of users</span></span>

- <span data-ttu-id="63c11-107">En el panel de navegación izquierdo, haga clic en **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="63c11-107">In the left navigation, click **Users**.</span></span>


## <a name="what-else-should-i-know"></a><span data-ttu-id="63c11-108">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="63c11-108">What else should I know?</span></span>

- <span data-ttu-id="63c11-109">Al ver la lista de usuarios que están habilitadas, puede seleccionar un usuario de la lista para modificar la configuración de conferencia de audio para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="63c11-109">When you view the list of users that are enabled, you can select a user from the list to edit the audio conferencing settings for that user.</span></span>
    
- <span data-ttu-id="63c11-110">Cuando se selecciona un único usuario que está configurado para usar Microsoft como proveedor de conferencias de audio, puede ver el número de teléfono predeterminado y si la organización está habilitada para los identificadores de conferencia dinámico y puede restablecer el identificador de conferencia para las reuniones que el Organiza el usuario.</span><span class="sxs-lookup"><span data-stu-id="63c11-110">When you select a single user that is configured to use Microsoft as the audio conferencing provider, you can view the default phone number and whether your organization is enabled for dynamic conference IDs, and you can reset the conference ID for meetings that the user organizes.</span></span>
    
- <span data-ttu-id="63c11-111">Cuando se selecciona un único usuario al que está configurado para usar un proveedor de conferencia de audio de terceros, puede ver el nombre del proveedor de conferencias de audio, el número de teléfono de pago y el número de teléfono gratuito (si se configuran).</span><span class="sxs-lookup"><span data-stu-id="63c11-111">When you select a single user who is configured to use a third-party audio conferencing provider, you can view the name of the audio conferencing provider, the toll phone number, and the toll-free phone number (if they are set up).</span></span>
    
   
- <span data-ttu-id="63c11-112">Puede usar el botón Buscar para buscar un usuario individual en la lista.</span><span class="sxs-lookup"><span data-stu-id="63c11-112">You can use the search button to search for an individual user in the list.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="63c11-113">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="63c11-113">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="63c11-p102">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="63c11-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="63c11-117">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="63c11-117">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="63c11-118">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="63c11-118">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="63c11-119">Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="63c11-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="63c11-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="63c11-120">Related topics</span></span>

[<span data-ttu-id="63c11-121">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="63c11-121">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
