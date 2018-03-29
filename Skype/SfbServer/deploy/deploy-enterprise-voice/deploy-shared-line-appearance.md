---
title: Implementar la apariencia de línea compartida en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lea este tema para obtener información acerca de cómo implementar apariencia de líneas compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. Apariencia de líneas compartida es una característica para administrar varias llamadas en un número específico, denominado número compartido.
ms.openlocfilehash: ba7ca76c9ef0c6ed49ba26205df69e7840ec75d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="eb22f-104">Implementar la apariencia de línea compartida en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="eb22f-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eb22f-p102">Lea este tema para obtener información acerca de cómo implementar apariencia de líneas compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. Apariencia de líneas compartida es una característica para administrar varias llamadas en un número específico, denominado número compartido.</span><span class="sxs-lookup"><span data-stu-id="eb22f-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span> 
  
<span data-ttu-id="eb22f-107">Para obtener más información acerca de esta característica, consulte [Plan de apariencia de línea compartida en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="eb22f-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>
  
<span data-ttu-id="eb22f-108">Apariencia de línea compartida (SLA) es una nueva característica de Skype para Business Server, noviembre de 2015 actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="eb22f-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="eb22f-109">Para habilitar esta característica, primero tiene que implementar esta actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="eb22f-109">To enable this feature, you must have first deployed this cumulative update.</span></span>
  
### <a name="install-shared-line-appearance"></a><span data-ttu-id="eb22f-110">Instalar Apariencia de línea compartida</span><span class="sxs-lookup"><span data-stu-id="eb22f-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="eb22f-111">Después de Skype para Business Server, noviembre de 2015 se implementa la actualización acumulativa, ejecute el `SkypeServerUpdateInstaller.exe` revisión en cada servidor Front-End en el grupo.</span><span class="sxs-lookup"><span data-stu-id="eb22f-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>
    
2. <span data-ttu-id="eb22f-p104">El instalador implementará la última versión de la aplicación SLA, pero la aplicación no está habilitada de forma predeterminada. Para habilitarla, siga los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="eb22f-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>
    
    <span data-ttu-id="eb22f-114">a.</span><span class="sxs-lookup"><span data-stu-id="eb22f-114">a.</span></span> <span data-ttu-id="eb22f-115">Registre SLA como una aplicación de servidor; para ello, ejecute el comando siguiente para cada grupo:</span><span class="sxs-lookup"><span data-stu-id="eb22f-115">Register SLA as a server application by running the following command for each pool:</span></span>
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   <span data-ttu-id="eb22f-116">donde %FQDN% es el nombre de dominio completo del grupo.</span><span class="sxs-lookup"><span data-stu-id="eb22f-116">where %FQDN% is the fully qualified domain name of the pool.</span></span> 
    
    <span data-ttu-id="eb22f-117">b.</span><span class="sxs-lookup"><span data-stu-id="eb22f-117">b.</span></span> <span data-ttu-id="eb22f-118">Ejecute el comando siguiente para actualizar los roles RBAC para los cmdlets de SLA:</span><span class="sxs-lookup"><span data-stu-id="eb22f-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span> 
    
   ```
   Update-CsAdminRole 
   ```

    <span data-ttu-id="eb22f-119">c.</span><span class="sxs-lookup"><span data-stu-id="eb22f-119">c.</span></span> <span data-ttu-id="eb22f-120">Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos donde se instaló y habilitó SLA:</span><span class="sxs-lookup"><span data-stu-id="eb22f-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="eb22f-121">Crear un grupo de SLA y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="eb22f-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="eb22f-122">Cree el grupo SLA mediante el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="eb22f-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -MaxNumberOfCalls <Number> -BusyOption
          <BusyOnBusy|Voicemail|Forward> [-Target
          <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="eb22f-p108">El cmdlet Set-CsSlaConfiguration marca la cuenta de telefonía IP empresarial SLAGrupo1 como una entidad de SLA y el número de SLAGrupo1 se convierte en el número para el grupo de SLA. Todas las llamadas del SLAGrupo1 llamarán a todo el grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="eb22f-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="eb22f-125">En el ejemplo siguiente se crea un grupo de SLA para un usuario de telefonía IP empresarial existente (SLAGrupo1) y se usa el número asignado para SLAGrupo1 como el número de la línea principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="eb22f-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span> 
    
    <span data-ttu-id="eb22f-126">El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3 y configura las llamadas que superen ese número para que escuchen una señal de línea ocupada:</span><span class="sxs-lookup"><span data-stu-id="eb22f-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
          -BusyOption BusyOnBusy
  ```

    <span data-ttu-id="eb22f-127">Puede usar Set-CsSlaConfiguration para crear un grupo de SLA o modificar uno existente.</span><span class="sxs-lookup"><span data-stu-id="eb22f-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb22f-128">Tenga en cuenta que lo que especifique para `-Identity` debe ser una cuenta válida de usuario habilitado para Telefonía IP empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="eb22f-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>
  
2. <span data-ttu-id="eb22f-129">Agregar delegados al grupo mediante el cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="eb22f-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    <span data-ttu-id="eb22f-130">En el ejemplo siguiente se agrega un usuario al grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="eb22f-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="eb22f-131">Cada usuario que se agrega al grupo debe ser un usuario habilitado para Telefonía IP empresarial válido:</span><span class="sxs-lookup"><span data-stu-id="eb22f-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate1@contoso.com
  ```

    <span data-ttu-id="eb22f-p110">Repita el cmdlet para cada usuario que quiera agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="eb22f-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>
    
### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="eb22f-134">Configurar la opción de ocupado del grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="eb22f-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="eb22f-135">Configurar el SLA opción ocupado de grupo mediante el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="eb22f-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="eb22f-136">En el ejemplo siguiente se muestran llamadas que superan el número máximo de llamadas simultáneas que se reenviarán al número de teléfono 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="eb22f-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="eb22f-137">El destino puede ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis para la persona que reciba las llamadas desviadas es el mismo que cuando se especifica un delegado: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="eb22f-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="eb22f-138">El posible parámetro para `BusyOption` es `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="eb22f-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
          -Target tel:+2025551234]
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="eb22f-139">Configurar la opción de llamada perdida del grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="eb22f-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="eb22f-140">Configurar el grupo de SLA opción de llamadas perdidas mediante el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="eb22f-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
          -MissedCallOption <Option> -MissedCallForwardTarget
          <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. <span data-ttu-id="eb22f-141">En el ejemplo siguiente se especifica que se enviará al usuario denominado llamadas perdidas `sla_forward_number`.</span><span class="sxs-lookup"><span data-stu-id="eb22f-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="eb22f-142">Las opciones válidas para la `-MissedCallOption` parámetro son `Forward`, `BusySignal`, o `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="eb22f-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="eb22f-143">Si elige `Forward`, debe incluir también el `-MissedCallForwardTarget` parámetro, con un número de teléfono o el usuario como el destino:</span><span class="sxs-lookup"><span data-stu-id="eb22f-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
          Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
    -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="eb22f-144">Quitar un delegado de un grupo</span><span class="sxs-lookup"><span data-stu-id="eb22f-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="eb22f-145">Para quitar a un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="eb22f-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    <span data-ttu-id="eb22f-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eb22f-146">For example:</span></span>
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="eb22f-147">Eliminar un grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="eb22f-147">Delete an SLA group</span></span>

- <span data-ttu-id="eb22f-148">Eliminar un grupo de acuerdo con el cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="eb22f-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
          
  ```

    <span data-ttu-id="eb22f-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eb22f-149">For example:</span></span> 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


