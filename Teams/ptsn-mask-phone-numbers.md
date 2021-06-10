---
title: Enmascarar números de teléfono en Microsoft Teams reuniones
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo enmascarar números de teléfono Microsoft Teams reuniones
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117718"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="7be47-103">Enmascarar números de teléfono en Microsoft Teams reuniones</span><span class="sxs-lookup"><span data-stu-id="7be47-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="7be47-104">Para mayor privacidad, los números de teléfono de los participantes que se marcan en una reunión de Teams mediante audioconferencia se muestran por completo a los participantes internos.</span><span class="sxs-lookup"><span data-stu-id="7be47-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="7be47-105">Los números se enmascaran de los participantes fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="7be47-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="7be47-106">Esta configuración es la predeterminada para todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="7be47-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="7be47-107">El número enmascarado se muestra como se muestra en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="7be47-107">The masked number is displayed as shown in the following image:</span></span>

![un ejemplo de un número de teléfono enmascarado](media/hiddenPhoneNum.png)

<span data-ttu-id="7be47-109">Para casos de uso específicos del sector, los administradores tienen la capacidad de elegir cómo aparecen los números de teléfono de los participantes de las audioconferencias en las reuniones que están organizadas en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="7be47-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="7be47-110">Los administradores pueden elegir entre tres opciones:</span><span class="sxs-lookup"><span data-stu-id="7be47-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="7be47-111">Teléfono los números se enmascaran solo de los participantes externos.</span><span class="sxs-lookup"><span data-stu-id="7be47-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="7be47-112">Los participantes que pertenecen al inquilino del organizador de la reunión siguen teniendo el número de teléfono completo.</span><span class="sxs-lookup"><span data-stu-id="7be47-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="7be47-113">Teléfono los números se enmascaran de todos los usuarios de la reunión, excepto el organizador.</span><span class="sxs-lookup"><span data-stu-id="7be47-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="7be47-114">Teléfono números están desenmascarados, lo que los hace visibles para todos los usuarios de la reunión.</span><span class="sxs-lookup"><span data-stu-id="7be47-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="7be47-115">Esta configuración se aplica a todas las superficies de la reunión donde se exponen los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="7be47-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="7be47-116">Usar Microsoft PowerShell para establecer el enmascaramiento de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="7be47-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="7be47-117">Para cambiar la configuración de enmascaramiento de red telefónica conmutada (RTC), establezca el parámetro del **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en una de las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="7be47-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="7be47-118">Para enmascarar los números de teléfono solo de participantes externos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7be47-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="7be47-119">Para enmascarar los números de teléfono de todos los participantes de la reunión (excepto el organizador), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7be47-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="7be47-120">Para deshabilitar el enmascaramiento de números de teléfono, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7be47-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```