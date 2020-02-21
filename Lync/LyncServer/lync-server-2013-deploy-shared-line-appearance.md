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
ms.openlocfilehash: 3be8c6610d27040d608070ca1e7dfb50a29a0cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Implementar la apariencia de línea compartida en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-13_

Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Lync Server 2013, actualización acumulativa de abril de 2016. SLA es una característica para controlar varias llamadas en un número específico denominado número compartido.

Para obtener más información sobre esta característica, vea [Plan for shared line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

Apariencia de línea compartida (SLA) es una nueva característica de Lync Server 2013, actualización acumulativa de abril de 2016. Para habilitar esta característica, primero debe implementar esta actualización acumulativa.

<div>

## <a name="install-shared-line-appearance"></a>Instalación de apariencia de línea compartida

1.  Una vez implementado Lync Server 2013, la actualización acumulativa de abril de 2016, la aplicación de SLA no está habilitada de forma predeterminada. Para habilitar la aplicación, siga estos pasos:
    
    1.  Registre el SLA como una aplicación de servidor mediante la ejecución del siguiente comando para cada grupo de servidores:
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        donde% FQDN% es el nombre de dominio completo del grupo de servidores.
    
    2.  Ejecute el siguiente comando para actualizar los roles RBAC para los cmdlets de SLA:
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos donde se instaló y habilitó el SLA:
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Crear un grupo de SLA y agregar usuarios a él

1.  Cree el grupo SLA mediante el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    El cmdlet Set-CsSlaConfiguration marca la cuenta de Enterprise Voice Slagrupo1 como una entidad de SLA y el número de Slagrupo1 se convierte en el número del grupo de SLA. Todas las llamadas a Slagrupo1 sonarán a todo el grupo de SLA.
    
    En el ejemplo siguiente se crea un grupo de SLA para un usuario existente de Enterprise Voice, Slagrupo1, y se usa el número asignado para Slagrupo1 como el número de la principal de SLA.
    
    El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3, y para las llamadas que superen eso para oír una señal de ocupado:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Puede usar Set-CsSlaConfiguration para crear un nuevo grupo de SLA o modificar uno existente.
    
    <div>
    

    > [!NOTE]  
    > Tenga en <CODE>-Identity</CODE> cuenta que lo que especifique debe ser una cuenta de usuario habilitada de Enterprise Voice existente válida.

    
    </div>

2.  Agregue delegados al grupo con el cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    En el ejemplo siguiente se agrega un usuario al grupo de SLA. Cada usuario agregado al grupo debe ser un usuario válido habilitado para telefonía IP empresarial:
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Repita el cmdlet para cada usuario que desee agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Configurar la opción de ocupado del grupo de SLA

1.  Configure la opción ocupado del grupo de SLA con el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    En el siguiente ejemplo se establecen llamadas que superan el número máximo de llamadas simultáneas que se van a reenviar al número de teléfono 202-555-1234. El destino puede ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis de la persona que va a recibir las llamadas enviadas es la misma que cuando se especifica un `sip:<NameofDelegate@domain>`delegado:. El otro parámetro posible `BusyOption` es: `Voicemail`
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Configuración de la opción de llamada perdida del grupo SLA

1.  Configure la opción de llamada perdida del grupo SLA mediante el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    En el siguiente ejemplo se especifica que las llamadas perdidas se reenviarán al `sla_forward_number`usuario denominado. Las opciones válidas para `-MissedCallOption` el parámetro `Forward`son `BusySignal`, o `Disconnect`. Si lo prefiere `Forward`, también debe incluir el `-MissedCallForwardTarget` parámetro, con un usuario o número de teléfono como destino:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Quitar un delegado de un grupo

1.  Quite un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Por ejemplo:
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>Eliminar un grupo de SLA

1.  Elimine un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Por ejemplo:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

