---
title: Implementar la apariencia de línea compartida en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Skype empresarial Server 2015, actualización acumulativa de noviembre de 2015. SLA es una característica para controlar varias llamadas en un número específico denominado número compartido.
ms.openlocfilehash: 2009b313b343d9746f3eeff5f53fec4899c2f9a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129313"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implementar la apariencia de línea compartida en Skype empresarial Server 2015

Lea este tema para obtener información sobre cómo implementar la apariencia de línea compartida (SLA) en Skype empresarial Server 2015, actualización acumulativa de noviembre de 2015. SLA es una característica para controlar varias llamadas en un número específico denominado número compartido.

Para obtener más información acerca de esta característica, consulte [Plan for shared line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Apariencia de línea compartida (SLA) es una nueva característica de Skype empresarial Server, actualización acumulativa de noviembre de 2015. Para habilitar esta característica, primero debe implementar esta actualización acumulativa.

### <a name="install-shared-line-appearance"></a>Instalación de apariencia de línea compartida

1. Después de implementar Skype empresarial Server, se ha implementado la actualización acumulativa de `SkypeServerUpdateInstaller.exe` noviembre de 2015, ejecute la revisión en cada servidor front-end del grupo.

2. El instalador implementará la versión más reciente de la aplicación SLA, pero la aplicación no está habilitada de forma predeterminada. Para habilitarlo, siga los pasos que se describen a continuación:

    a. Registre el SLA como una aplicación de servidor mediante la ejecución del siguiente comando para cada grupo de servidores:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   donde% FQDN% es el nombre de dominio completo del grupo de servidores.

    b. Ejecute el siguiente comando para actualizar los roles RBAC para los cmdlets de SLA:

   ```powershell
   Update-CsAdminRole
   ```

    c. Reinicie todos los servidores front-end (servicio RTCSRV) en todos los grupos donde se instaló y habilitó el SLA:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Crear un grupo de SLA y agregar usuarios a él

1. Cree el grupo SLA mediante el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    El cmdlet Set-CsSlaConfiguration marca la cuenta de Enterprise Voice Slagrupo1 como una entidad de SLA y el número de Slagrupo1 se convierte en el número del grupo de SLA. Todas las llamadas a Slagrupo1 sonarán a todo el grupo de SLA.

    En el ejemplo siguiente se crea un grupo de SLA para un usuario existente de Enterprise Voice, Slagrupo1, y se usa el número asignado para Slagrupo1 como el número de la principal de SLA.

    El comando establece el número máximo de llamadas simultáneas para el nuevo grupo de SLA en 3, y para las llamadas que superen eso para oír una señal de ocupado:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Puede usar Set-CsSlaConfiguration para crear un nuevo grupo de SLA o modificar uno existente.

    > [!NOTE]
    > Tenga en `-Identity` cuenta que lo que especifique debe ser una cuenta de usuario habilitada de Enterprise Voice existente válida.

2. Agregue delegados al grupo con el cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    En el ejemplo siguiente se agrega un usuario al grupo de SLA. Cada usuario agregado al grupo debe ser un usuario válido habilitado para telefonía IP empresarial:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Repita el cmdlet para cada usuario que desee agregar al grupo. Los usuarios solo pueden pertenecer a un único grupo de SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurar la opción de ocupado del grupo de SLA

- Configure la opción ocupado del grupo de SLA con el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    En el siguiente ejemplo se establecen llamadas que superan el número máximo de llamadas simultáneas que se van a reenviar al número de teléfono 202-555-1234. El destino puede ser un usuario de la organización en lugar de un número de teléfono; en ese caso, la sintaxis de la persona que va a recibir las llamadas enviadas es la misma que cuando se especifica un `sip:<NameofDelegate@domain>`delegado:. El otro parámetro posible `BusyOption` es: `Voicemail`

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configuración de la opción de llamada perdida del grupo SLA

1. Configure la opción de llamada perdida del grupo SLA mediante el cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. En el siguiente ejemplo se especifica que las llamadas perdidas se reenviarán al `sla_forward_number`usuario denominado. Las opciones válidas para `-MissedCallOption` el parámetro `Forward`son `BusySignal`, o `Disconnect`. Si lo prefiere `Forward`, también debe incluir el `-MissedCallForwardTarget` parámetro, con un usuario o número de teléfono como destino:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Quitar un delegado de un grupo

- Quite un delegado de un grupo mediante el cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por ejemplo:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Eliminar un grupo de SLA

- Elimine un grupo de SLA mediante el cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por ejemplo:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


