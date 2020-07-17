---
title: Configuración del teclado de marcado de Teams
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
description: Obtenga más información sobre cómo configurar el teclado de marcado en el cliente de Teams para que los usuarios puedan acceder a la funcionalidad de red telefónica conmutada (RTC).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012425"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="cf129-103">Configuración del teclado de marcado</span><span class="sxs-lookup"><span data-stu-id="cf129-103">Dial pad configuration</span></span>

<span data-ttu-id="cf129-104">En el cliente de Teams, el teclado de marcado permite a los usuarios acceder a la funcionalidad de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="cf129-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="cf129-105">El teclado de marcado está disponible para los usuarios con una licencia de sistema telefónico, siempre que estén configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf129-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="cf129-106">Los siguientes criterios son necesarios para que el teclado de marcado se muestre:</span><span class="sxs-lookup"><span data-stu-id="cf129-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="cf129-107">El usuario tiene una licencia de sistema telefónico habilitado ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="cf129-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="cf129-108">El usuario tiene el plan de llamadas de Microsoft o está habilitado para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="cf129-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="cf129-109">El usuario tiene habilitada la telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="cf129-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="cf129-110">El usuario está conectado en línea y no en Skype empresarial local</span><span class="sxs-lookup"><span data-stu-id="cf129-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="cf129-111">El usuario tiene habilitada la Directiva de llamadas de Teams</span><span class="sxs-lookup"><span data-stu-id="cf129-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="cf129-112">En las siguientes secciones se describe cómo usar PowerShell para comprobar los criterios.</span><span class="sxs-lookup"><span data-stu-id="cf129-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="cf129-113">En la mayoría de los casos, tendrá que mirar varias propiedades en el resultado del cmdlet Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="cf129-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="cf129-114">Algunos ejemplos suponen que $user es la dirección de UPN o SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="cf129-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="cf129-115">El usuario tiene una licencia de sistema telefónico habilitado ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="cf129-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="cf129-116">Debe asegurarse de que el plan asignado para el usuario muestre el **atributo CapabilityStatus establecido en habilitado** y el **plan de capacidades establecido en MCOEV** (licencia de sistema telefónico).</span><span class="sxs-lookup"><span data-stu-id="cf129-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="cf129-117">Es posible que vea MCOEV, MCOEV1, etc.</span><span class="sxs-lookup"><span data-stu-id="cf129-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="cf129-118">Todas son aceptables, siempre y cuando el plan de capacidades comience con MCOEV.</span><span class="sxs-lookup"><span data-stu-id="cf129-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="cf129-119">Para comprobar que los atributos se han establecido correctamente, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="cf129-120">El resultado tendrá un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cf129-120">The output will look like the following.</span></span> <span data-ttu-id="cf129-121">Solo tiene que comprobar los atributos de **CapabilityStatus** y **plan de capacidad** :</span><span class="sxs-lookup"><span data-stu-id="cf129-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="cf129-122">El usuario tiene el plan de llamadas de Microsoft o está habilitado para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="cf129-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="cf129-123">**Si el usuario tiene un plan de llamadas de Microsoft**, debe asegurarse de que el **atributo CapabilityStatus se establece en habilitado**y de que el **plan de capacidad está establecido en MCOPSTN**.</span><span class="sxs-lookup"><span data-stu-id="cf129-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="cf129-124">Es posible que vea MCOPSTN1, MCOPSTN2, etc.</span><span class="sxs-lookup"><span data-stu-id="cf129-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="cf129-125">Todas son aceptables, siempre y cuando el plan de capacidades comience con MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="cf129-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="cf129-126">Para comprobar los atributos, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="cf129-127">El resultado tendrá un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cf129-127">The output will look like the following.</span></span> <span data-ttu-id="cf129-128">Solo tiene que comprobar los atributos de **CapabilityStatus** y **plan de capacidad** :</span><span class="sxs-lookup"><span data-stu-id="cf129-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="cf129-129">**Si el usuario está habilitado para el enrutamiento directo**, el usuario debe tener asignado un valor no nulo para OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="cf129-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="cf129-130">Para comprobar el atributo, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="cf129-131">La salida debe tener un valor no nulo, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf129-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="cf129-132">El usuario tiene habilitada la telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="cf129-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="cf129-133">Para comprobar si el usuario tiene habilitada la telefonía IP empresarial, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="cf129-134">El resultado debería tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf129-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="cf129-135">El usuario está conectado en línea y no en Skype empresarial local</span><span class="sxs-lookup"><span data-stu-id="cf129-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="cf129-136">Para garantizar que el usuario está conectado y no en Skype para empresas, la RegistrarPool debe ser nula y Hostingprovider manda debe contener un valor que empiece por "sipfed. online".</span><span class="sxs-lookup"><span data-stu-id="cf129-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="cf129-137">Para comprobar los valores, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="cf129-138">El resultado debería ser similar a:</span><span class="sxs-lookup"><span data-stu-id="cf129-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="cf129-139">El usuario tiene habilitada la Directiva de llamadas de Teams</span><span class="sxs-lookup"><span data-stu-id="cf129-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="cf129-140">La TeamsCallingPolicy vigente del usuario debe tener AllowPrivateCalling establecido en true.</span><span class="sxs-lookup"><span data-stu-id="cf129-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="cf129-141">De forma predeterminada, los usuarios heredan la directiva global, que tiene AllowPrivateCallingPolicy establecido en true de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cf129-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="cf129-142">Para obtener el TeamsCallingPolicy para un usuario y comprobar que AllowPrivateCalling está establecido en true, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="cf129-143">El resultado debería tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf129-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="cf129-144">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="cf129-144">Additional notes</span></span>

-   <span data-ttu-id="cf129-145">Es posible que tenga que reiniciar el cliente de Teams después de realizar cualquiera de estos cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="cf129-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="cf129-146">Si ha actualizado recientemente alguno de los criterios anteriores, es posible que tenga que esperar unas pocas horas para que el cliente reciba la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="cf129-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="cf129-147">Si sigue sin ver el teclado de marcado, compruebe si hay un error de aprovisionamiento con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cf129-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="cf129-148">Si ha transcurrido más de 24 horas y sigues teniendo problemas, ponte en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="cf129-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


