---
title: 'Lync Server 2013: implementación de la apariencia de línea compartida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d0bffd92c4c2e2448938c467eec73c9bab1a94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531417"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="9577a-102">Implementar la apariencia de línea compartida en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9577a-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9577a-103">_**Última modificación del tema:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="9577a-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="9577a-104">Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Lync Server 2013, actualización acumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="9577a-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="9577a-105">SLA es una característica para controlar varias llamadas en un número específico denominado número compartido.</span><span class="sxs-lookup"><span data-stu-id="9577a-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="9577a-106">Para obtener más información sobre esta característica, vea [Plan for shared line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="9577a-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="9577a-107">Apariencia de línea compartida (SLA) es una nueva característica de Lync Server 2013, actualización acumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="9577a-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="9577a-108">Para habilitar esta característica, primero debe implementar esta actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="9577a-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="9577a-109">Instalación de apariencia de línea compartida</span><span class="sxs-lookup"><span data-stu-id="9577a-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="9577a-110">Una vez implementado Lync Server 2013, la actualización acumulativa de abril de 2016, la aplicación de SLA no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9577a-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="9577a-111">Para habilitar la aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9577a-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="9577a-112">Registre el SLA como una aplicación de servidor mediante la ejecución del siguiente comando para cada grupo de servidores:</span><span class="sxs-lookup"><span data-stu-id="9577a-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="9577a-113">donde% FQDN% es el nombre de dominio completo del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="9577a-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="9577a-114">Ejecute el siguiente comando para actualizar los roles RBAC para los cmdlets de SLA:</span><span class="sxs-lookup"><span data-stu-id="9577a-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="9577a-115">Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos donde se instaló y habilitó el SLA:</span><span class="sxs-lookup"><span data-stu-id="9577a-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="9577a-116">Crear un grupo de SLA y agregar usuarios a él</span><span class="sxs-lookup"><span data-stu-id="9577a-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="9577a-117">Cree el grupo SLA mediante el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="9577a-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="9577a-118">El cmdlet Set-CsSlaConfiguration marca la cuenta de Enterprise Voice Slagrupo1 como una entidad de SLA y el número de Slagrupo1 se convierte en el número del grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="9577a-118">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="9577a-119">Todas las llamadas a Slagrupo1 sonarán a todo el grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="9577a-119">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="9577a-120">En el ejemplo siguiente se crea un grupo de SLA para un usuario existente de Enterprise Voice, Slagrupo1, y se usa el número asignado para Slagrupo1 como el número de la principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="9577a-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="9577a-121">El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3, y para las llamadas que superen eso para oír una señal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="9577a-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="9577a-122">Puede usar Set-CsSlaConfiguration para crear un nuevo grupo de SLA o modificar uno existente.</span><span class="sxs-lookup"><span data-stu-id="9577a-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9577a-123">Tenga en cuenta que lo que especifique <CODE>-Identity</CODE> debe ser una cuenta de usuario habilitada de Enterprise Voice existente válida.</span><span class="sxs-lookup"><span data-stu-id="9577a-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="9577a-124">Agregue delegados al grupo con el cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="9577a-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="9577a-125">En el ejemplo siguiente se agrega un usuario al grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="9577a-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="9577a-126">Cada usuario agregado al grupo debe ser un usuario válido habilitado para telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="9577a-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="9577a-127">Repita el cmdlet para cada usuario que desee agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="9577a-127">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="9577a-128">Los usuarios solo pueden pertenecer a un único grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="9577a-128">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="9577a-129">Configurar la opción de ocupado del grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="9577a-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="9577a-130">Configure la opción ocupado del grupo de SLA con el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="9577a-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="9577a-131">En el siguiente ejemplo se establecen llamadas que superan el número máximo de llamadas simultáneas que se van a reenviar al número de teléfono 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="9577a-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="9577a-132">El destino puede ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis de la persona que va a recibir las llamadas enviadas es la misma que cuando se especifica un delegado: `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="9577a-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="9577a-133">El otro parámetro posible `BusyOption` es `Voicemail` :</span><span class="sxs-lookup"><span data-stu-id="9577a-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="9577a-134">Configuración de la opción de llamada perdida del grupo SLA</span><span class="sxs-lookup"><span data-stu-id="9577a-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="9577a-135">Configure la opción de llamada perdida del grupo SLA mediante el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="9577a-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="9577a-136">En el siguiente ejemplo se especifica que las llamadas perdidas se reenviarán al usuario denominado `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="9577a-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="9577a-137">Las opciones válidas para el `-MissedCallOption` parámetro son `Forward` , `BusySignal` o `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="9577a-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="9577a-138">Si lo prefiere `Forward` , también debe incluir el `-MissedCallForwardTarget` parámetro, con un usuario o número de teléfono como destino:</span><span class="sxs-lookup"><span data-stu-id="9577a-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="9577a-139">Quitar un delegado de un grupo</span><span class="sxs-lookup"><span data-stu-id="9577a-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="9577a-140">Quite un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="9577a-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="9577a-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9577a-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="9577a-142">Eliminar un grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="9577a-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="9577a-143">Elimine un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="9577a-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="9577a-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9577a-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

