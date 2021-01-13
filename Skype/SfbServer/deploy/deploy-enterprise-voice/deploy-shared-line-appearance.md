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
description: Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. SLA es una característica para administrar varias llamadas en un número específico denominado número compartido.
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812410"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implementar la apariencia de línea compartida en Skype Empresarial Server 2015

Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. SLA es una característica para administrar varias llamadas en un número específico denominado número compartido.

Para obtener más información acerca de esta característica, consulte [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Apariencia de línea compartida (SLA) es una nueva característica de Skype Empresarial Server, actualización acumulativa de noviembre de 2015. Para habilitar esta característica, primero debes haber implementado esta actualización acumulativa.

### <a name="install-shared-line-appearance"></a>Instalar apariencia de línea compartida

1. Después de implementar Skype Empresarial Server, la actualización acumulativa de noviembre de 2015, ejecute la revisión en cada servidor  `SkypeServerUpdateInstaller.exe` front-end del grupo.

2. Sin embargo, el instalador implementará la versión más reciente de la aplicación de SLA, pero la aplicación no está habilitada de forma predeterminada. Se habilita siguiendo los pasos que se describen a continuación:

    a. Registre SLA como aplicación de servidor ejecutando el siguiente comando para cada grupo de servidores:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   donde %FQDN% es el nombre de dominio completo del grupo.

    b. Ejecute el siguiente comando para actualizar los roles RBAC para los cmdlets de SLA:

   ```powershell
   Update-CsAdminRole
   ```

    c. Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos en los que se instaló y habilitó el SLA:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Crear un grupo de SLA y agregarle usuarios

1. Cree el grupo de SLA con el cmdlet [Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    El cmdlet Set-CsSlaConfiguration marca la cuenta de Telefonía IP empresarial SLAGroup1 como entidad de SLA y el número de SLAGroup1 se convierte en el número del grupo de SLA. Todas las llamadas a SLAGroup1 llamarán a todo el grupo de SLA.

    En el siguiente ejemplo se crea un grupo de SLA para un usuario de Telefonía IP empresarial existente, SLAGroup1, y se usa el número asignado para SLAGroup1 como número de línea principal de SLA.

    El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3, y para las llamadas que supere ese número oirá una señal de ocupado:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Puede usar Set-CsSlaConfiguration para crear un nuevo grupo de SLA o modificar uno existente.

    > [!NOTE]
    > Tenga en cuenta que lo que especifique debe ser una cuenta de usuario  `-Identity` Telefonía IP empresarial existente válida.

2. Agregue delegados al grupo mediante el cmdlet [Add-CsSlaDelegates:](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    En el siguiente ejemplo se agrega un usuario al grupo de SLA. Cada usuario agregado al grupo debe ser un usuario Telefonía IP empresarial habilitado para correo electrónico:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Repita el cmdlet para cada usuario que desee agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurar la opción de disponibilidad del grupo de SLA

- Configure la opción de disponibilidad del grupo de SLA con el cmdlet [Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    En el siguiente ejemplo se establecen llamadas que superan el número máximo de llamadas simultáneas que se reenviarán al número de teléfono 202-555-1234. El destino podría ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis para que la persona reciba las llamadas reenviadas es la misma que cuando se especifica un delegado:  `sip:<NameofDelegate@domain>` . El otro parámetro posible  `BusyOption` `Voicemail` es:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurar la opción de llamada perdida del grupo de SLA

1. Configure la opción de llamada perdida del grupo de SLA con el cmdlet [Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. En el siguiente ejemplo se especifica que las llamadas perdidas se desván al usuario denominado  `sla_forward_number` . Las opciones válidas para  `-MissedCallOption` el parámetro son , o `Forward`  `BusySignal`  `Disconnect` . Si lo  `Forward` elige, también debe incluir el  `-MissedCallForwardTarget` parámetro, con un usuario o número de teléfono como destino:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Quitar un delegado de un grupo

- Quite un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates:](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por ejemplo:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Eliminar un grupo de SLA

- Elimine un grupo de SLA con el cmdlet [Remove-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por ejemplo:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


