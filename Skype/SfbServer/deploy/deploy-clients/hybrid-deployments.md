---
title: Implementaciones híbridas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar el sistema de sala de Skype en un entorno híbrido.
ms.openlocfilehash: 2f48707fd4e247a952bc17d26284a8a29eba025a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895176"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implementaciones híbridas del Sistema de salas de Skype

Lea este tema para obtener información sobre cómo implementar el sistema de sala de Skype en un entorno híbrido.
  
## <a name="hybrid-deployments"></a>Implementaciones híbridas

Siga estos pasos si la topología tiene Skype para Business Server y Exchange Online y desea hospedar el buzón de recursos del sistema de salas de Skype en Exchange Online. En esta sección también se tiene en cuenta un escenario híbrido donde tiene implementado tanto Exchange Online como Exchange Server.
  
Con fines ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.
  
1. Crear un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net) mediante la conexión a la consola de administración de Exchange Online tal como se describe en el aprovisionamiento en línea de Exchange.
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Puede comprobar la conectividad OWA mediante lrstest5@LyncSample.ccsctp.net para iniciar sesión.
    
2. En el centro de administración de Office 365 Exchange, agregue un correo electrónico dirección lrstest5@LyncSample.com (dominio en prem) y establézcala como la dirección de respuesta.
    
3. Crear un en prem Active Directory usuario lrstest5@LyncSample.com, establezca la dirección de correo electrónico a lrstest5@LyncSample.com y establece la dirección de destino en lrstest5@LyncSample.com.
    
4. Desencadenar la sincronización de directorios y, una vez finalizada la sincronización, compruebe que los usuarios combinar en AAD y que no es capaz de cambiar las propiedades de los recursos del destinatario en el centro de administración de Exchange Office365.
    
5. Compruebe la conectividad OWA mediante lrstest5@LyncSample.com. (Anteriormente, comprobó la conectividad de OWA con el dominio en línea).
    
    Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.
    
   > [!NOTE]
   > Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya a la consola de administración de Exchange y Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-salón. A continuación, active la sincronización de directorios. 
  
    Si desea alojar el buzón del sistema de salas de Skype en Exchange Online, estos pasos de Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.
    
6. Habilitar la cuenta del sistema de salas de Skype para Skype para la empresa, ejecute el siguiente cmdlet en Skype para Shell de administración de negocio:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si tiene Skype para profesionales en línea en lugar de Skype para Business Server en el escenario anterior, a continuación, después de aprovisionar el buzón de recursos de Exchange, aprovisionar un Skype para cuenta de la empresa tal como se describe en Skype para aprovisionamiento en línea de negocio. 
  

