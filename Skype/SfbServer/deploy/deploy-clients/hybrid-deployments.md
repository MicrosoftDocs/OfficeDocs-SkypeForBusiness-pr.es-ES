---
title: Skype Implementaciones híbridas del sistema de sala
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar Skype room system en un entorno híbrido.
ms.openlocfilehash: caebf77f0ef5abb2b56c64446ad04a052d8f98f9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841952"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Implementaciones híbridas del sistema de sala

Lea este tema para obtener información sobre cómo implementar Skype room system en un entorno híbrido.
  
## <a name="hybrid-deployments"></a>Implementaciones híbridas

Siga estos pasos si la topología tiene Skype Empresarial Server y Exchange Online y desea hospedar el buzón de recursos del sistema de Skype en Exchange Online. En esta sección también se trata un escenario híbrido en el que se Exchange Online y Exchange Server implementación.
  
Para fines ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.
  
1. Cree un buzón de recursos en Exchange centro de administración (LyncSample.ccsctp.net) conectándose al shell de administración de Exchange Online como se describe en Exchange Online Provisioning.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Puede comprobar la conectividad de OWA lrstest5@LyncSample.ccsctp.net para iniciar sesión.
    
2. En el centro de administración Microsoft 365 o Office 365 Exchange, agregue una dirección de correo electrónico lrstest5@LyncSample.com (dominio local) y estadóla como la dirección de respuesta.
    
3. Cree una dirección de usuario de Active Directory local lrstest5@LyncSample.com, establezca la dirección de correo electrónico en lrstest5@LyncSample.com y establezca la dirección de destino en lrstest5@LyncSample.com.
    
4. Desencadene la sincronización de directorios y, una vez completada la sincronización, compruebe que los usuarios se combinan en AAD y que no puede cambiar las propiedades de los recursos del destinatario en el centro de administración de Microsoft 365 o Office 365 Exchange.
    
5. Compruebe la conectividad de OWA mediante lrstest5@LyncSample.com. (Anteriormente, ha comprobado la conectividad de OWA con el dominio en línea).
    
    Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell Exchange Online administración para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información.
    
   > [!NOTE]
   > Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya al Shell de administración de Exchange y Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. A continuación, desencadene la sincronización de directorios. 
  
    Si desea hospedar el buzón de Skype Room System en Exchange Online, estos pasos del Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.
    
6. Habilite la cuenta Skype room system para Skype Empresarial mediante la ejecución del siguiente cmdlet en Skype Empresarial Shell de administración:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si ha Skype Empresarial Online en lugar de Skype Empresarial Server en el escenario anterior, después de aprovisionar el buzón de recursos de Exchange, aprovisione una cuenta Skype Empresarial como se describe en Skype Empresarial Online Aprovisionamiento. 
  

