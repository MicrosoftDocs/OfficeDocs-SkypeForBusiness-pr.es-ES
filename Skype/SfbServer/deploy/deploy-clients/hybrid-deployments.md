---
title: Implementaciones híbridas del sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno híbrido.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219680"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implementaciones híbridas del sistema de salas de Skype

Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno híbrido.
  
## <a name="hybrid-deployments"></a>Implementaciones híbridas

Siga estos pasos si su topología tiene Skype empresarial Server y Exchange Online, y desea hospedar el buzón de recursos del sistema de salas de Skype en Exchange Online. En esta sección también se trata un escenario híbrido en el que se han implementado tanto Exchange online como Exchange Server.
  
Por motivos ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.
  
1. Cree un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net) conectándose al shell de administración de Exchange online como se describe en aprovisionamiento en línea de Exchange.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Puede comprobar la conectividad de OWA con lrstest5@LyncSample.ccsctp.net para iniciar sesión.
    
2. En Microsoft 365 o en el centro de administración de Office 365 Exchange, agregue una dirección de correo electrónico lrstest5@LyncSample.com (dominio local) y establézcalo como la dirección de respuesta.
    
3. Cree una lrstest5@LyncSample.com de usuario de Active Directory local, establezca la dirección de correo electrónico en lrstest5@LyncSample.com y establezca la dirección de destino en lrstest5@LyncSample.com.
    
4. Desencadene la sincronización de directorios y, una vez completada la sincronización, compruebe que los usuarios se fusionan en AAD y que no puede cambiar las propiedades de los recursos del destinatario en el centro de administración de Microsoft 365 o Office 365 Exchange.
    
5. Compruebe la conectividad de OWA con lrstest5@LyncSample.com. (Anteriormente, se comprobó la conectividad de OWA con el dominio en línea.)
    
    Después de crear el buzón, puede usar Set-CalendarProcessing en el shell de administración de Exchange Online para configurar el buzón. Para obtener más información, consulte los pasos 3 a 6 en implementaciones locales de un solo bosque.
    
   > [!NOTE]
   > Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya al shell de administración de Exchange y habilite-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. A continuación, desencadene la sincronización de directorios. 
  
    Si desea hospedar el buzón del sistema de salas de Skype en Exchange Online, no se requieren estos pasos del shell de administración de Exchange y puede continuar con el paso 6.
    
6. Habilite la cuenta de sistema de salas de Skype para Skype empresarial ejecutando el siguiente cmdlet en Shell de administración de Skype empresarial:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si tiene Skype empresarial online en lugar de Skype empresarial Server en el escenario anterior, después de aprovisionar el buzón de recursos de Exchange, aprovisione una cuenta de Skype empresarial como se describe en aprovisionamiento de Skype empresarial online. 
  

