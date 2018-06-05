---
title: Implementar la apariencia de línea compartida en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lea este tema para obtener información acerca de cómo implementar apariencia de líneas compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. Apariencia de líneas compartida es una característica para administrar varias llamadas en un número específico, denominado número compartido.
ms.openlocfilehash: e8325cd7bbd6c1777143ac83ad88aae07a3a48a0
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568341"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implementar la apariencia de línea compartida en Skype Empresarial Server 2015
 
Lea este tema para obtener información acerca de cómo implementar apariencia de líneas compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. Apariencia de líneas compartida es una característica para administrar varias llamadas en un número específico, denominado número compartido. 
  
Para obtener más información acerca de esta característica, vea [Plan for Shared apariencia de línea en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).
  
Apariencia de línea compartida (SLA) es una característica nueva de Skype para Business Server, de noviembre de 2015 actualización acumulativa. Para habilitar esta característica, primero tiene que implementar esta actualización acumulativa.
  
### <a name="install-shared-line-appearance"></a>Instalar Apariencia de línea compartida

1. Después de Skype para Business Server, de noviembre de 2015 se haya implementado la actualización acumulativa, ejecute el `SkypeServerUpdateInstaller.exe` revisión en cada servidor Front-End del grupo de servidores.
    
2. El instalador implementará la última versión de la aplicación SLA, pero la aplicación no está habilitada de forma predeterminada. Para habilitarla, siga los pasos que se indican a continuación:
    
    a. Registre SLA como una aplicación de servidor; para ello, ejecute el comando siguiente para cada grupo:
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   donde %FQDN% es el nombre de dominio completo del grupo. 
    
    b. Ejecute el comando siguiente para actualizar los roles RBAC para los cmdlets de SLA: 
    
   ```
   Update-CsAdminRole 
   ```

    c. Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos donde se instaló y habilitó SLA:
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV   
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Crear un grupo de SLA y agregar usuarios

1. Crear el grupo de SLA mediante el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
  ```

    El cmdlet Set-CsSlaConfiguration marca la cuenta de telefonía IP empresarial SLAGrupo1 como una entidad de SLA y el número de SLAGrupo1 se convierte en el número para el grupo de SLA. Todas las llamadas del SLAGrupo1 llamarán a todo el grupo de SLA.
    
    En el ejemplo siguiente se crea un grupo de SLA para un usuario de telefonía IP empresarial existente (SLAGrupo1) y se usa el número asignado para SLAGrupo1 como el número de la línea principal de SLA. 
    
    El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3 y configura las llamadas que superen ese número para que escuchen una señal de línea ocupada:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
  ```

    Puede usar Set-CsSlaConfiguration para crear un grupo de SLA o modificar uno existente.
    
    > [!NOTE]
    > Tenga en cuenta que lo que se especifique para `-Identity` debe ser una cuenta de usuario habilitado para Enterprise Voice existente válido.
  
2. Agregue delegados al grupo mediante el cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    En el ejemplo siguiente se agrega un usuario al grupo de SLA. Cada usuario que se agregará al grupo debe ser un usuario habilitado para Enterprise Voice válido:
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
  ```

    Repita el cmdlet para cada usuario que quiera agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de SLA.
    
### <a name="configure-the-sla-group-busy-option"></a>Configurar la opción de ocupado del grupo de SLA

- Configurar el SLA opción ocupado de grupo mediante el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    En el ejemplo siguiente se muestran llamadas que superan el número máximo de llamadas simultáneas que se reenviarán al número de teléfono 202-555-1234. El destino podría ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis de la persona que reciba las llamadas desviadas es el mismo que cuando se especifica un delegado: `sip:<NameofDelegate@domain>`. El parámetro otro posible para `BusyOption` es `Voicemail`:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234]
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurar la opción de llamada perdida del grupo de SLA

1. Configurar el grupo de SLA opción de llamadas perdidas mediante el cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. En el ejemplo siguiente se especifica que las llamadas perdidas están se transfieran al usuario denominado `sla_forward_number`. Las opciones válidas para la `-MissedCallOption` parámetro son `Forward`, `BusySignal`, o `Disconnect`. Si elige `Forward`, también debe incluir la `-MissedCallForwardTarget` parámetro, con un usuario o número de teléfono como destino:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a>Quitar un delegado de un grupo

- Quitar a un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por ejemplo:
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Eliminar un grupo de SLA

- Eliminar un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por ejemplo: 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


