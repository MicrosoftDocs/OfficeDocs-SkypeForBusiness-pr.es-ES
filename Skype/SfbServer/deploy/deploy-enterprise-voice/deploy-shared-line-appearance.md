---
title: Implementación de la apariencia de línea compartida en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lea este tema para obtener información sobre cómo implementar Shared Line Appearance (SLA) en Skype Empresarial Server actualización acumulativa de noviembre de 2015. Sla es una característica para controlar varias llamadas en un número específico denominado número compartido.
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671596"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implementación de la apariencia de línea compartida en Skype Empresarial Server 2015

Lea este tema para obtener información sobre cómo implementar Shared Line Appearance (SLA) en Skype Empresarial Server actualización acumulativa de noviembre de 2015. Sla es una característica para controlar varias llamadas en un número específico denominado número compartido.

Para obtener más información sobre esta característica, vea [Planear la apariencia de línea compartida en Skype Empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Shared Line Appearance (SLA) es una nueva característica de Skype Empresarial Server, actualización acumulativa de noviembre de 2015. Para habilitar esta característica, primero debe haber implementado esta actualización acumulativa.

## <a name="install-shared-line-appearance"></a>Instalación de la apariencia de línea compartida

1. Después de Skype Empresarial Server, se implementa la actualización acumulativa de noviembre de 2015, ejecute la `SkypeServerUpdateInstaller.exe` revisión en cada servidor front-end del grupo.

2. El instalador implementará la versión más reciente de la aplicación de acuerdo de nivel de servicio, pero la aplicación no está habilitada de forma predeterminada. Se habilita siguiendo los pasos descritos a continuación:

    a. Registre el Acuerdo de Nivel de Servicio como una aplicación de servidor mediante la ejecución del siguiente comando para cada grupo:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   donde %FQDN% es el nombre de dominio completo del grupo.

    b. Ejecute el siguiente comando para actualizar los roles de RBAC para los cmdlets del Acuerdo de Nivel de Servicio:

   ```powershell
   Update-CsAdminRole
   ```

    c. Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos en los que se ha instalado y habilitado el Acuerdo de Nivel de Servicio:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>Creación de un grupo de acuerdos de nivel de servicio y incorporación de usuarios

1. Cree el grupo de SLA mediante el cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    El cmdlet Set-CsSlaConfiguration marca la cuenta de Telefonía IP empresarial SLAGroup1 como una entidad sla y el número de SLAGroup1 se convierte en el número del grupo de SLA. Todas las llamadas a SLAGroup1 llamarán a todo el grupo de SLA.

    En el ejemplo siguiente se crea un grupo de acuerdos de nivel de servicio para un usuario Telefonía IP empresarial existente, SLAGroup1, y se usa el número asignado para SLAGroup1 como número de línea principal del ACUERDO de Nivel de Servicio.

    El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3, y para las llamadas que exceden esa cantidad para escuchar una señal de ocupado:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Puede usar Set-CsSlaConfiguration para crear un nuevo grupo de ACUERDO de Nivel de Servicio o modificar uno existente.

    > [!NOTE]
    > Tenga en cuenta que lo que especifique para debe ser una cuenta de usuario habilitada para `-Identity` Telefonía IP empresarial existente.

2. Agregue delegados al grupo mediante el cmdlet [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    En el ejemplo siguiente se agrega un usuario al grupo de acuerdos de nivel de servicio. Cada usuario agregado al grupo debe ser un usuario válido habilitado para Telefonía IP empresarial:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Repita el cmdlet para cada usuario que quiera agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de ACUERDO de Nivel de Servicio.

## <a name="configure-the-sla-group-busy-option"></a>Configuración de la opción de disponibilidad del grupo de acuerdos de nivel de servicio

- Configure la opción busy del grupo de ACUERDO de nivel de servicio mediante el cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    En el ejemplo siguiente se establecen llamadas que superan el número máximo de llamadas simultáneas que se van a reenviar al número de teléfono 202-555-1234. El destino podría ser un usuario de su organización en lugar de un número de teléfono; en ese caso, la sintaxis para que la persona reciba las llamadas reenviadas es la misma que cuando se especifica un delegado:  `sip:<NameofDelegate@domain>`. El otro parámetro posible para  `BusyOption` es `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>Configuración de la opción de llamada perdida del grupo de acuerdo de nivel de servicio

1. Configure la opción de llamada perdida del grupo de SLA mediante el cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. En el ejemplo siguiente se especifica que las llamadas perdidas se van a reenviar al usuario denominado  `sla_forward_number`. Las opciones válidas para el  `-MissedCallOption` parámetro son `Forward`,  `BusySignal`o  `Disconnect`. Si elige  `Forward`, también debe incluir el  `-MissedCallForwardTarget` parámetro , con un usuario o un número de teléfono como destino:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>Quitar un delegado de un grupo

- Quite un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por ejemplo:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>Eliminación de un grupo de ACUERDO de nivel de servicio

- Elimine un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por ejemplo:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
