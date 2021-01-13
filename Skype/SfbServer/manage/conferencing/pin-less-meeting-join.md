---
title: Configurar la participación en reuniones sin PIN en Skype Empresarial Server
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
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumen: obtenga información sobre cómo configurar la opción de participación en reuniones sin PIN en Skype Empresarial Server.'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827990"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="65b03-103">Configurar la participación en reuniones sin PIN en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65b03-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="65b03-104">**Resumen:** Obtenga información sobre cómo configurar la opción de participación en reuniones sin PIN en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="65b03-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="65b03-105">Cuando un autor de llamada de acceso telefónico intenta unirse a una reunión, el servicio de Operador automático de conferencia (CAA) coloca al autor de la llamada en un lápiz en espera que es diferente de la sala de espera &#x2014; si un moderador no está en una llamada y el autor de la llamada de acceso telefónico no ha escrito un PIN de líder.</span><span class="sxs-lookup"><span data-stu-id="65b03-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="65b03-106">La opción de unirse a una reunión sin PIN permite que los autores de llamadas de acceso telefónico se unan a una reunión sin escribir un PIN de líder, incluso si son la primera persona en una llamada.</span><span class="sxs-lookup"><span data-stu-id="65b03-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="65b03-107">Tenga en cuenta lo siguiente al configurar esta característica:</span><span class="sxs-lookup"><span data-stu-id="65b03-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="65b03-108">Solo se aplica a reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="65b03-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="65b03-109">Permite a los autores de llamadas RTC permanecer en reuniones privadas sin la presencia de usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="65b03-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="65b03-110">Después de cambiar la configuración, se aplica a todas las reuniones privadas existentes y nuevas.</span><span class="sxs-lookup"><span data-stu-id="65b03-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="65b03-111">Se puede habilitar en el sitio del organizador o en el nivel global.</span><span class="sxs-lookup"><span data-stu-id="65b03-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="65b03-112">Las opciones para quién puede omitir la sala de espera se pueden establecer para cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="65b03-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="65b03-113">**Cualquier persona de mi organización con autores de llamadas se mete directamente**</span><span class="sxs-lookup"><span data-stu-id="65b03-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="65b03-114">**Cualquiera (sin restricciones) con** autores de llamadas se mete directamente (esta es la configuración predeterminada).</span><span class="sxs-lookup"><span data-stu-id="65b03-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="65b03-115">Cuando se configura para habilitar la unión sin PIN, el servicio caa sigue solicitando un PIN de líder.</span><span class="sxs-lookup"><span data-stu-id="65b03-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="65b03-116">Los usuarios pueden unirse a la reunión independientemente de si se introduce o no un PIN.</span><span class="sxs-lookup"><span data-stu-id="65b03-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="65b03-117">Sin embargo, conservar la capacidad de especificar un PIN de líder permite que el autor de la llamada de acceso telefónico se autentique como líder y administre la reunión si es necesario.</span><span class="sxs-lookup"><span data-stu-id="65b03-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="65b03-118">Configurar la participación en reuniones sin PIN</span><span class="sxs-lookup"><span data-stu-id="65b03-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="65b03-119">Para habilitar la unión a reuniones sin PIN para los usuarios, use el cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="65b03-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="65b03-120">Por ejemplo, el siguiente comando habilita la unión a reuniones sin PIN para el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="65b03-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="65b03-121">Por motivos de seguridad, cuando se ha activado la participación en reuniones sin PIN, es posible que desee restringir la salida de los usuarios anónimos asegurándose de que ConferencingPolicy esté establecido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="65b03-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="65b03-122">Para obtener más información, [vea Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="65b03-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

