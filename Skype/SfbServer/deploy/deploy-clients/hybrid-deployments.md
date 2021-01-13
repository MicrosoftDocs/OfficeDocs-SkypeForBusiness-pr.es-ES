---
title: Implementaciones híbridas del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno híbrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805900"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implementaciones híbridas del Sistema de sala de Skype

Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno híbrido.
  
## <a name="hybrid-deployments"></a>Implementaciones híbridas

Siga estos pasos si su topología tiene Skype Empresarial Server y Exchange Online, y desea hospedar el buzón de recursos del Sistema de sala de Skype en Exchange Online. En esta sección también se describe un escenario híbrido en el que exchange Online y Exchange Server implementación.
  
Para fines ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.
  
1. Cree un buzón de recursos en el Centro de administración de Exchange (LyncSample.ccsctp.net) conectándose al Shell de administración de Exchange Online, tal como se describe en Aprovisionamiento de Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Puede comprobar la conectividad de OWA mediante lrstest5@LyncSample.ccsctp.net para iniciar sesión.
    
2. En el Centro de administración de Microsoft 365 u Office 365 Exchange, agregue una dirección de correo electrónico lrstest5@LyncSample.com (dominio local) y estacúla como la dirección de respuesta.
    
3. Cree un usuario local de Active Directory lrstest5@LyncSample.com, establezca la dirección de correo electrónico en lrstest5@LyncSample.com y establezca la dirección de destino en lrstest5@LyncSample.com.
    
4. Desencadene la sincronización de directorios y, una vez completada la sincronización, compruebe que los usuarios se combinan en AAD y que no puede cambiar las propiedades de los recursos del destinatario en el Centro de administración de Microsoft 365 u Office 365 Exchange.
    
5. Compruebe la conectividad de OWA mediante lrstest5@LyncSample.com. (Anteriormente, comprobó la conectividad de OWA con el dominio en línea).
    
    Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información.
    
   > [!NOTE]
   > Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya al Shell de administración de Exchange y Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. A continuación, desencadene la sincronización de directorios. 
  
    Si desea hospedar el buzón del Sistema de sala de Skype en Exchange Online, estos pasos del Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.
    
6. Habilite la cuenta del Sistema de sala de Skype para Skype Empresarial ejecutando el siguiente cmdlet en el Shell de administración de Skype Empresarial:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning. 
  

