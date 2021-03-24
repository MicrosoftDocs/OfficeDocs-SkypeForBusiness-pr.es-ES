---
title: Implementar la apariencia de línea compartida en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. SLA es una característica para controlar varias llamadas en un número específico denominado número compartido.
ms.openlocfilehash: 7758354b7c4be123cb9b5a482af3304b069931a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104916"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="d17fa-104">Implementar la apariencia de línea compartida en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d17fa-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="d17fa-105">Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015.</span><span class="sxs-lookup"><span data-stu-id="d17fa-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d17fa-106">SLA es una característica para controlar varias llamadas en un número específico denominado número compartido.</span><span class="sxs-lookup"><span data-stu-id="d17fa-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="d17fa-107">Para obtener más información acerca de esta característica, vea [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="d17fa-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="d17fa-108">Apariencia de línea compartida (SLA) es una nueva característica de Skype Empresarial Server, actualización acumulativa de noviembre de 2015.</span><span class="sxs-lookup"><span data-stu-id="d17fa-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d17fa-109">Para habilitar esta característica, primero debe haber implementado esta actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="d17fa-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="d17fa-110">Instalar apariencia de línea compartida</span><span class="sxs-lookup"><span data-stu-id="d17fa-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="d17fa-111">Después de implementar Skype Empresarial Server, actualización acumulativa de noviembre de 2015, ejecute la revisión en cada  `SkypeServerUpdateInstaller.exe` servidor front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="d17fa-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="d17fa-112">El instalador implementará la versión más reciente de la aplicación SLA, pero la aplicación no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d17fa-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="d17fa-113">Se habilita siguiendo los pasos descritos a continuación:</span><span class="sxs-lookup"><span data-stu-id="d17fa-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="d17fa-114">a.</span><span class="sxs-lookup"><span data-stu-id="d17fa-114">a.</span></span> <span data-ttu-id="d17fa-115">Registre SLA como una aplicación de servidor ejecutando el siguiente comando para cada grupo:</span><span class="sxs-lookup"><span data-stu-id="d17fa-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="d17fa-116">donde %FQDN% es el nombre de dominio completo del grupo.</span><span class="sxs-lookup"><span data-stu-id="d17fa-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="d17fa-117">b.</span><span class="sxs-lookup"><span data-stu-id="d17fa-117">b.</span></span> <span data-ttu-id="d17fa-118">Ejecute el siguiente comando para actualizar los roles RBAC para los cmdlets sla:</span><span class="sxs-lookup"><span data-stu-id="d17fa-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="d17fa-119">c.</span><span class="sxs-lookup"><span data-stu-id="d17fa-119">c.</span></span> <span data-ttu-id="d17fa-120">Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos de servidores donde se instaló y habilitó SLA:</span><span class="sxs-lookup"><span data-stu-id="d17fa-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="d17fa-121">Crear un grupo de SLA y agregarle usuarios</span><span class="sxs-lookup"><span data-stu-id="d17fa-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="d17fa-122">Cree el grupo sla mediante el cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d17fa-122">Create the SLA group by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="d17fa-123">El cmdlet Set-CsSlaConfiguration marca la cuenta Telefonía IP empresarial SLAGroup1 como una entidad SLA y el número de SLAGroup1 se convierte en el número del grupo sla.</span><span class="sxs-lookup"><span data-stu-id="d17fa-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="d17fa-124">Todas las llamadas a SLAGroup1 llamarán a todo el grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="d17fa-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="d17fa-125">En el siguiente ejemplo se crea un grupo sla para un usuario de Telefonía IP empresarial existente, SLAGroup1, y se usa el número asignado para SLAGroup1 como el número de línea principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="d17fa-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="d17fa-126">El comando establece el número máximo de llamadas simultáneas para el nuevo grupo sla en 3, y para las llamadas que supere eso para escuchar una señal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="d17fa-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="d17fa-127">Puede usar Set-CsSlaConfiguration para crear un nuevo grupo de SLA o modificar uno existente.</span><span class="sxs-lookup"><span data-stu-id="d17fa-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d17fa-128">Tenga en cuenta que lo que especifique debe ser una cuenta de usuario  `-Identity` Telefonía IP empresarial cuenta de usuario habilitada.</span><span class="sxs-lookup"><span data-stu-id="d17fa-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="d17fa-129">Agregue delegados al grupo mediante el cmdlet [Add-CsSlaDelegates:](/powershell/module/skype/add-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d17fa-129">Add delegates to the group by using the [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="d17fa-130">En el ejemplo siguiente se agrega un usuario al grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="d17fa-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="d17fa-131">Cada usuario agregado al grupo debe ser un usuario Telefonía IP empresarial habilitado para la aplicación:</span><span class="sxs-lookup"><span data-stu-id="d17fa-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="d17fa-132">Repita el cmdlet para cada usuario que desee agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="d17fa-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="d17fa-133">Los usuarios solo pueden pertenecer a un único grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="d17fa-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="d17fa-134">Configurar la opción de disponibilidad del grupo SLA</span><span class="sxs-lookup"><span data-stu-id="d17fa-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="d17fa-135">Configure el grupo sla opción ocupado mediante el cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d17fa-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="d17fa-136">En el ejemplo siguiente se establecen llamadas que superan el número máximo de llamadas simultáneas que se reenviarán al número de teléfono 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="d17fa-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="d17fa-137">El destino podría ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis para que la persona reciba las llamadas reenviadas es la misma que cuando se especifica un delegado:  `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="d17fa-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="d17fa-138">El otro parámetro posible  `BusyOption` para `Voicemail` es:</span><span class="sxs-lookup"><span data-stu-id="d17fa-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="d17fa-139">Configurar la opción de llamada perdida del grupo SLA</span><span class="sxs-lookup"><span data-stu-id="d17fa-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="d17fa-140">Configure la opción de llamada perdida del grupo SLA mediante el cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d17fa-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="d17fa-141">En el ejemplo siguiente se especifica que las llamadas perdidas se reenviarán al usuario denominado  `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="d17fa-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="d17fa-142">Las opciones válidas para  `-MissedCallOption` el parámetro son , o `Forward`  `BusySignal`  `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="d17fa-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="d17fa-143">Si elige  `Forward` , también debe incluir el parámetro, con un usuario o número de teléfono como  `-MissedCallForwardTarget` destino:</span><span class="sxs-lookup"><span data-stu-id="d17fa-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="d17fa-144">Quitar un delegado de un grupo</span><span class="sxs-lookup"><span data-stu-id="d17fa-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="d17fa-145">Quite un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates:](/powershell/module/skype/remove-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d17fa-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="d17fa-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d17fa-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="d17fa-147">Eliminar un grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="d17fa-147">Delete an SLA group</span></span>

- <span data-ttu-id="d17fa-148">Elimine un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration:](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d17fa-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="d17fa-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d17fa-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```