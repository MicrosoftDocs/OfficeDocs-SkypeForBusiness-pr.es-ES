---
title: Configurar unión a la reunión sin PIN para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumen: Obtenga información sobre cómo configurar el PIN-menor opción de unión en Skype para Business Server de la reunión.'
ms.openlocfilehash: c865d234b58b29890957a2c895a91d84b9a31bb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888110"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="b6a81-103">Configurar unión a la reunión sin PIN para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b6a81-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="b6a81-104">**Resumen:** Obtenga información sobre cómo configurar el PIN-menor opción de unión en Skype para Business Server de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b6a81-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="b6a81-105">Cuando un autor de la llamada telefónico intenta unirse a una reunión, el servicio de operador automático de conferencia (CAA) coloca el autor de la llamada en una pluma de explotación que es diferente de la & de la sala de espera #x 2014; Si un moderador no está ya en una llamada y el autor de marcado en la llamada no ha entrado un responsable de PIN.</span><span class="sxs-lookup"><span data-stu-id="b6a81-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="b6a81-106">La opción de unión a una reunión sin PIN permite que los autores de llamadas de acceso telefónico local puedan unirse a una reunión sin indicar un PIN de líder incluso si son la primera persona en una llamada.</span><span class="sxs-lookup"><span data-stu-id="b6a81-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="b6a81-107">Tenga en cuenta lo siguiente al configurar esta característica:</span><span class="sxs-lookup"><span data-stu-id="b6a81-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="b6a81-108">Solo se aplica a reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="b6a81-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="b6a81-109">Permite que los autores de llamadas RTC permanezcan en reuniones privadas sin la presencia de usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="b6a81-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="b6a81-110">Después de cambiar la opción, se aplica a todas las reuniones privadas existentes y nuevas.</span><span class="sxs-lookup"><span data-stu-id="b6a81-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="b6a81-111">Puede activarse en el sitio del organizador o a nivel global.</span><span class="sxs-lookup"><span data-stu-id="b6a81-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="b6a81-112">Se pueden establecer opciones para personas que pueden omitir la sala de espera en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6a81-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="b6a81-113">**Cualquier persona de mi organización con autores de llamada entran directamente**</span><span class="sxs-lookup"><span data-stu-id="b6a81-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="b6a81-114">**Cualquier persona (sin restricciones) con autores de llamada entran directamente** (Este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b6a81-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="b6a81-115">Al configurar la habilitación de la unión sin pin, el servicio CAA solicitará un PIN de líder.</span><span class="sxs-lookup"><span data-stu-id="b6a81-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="b6a81-116">Los usuarios pueden unirse a la reunión dispongan o no del PIN.</span><span class="sxs-lookup"><span data-stu-id="b6a81-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="b6a81-117">Sin embargo, conservar la capacidad de escribir un PIN de coordinador permite que un llamador telefónico autenticar como coordinador y administrar la reunión si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b6a81-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="b6a81-118">Configurar la unión a reuniones sin PIN</span><span class="sxs-lookup"><span data-stu-id="b6a81-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="b6a81-119">Para habilitar la participación en la reunión de menor de PIN para los usuarios, utilice el cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b6a81-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="b6a81-120">Por ejemplo, el comando siguiente habilita la unión a reuniones sin PIN para el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="b6a81-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="b6a81-121">Por motivos de seguridad, cuando se activa la unión a reuniones sin PIN, es posible que quiera restringir que los usuarios anónimos accedan por aceptación de llamada asegurándose de que ConferencingPolicy está configurado de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b6a81-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="b6a81-122">Para obtener más información, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b6a81-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

