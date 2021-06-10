---
title: Teams de teclado de marcado
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar el teclado de marcado en el cliente Teams para que los usuarios puedan acceder a la funcionalidad de red telefónica conmutada (RTC).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012425"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="9fd3f-103">Configuración del teclado de marcado</span><span class="sxs-lookup"><span data-stu-id="9fd3f-103">Dial pad configuration</span></span>

<span data-ttu-id="9fd3f-104">En el Teams, el teclado de marcado permite a los usuarios acceder a la funcionalidad de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="9fd3f-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="9fd3f-105">El teclado de marcado está disponible para los usuarios con Sistema telefónico licencia, siempre que estén configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="9fd3f-106">Todos los criterios siguientes son necesarios para que el teclado de marcado se muestre:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="9fd3f-107">El usuario tiene una licencia Sistema telefónico ("MCOEV") habilitada</span><span class="sxs-lookup"><span data-stu-id="9fd3f-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="9fd3f-108">El usuario tiene Microsoft Calling Plan o está habilitado para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="9fd3f-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="9fd3f-109">El usuario Telefonía IP empresarial habilitado</span><span class="sxs-lookup"><span data-stu-id="9fd3f-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="9fd3f-110">El usuario se encuentra en línea y no en Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="9fd3f-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="9fd3f-111">El usuario ha Teams directiva de llamadas habilitada</span><span class="sxs-lookup"><span data-stu-id="9fd3f-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="9fd3f-112">En las secciones siguientes se describe cómo usar PowerShell para comprobar los criterios.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="9fd3f-113">En la mayoría de los casos, debe buscar varias propiedades en el resultado del cmdlet Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="9fd3f-114">Algunos ejemplos suponen $user es la dirección UPN o sip del usuario.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="9fd3f-115">El usuario tiene una licencia Sistema telefónico ("MCOEV") habilitada</span><span class="sxs-lookup"><span data-stu-id="9fd3f-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="9fd3f-116">Debe asegurarse de que el plan asignado para el usuario muestra el atributo **CapabilityStatus** establecido en Habilitado y el Plan de capacidad establecido en **MCOEV** (Sistema telefónico licencia).</span><span class="sxs-lookup"><span data-stu-id="9fd3f-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="9fd3f-117">Es posible que vea MCOEV, MCOEV1, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="9fd3f-118">Todos son aceptables, siempre y cuando el Plan de capacidad comience con MCOEV.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="9fd3f-119">Para comprobar que los atributos están configurados correctamente, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="9fd3f-120">El resultado tendrá el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-120">The output will look like the following.</span></span> <span data-ttu-id="9fd3f-121">Solo tiene que comprobar los atributos **CapabilityStatus** y **Capability Plan:**</span><span class="sxs-lookup"><span data-stu-id="9fd3f-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="9fd3f-122">El usuario tiene Microsoft Calling Plan O está habilitado para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="9fd3f-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="9fd3f-123">**Si el usuario tiene Microsoft Calling Plan,** debe asegurarse de que el atributo **CapabilityStatus** está establecido en Habilitado y de que el plan de capacidad se establece en **MCOPSTN.**</span><span class="sxs-lookup"><span data-stu-id="9fd3f-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="9fd3f-124">Es posible que vea MCOPSTN1, MCOPSTN2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="9fd3f-125">Todos son aceptables, siempre y cuando el Plan de capacidad comience con MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="9fd3f-126">Para comprobar los atributos, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="9fd3f-127">El resultado tendrá el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-127">The output will look like the following.</span></span> <span data-ttu-id="9fd3f-128">Solo tiene que comprobar los atributos **CapabilityStatus** y **Capability Plan:**</span><span class="sxs-lookup"><span data-stu-id="9fd3f-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="9fd3f-129">**Si el usuario está habilitado para enrutamiento** directo, se le debe asignar un valor no nulo para OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="9fd3f-130">Para comprobar el atributo, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="9fd3f-131">El resultado debe tener un valor no nulo, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="9fd3f-132">El usuario Telefonía IP empresarial habilitado</span><span class="sxs-lookup"><span data-stu-id="9fd3f-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="9fd3f-133">Para comprobar si el usuario Telefonía IP empresarial habilitado, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="9fd3f-134">El resultado debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="9fd3f-135">El usuario se encuentra en línea y no en Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="9fd3f-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="9fd3f-136">Para asegurarse de que el usuario se aloja en línea y no en Skype Empresarial local, registrarpool no debe ser nulo y el HostProvider debe contener un valor que comienza con "sipfed.online".</span><span class="sxs-lookup"><span data-stu-id="9fd3f-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="9fd3f-137">Para comprobar los valores, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="9fd3f-138">El resultado debe ser similar a:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="9fd3f-139">El usuario ha Teams directiva de llamadas habilitada</span><span class="sxs-lookup"><span data-stu-id="9fd3f-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="9fd3f-140">TeamsCallingPolicy efectivo del usuario debe tener AllowPrivateCalling establecido en true.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="9fd3f-141">De forma predeterminada, los usuarios heredan la directiva global, que tiene AllowPrivateCallingPolicy establecido en true de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="9fd3f-142">Para obtener TeamsCallingPolicy para un usuario y comprobar que AllowPrivateCalling está establecido en true, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="9fd3f-143">El resultado debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="9fd3f-144">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="9fd3f-144">Additional notes</span></span>

-   <span data-ttu-id="9fd3f-145">Es posible que deba reiniciar el Teams después de realizar cualquiera de estos cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="9fd3f-146">Si actualizó recientemente cualquiera de los criterios anteriores, es posible que tenga que esperar unas horas para que el cliente reciba la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="9fd3f-147">Si sigue sin ver el teclado de marcado, compruebe si hay un error de aprovisionamiento mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fd3f-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="9fd3f-148">Si han pasado más de 24 horas y sigues viendo problemas, ponte en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="9fd3f-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


