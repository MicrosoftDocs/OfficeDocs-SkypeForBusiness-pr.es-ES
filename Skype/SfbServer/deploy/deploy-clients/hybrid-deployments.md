---
title: Implementaciones híbridas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para aprender a implementar el sistema de sala de Skype en un entorno híbrido.
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a>Implementaciones híbridas del Sistema de salas de Skype
 
Lea este tema para aprender a implementar el sistema de sala de Skype en un entorno híbrido.
  
## <a name="hybrid-deployments"></a>Implementaciones híbridas

Si la topología tiene Skype para Business Server y Exchange Online y que desea alojar el buzón de recursos de sistema del sitio de Skype en Exchange Online, siga estos pasos. En esta sección también se tiene en cuenta un escenario híbrido donde tiene implementado tanto Exchange Online como Exchange Server.
  
Con propósitos ilustrativos, utilizamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.
  
1. Conectando con el shell de administración de Exchange en línea, como se describe en la provisión en línea de Exchange, cree un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net).
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    Puede comprobar la conectividad OWA usando lrstest5@LyncSample.ccsctp.net para iniciar la sesión.
    
2. En el centro de administración de Office 365 Exchange, agregue un correo electrónico dirección lrstest5@LyncSample.com (en prem dominio) y se establece como la dirección de respuesta.
    
3. Crear un sobre prem Active Directory usuario lrstest5@LyncSample.com, establezca la dirección de correo electrónico a lrstest5@LyncSample.com y establezca la dirección de destino a lrstest5@LyncSample.com.
    
4. Activar la sincronización de directorios y, una vez finalizada la sincronización, compruebe que los usuarios combinan en DAA y que no es posible cambiar las propiedades de los recursos del destinatario en el centro de administración de Exchange Office365.
    
5. Comprobar la conectividad OWA mediante lrstest5@LyncSample.com. (Anteriormente, usted comprobar conectividad OWA mediante el dominio en línea).
    
    Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.
    
    > [!NOTE]
    > Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya a la Shell de administración de Exchange y habilitar RemoteMailbox lrstest5@LyncSample.com RemoteRoutingAddress - lrstest5@LyncSample.mail.ccsctp.net-sala. A continuación, active la sincronización de directorios. 
  
    Si desea alojar el buzón del sistema de sala de Skype en Exchange Online, estos pasos de Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.
    
6. Habilitar la cuenta de sistema del sitio de Skype de Skype para empresas ejecutando el siguiente cmdlet en Skype de Shell de administración de negocios:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si tienes Skype para los negocios en línea en lugar de Skype para Business Server en el escenario anterior, después de crear el buzón de recursos de Exchange, aprovisionar un Skype para la cuenta de la empresa como se describe en Skype para el aprovisionamiento en línea de negocio. 
  

