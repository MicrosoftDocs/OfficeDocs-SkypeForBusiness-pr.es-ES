---
title: Implementaciones híbridas del Sistema de salas de Skype
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
ms.openlocfilehash: 3fe92990fa80f938d078c92624232a289b5f8621
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768973"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implementaciones híbridas del Sistema de salas de Skype

Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno híbrido.
  
## <a name="hybrid-deployments"></a>Implementaciones híbridas

Siga estos pasos si su topología tiene Skype empresarial Server y Exchange Online, y quiere hospedar el buzón de recursos del sistema de salas de Skype en Exchange Online. En esta sección también se tiene en cuenta un escenario híbrido donde tiene implementado tanto Exchange Online como Exchange Server.
  
Por motivos ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.
  
1. Para crear un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net), conéctese al shell de administración de Exchange online como se describe en aprovisionamiento de Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Puede comprobar la conectividad de OWA con lrstest5@LyncSample.ccsctp.net para iniciar sesión.
    
2. En el centro de administración de Office 365 de Exchange, agregue una dirección de correo electrónico lrstest5@LyncSample.com (dominio local) y establézcalo como la dirección de respuesta.
    
3. Cree una lrstest5@LyncSample.com de usuario de Active Directory local, establezca la dirección de correo electrónico en lrstest5@LyncSample.com y establezca la dirección de destino en lrstest5@LyncSample.com.
    
4. Desencadene la sincronización de directorios y, una vez completada la sincronización, compruebe que los usuarios se fusionan en AAD y que no puede cambiar las propiedades de los recursos del destinatario en el centro de administración de Exchange de Office365.
    
5. Comprobar la conectividad de OWA con lrstest5@LyncSample.com. (Anteriormente, comprobó la conectividad de OWA con el dominio en línea).
    
    Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.
    
   > [!NOTE]
   > Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya al shell de administración de Exchange y habilite-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. A continuación, active la sincronización de directorios. 
  
    Si desea hospedar el buzón del sistema de Skype Room en Exchange Online, estos pasos del shell de administración de Exchange no son necesarios y puede continuar con el paso 6.
    
6. Habilite la cuenta del sistema de Skype Room para Skype empresarial ejecutando el siguiente cmdlet en el shell de administración de Skype empresarial:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si tiene Skype empresarial online en lugar de Skype empresarial Server en el escenario anterior, después de aprovisionar el buzón de recursos de Exchange, aprovisione una cuenta de Skype empresarial, tal y como se describe en Skype empresarial online aprovisionamiento. 
  

