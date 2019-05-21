---
title: Configurar unión a la reunión sin PIN para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumen: Aprenda a configurar la opción de unión de reunión sin PIN en Skype empresarial Server.'
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280386"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="19026-103">Configurar unión a la reunión sin PIN para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="19026-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="19026-104">**Resumen:** Obtenga información sobre cómo configurar la opción de unión de reunión sin PIN en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="19026-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="19026-105">Cuando una persona que llama de acceso telefónico intenta unirse a una reunión, el servicio operador automático de la Conferencia (CAA) coloca al autor de la llamada en un lápiz que es diferente del de la sala de espera & # x2014; Si un moderador ya no está en una llamada, y la persona que llama no ha entrado en un PIN de relleno.</span><span class="sxs-lookup"><span data-stu-id="19026-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="19026-106">La opción de unión a una reunión sin PIN permite que los autores de llamadas de acceso telefónico local puedan unirse a una reunión sin indicar un PIN de líder incluso si son la primera persona en una llamada.</span><span class="sxs-lookup"><span data-stu-id="19026-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="19026-107">Tenga en cuenta lo siguiente al configurar esta característica:</span><span class="sxs-lookup"><span data-stu-id="19026-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="19026-108">Solo se aplica a reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="19026-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="19026-109">Permite que los autores de llamadas RTC permanezcan en reuniones privadas sin la presencia de usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="19026-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="19026-110">Después de cambiar la opción, se aplica a todas las reuniones privadas existentes y nuevas.</span><span class="sxs-lookup"><span data-stu-id="19026-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="19026-111">Puede activarse en el sitio del organizador o a nivel global.</span><span class="sxs-lookup"><span data-stu-id="19026-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="19026-112">Se pueden establecer opciones para personas que pueden omitir la sala de espera en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="19026-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="19026-113">**Cualquier persona de mi organización con autores de llamada entran directamente**</span><span class="sxs-lookup"><span data-stu-id="19026-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="19026-114">**Cualquier persona (sin restricciones) con autores de llamada entran directamente** (Este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="19026-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="19026-115">Al configurar la habilitación de la unión sin pin, el servicio CAA solicitará un PIN de líder.</span><span class="sxs-lookup"><span data-stu-id="19026-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="19026-116">Los usuarios pueden unirse a la reunión dispongan o no del PIN.</span><span class="sxs-lookup"><span data-stu-id="19026-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="19026-117">Sin embargo, mantener la posibilidad de introducir un PIN de relleno permite a una persona que llama de acceso telefónico autenticar como un líder y administrar la reunión si es necesario.</span><span class="sxs-lookup"><span data-stu-id="19026-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="19026-118">Configurar la unión a reuniones sin PIN</span><span class="sxs-lookup"><span data-stu-id="19026-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="19026-119">Para habilitar la combinación de reuniones sin PIN para los usuarios, use el cmdlet [set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="19026-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="19026-120">Por ejemplo, el comando siguiente habilita la unión a reuniones sin PIN para el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="19026-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="19026-121">Por motivos de seguridad, cuando se activa la unión a reuniones sin PIN, es posible que quiera restringir que los usuarios anónimos accedan por aceptación de llamada asegurándose de que ConferencingPolicy está configurado de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="19026-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="19026-122">Para obtener más información, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="19026-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

