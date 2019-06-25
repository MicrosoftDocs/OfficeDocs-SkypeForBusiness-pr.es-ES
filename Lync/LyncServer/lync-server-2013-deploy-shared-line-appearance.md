---
title: 'Lync Server 2013: implementación de la apariencia de línea compartida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 708dc90d28944a050624e83af5f0c5fe48f6eeeb
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Implementar la apariencia de línea compartida en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-13_

Lea este tema para obtener información sobre cómo implementar el aspecto de línea compartida (SLA) en Lync Server 2013, actualización acumulativa de abril de 2016. Apariencia de líneas compartida es una característica para administrar varias llamadas en un número específico, denominado número compartido.

Para obtener más información sobre esta característica, vea [planear la apariencia de líneas compartidas en Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

La apariencia de línea compartida (SLA) es una característica nueva de Lync Server 2013, actualización acumulativa de abril de 2016. Para habilitar esta característica, primero tiene que implementar esta actualización acumulativa.

<div>

## <a name="install-shared-line-appearance"></a>Instalar Apariencia de línea compartida

1.  Después de implementar Lync Server 2013, la actualización acumulativa de abril de 2016, la aplicación SLA no está habilitada de forma predeterminada. Para habilitar la aplicación, siga los pasos que se indican a continuación:
    
    1.  Registre SLA como una aplicación de servidor; para ello, ejecute el comando siguiente para cada grupo:
        
            New-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                            http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                            $true -Priority (Get-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/UserServices').Priority 
        
        donde %FQDN% es el nombre de dominio completo del grupo.
    
    2.  Ejecute el comando siguiente para actualizar los roles RBAC para los cmdlets de SLA:
        
            Update-CsAdminRole 
    
    3.  Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos donde se instaló y habilitó SLA:
        
        ``` 
         Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Crear un grupo de SLA y agregar usuarios

1.  Para crear el grupo de SLA, use el cmdlet de [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -MaxNumberOfCalls <Number> -BusyOption
                  <BusyOnBusy|Voicemail|Forward> [-Target
                  <TargetUserOrPhoneNumber>]
    
    El cmdlet Set-CsSlaConfiguration marca la cuenta de telefonía IP empresarial SLAGrupo1 como una entidad de SLA y el número de SLAGrupo1 se convierte en el número para el grupo de SLA. Todas las llamadas del SLAGrupo1 llamarán a todo el grupo de SLA.
    
    En el ejemplo siguiente se crea un grupo de SLA para un usuario de telefonía IP empresarial existente (SLAGrupo1) y se usa el número asignado para SLAGrupo1 como el número de la línea principal de SLA.
    
    El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3 y configura las llamadas que superen ese número para que escuchen una señal de línea ocupada:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                  -BusyOption BusyOnBusy
    
    Puede usar Set-CsSlaConfiguration para crear un grupo de SLA o modificar uno existente.
    
    <div>
    

    > [!NOTE]  
    > Ten en cuenta que lo que <CODE>-Identity</CODE> especifiques debe ser una cuenta de usuario válida habilitada para voz de empresa existente.

    
    </div>

2.  Agregue delegados al grupo con el cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates):
    
        Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    En el ejemplo siguiente se agrega un usuario al grupo de SLA. Cada usuario agregado al grupo debe ser un usuario válido habilitado para voz empresarial:
    
        Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate1@contoso.com
    
    Repita el cmdlet para cada usuario que quiera agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Configurar la opción de ocupado del grupo de SLA

1.  Configure la opción de ocupado del grupo de SLA con el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    
    En el ejemplo siguiente se muestran llamadas que superan el número máximo de llamadas simultáneas que se reenviarán al número de teléfono 202-555-1234. El objetivo puede ser un usuario de su organización en lugar de un número de teléfono; en ese caso, la sintaxis de la persona que recibe las llamadas desviadas es la misma que cuando se especifica un delegado: `sip:<NameofDelegate@domain>`. El otro parámetro posible para `BusyOption` es `Voicemail`:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
                  -Target tel:+2025551234]

</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Configurar la opción de llamada perdida del grupo de SLA

1.  Configure la opción de llamada perdida del grupo de SLA con el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
                  -MissedCallOption <Option> -MissedCallForwardTarget
                  <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    
    En el ejemplo siguiente se especifica que las llamadas perdidas se desviarán al usuario `sla_forward_number`con nombre. Las opciones válidas para `-MissedCallOption` el parámetro `Forward`son `BusySignal`, o `Disconnect`. Si lo desea `Forward`, también debe incluir el `-MissedCallForwardTarget` parámetro, con un número de teléfono o usuario como destino:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
                  Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
            -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 

</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Quitar un delegado de un grupo

1.  Para quitar un delegado de un grupo, use el cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates):
    
        Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    Por ejemplo:
    
        Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate3@contoso.com

</div>

<div>

## <a name="delete-an-sla-group"></a>Eliminar un grupo de SLA

1.  Eliminar un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):
    
    ``` 
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Por ejemplo:
    
        Remove-CsSlaConfiguration -Identity SLAGroup1 

</div>

</div>

<span> </span>

</div>

</div>

</div>

