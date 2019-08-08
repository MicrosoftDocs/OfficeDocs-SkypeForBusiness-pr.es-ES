---
title: Configurar cuentas para salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo configurar cuentas para salas de Microsoft Teams en Exchange y Skype empresarial.
ms.openlocfilehash: 30e887aa09b9013c3db18fb33133d11c639f9fe8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243327"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar cuentas para salas de Microsoft Teams
 
Lea este tema para obtener información sobre las salas de Microsoft Teams y sobre cómo se integra con Exchange y Skype empresarial.
  
En este tema se presenta cómo crear cuentas usadas por salas de Microsoft Teams en Microsoft Exchange y Skype empresarial. Las instrucciones de implementación para los dispositivos de salas de Microsoft Teams se tratan en [configurar una consola de salas de Microsoft Teams](console.md). Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: el entorno de la organización se implementa completamente en Office 365. Para obtener más información, consulte [implementar salas de Microsoft Teams con Office 365](with-office-365.md).
    
- Implementación local: su organización tiene servidores que controla, en los que se hospedan Active Directory, Exchange y Skype empresarial Server. Para obtener más información, consulte [implementar salas de Microsoft Teams con Skype empresarial Server](with-skype-for-business-server-2015.md)
    
- Implementaciones híbridas: su organización tiene una combinación de servicios, algunos locales hospedados y algunos hospedados en línea a través de Office 365. Con las salas de Microsoft Teams, se admiten los siguientes escenarios híbridos: 
    
  - Exchange Online con Skype empresarial Server local. Para obtener más información, consulte [implementar salas de Microsoft Teams con Exchange Online (implementación híbrida)](with-exchange-online.md).
    
  - Exchange local con Microsoft Teams o Skype empresarial online. Para obtener más información, consulte [implementar salas de Microsoft Teams con Exchange local (híbrido)](with-exchange-on-premises.md).
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Las salas de Microsoft Teams deben tener asignada una "cuenta de dispositivo" en Active Directory, Exchange y Skype empresarial. La cuenta se usa para acceder al calendario de reuniones y para establecer la conectividad de Microsoft Teams o Skype empresarial. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Las salas de Microsoft Teams podrán unirse a esa reunión y proporcionar diversas características a los asistentes de la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de dispositivo, no funcionará ninguna de estas características. 
  
Cada cuenta de dispositivo es única para un único dispositivo de salas de Microsoft Teams y requiere cierta configuración:
  
- La cuenta del dispositivo debe estar configurada correctamente.
    
- La infraestructura debe estar configurada para permitir que las salas de Microsoft Teams validen la cuenta del dispositivo y puedan comunicarse con los servicios de Microsoft apropiados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación. En entornos híbridos, la cuenta usada para salas de Microsoft Teams debe tener la sincronización de contraseña habilitada en AAD Sync porque la autenticación de salas de Microsoft Teams requiere la autenticación de Office 365.
  
Puede pensar en una cuenta de dispositivo como la cuenta de recursos que las personas reconocen como una cuenta de sala de conferencias o de un espacio de reunión. Cuando desee programar una reunión en esa sala de conferencias, invitará a la cuenta a esa reunión. Para usar las salas de Microsoft Teams de manera más eficaz, haga lo mismo con la cuenta del dispositivo asignada a cada una de ellas.
  
Si ya tiene configurada una cuenta de buzón de recursos para el espacio de reunión en el que está instalando salas de Microsoft Teams, puede cambiar esa cuenta de recursos a una cuenta de dispositivo. Una vez que haya terminado, todo lo que tiene que hacer es agregar la cuenta de dispositivo a un dispositivo de salas de Microsoft Teams. Consulte los ejemplos de configuración de la cuenta de dispositivo proporcionados a continuación.
  
Con la configuración adicional, la administración remota puede usar Microsoft Azure monitor tal como se describe en [planear la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-plan.md), [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md)y [ Administrar dispositivos de salas de Microsoft Teams con el monitor de Azure](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para que una cuenta de dispositivo funcione con salas de Microsoft Teams. Es posible que la cuenta del dispositivo requiera una configuración adicional.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Buzón de Exchange (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |Si habilita la cuenta con un buzón de Exchange, la cuenta del dispositivo tendrá la capacidad de recibir y enviar solicitudes de correo y de reunión, así como de mostrar un calendario de reuniones en el dispositivo de salas de Microsoft Teams. El buzón de Microsoft Team Rooms debe ser un buzón de sala.  <br/> |
|Skype empresarial está habilitado  <br/> |Skype empresarial debe estar habilitado para poder usar varias características de conferencia, como las videollamadas, la mensajería instantánea y el uso compartido de pantalla. Se admiten tanto Skype empresarial online como Skype empresarial Server.  <br/> |
|Habilitada con contraseña  <br/> |La cuenta del dispositivo debe estar habilitada con una contraseña o no se puede autenticar con Exchange ni con Skype empresarial Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Aunque las propiedades de la configuración básica permiten configurar la cuenta del dispositivo en un entorno simple, es posible que el entorno tenga otras restricciones en las cuentas de directorio que deben cumplirse para que las salas de Microsoft Teams usen correctamente el cuenta del dispositivo.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Es posible que se necesiten certificados para Exchange y Skype empresarial Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
   
La manera más fácil de configurar las cuentas de dispositivo es configurarlas con Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de dispositivos, o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de dispositivos de salas de Microsoft Teams compatibles.
  
Si prefiere usar la interfaz de usuario de Office 365 sobre cmdlets de Windows PowerShell, algunos pasos se pueden realizar manualmente. Vea [crear una cuenta de dispositivo con Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Vea también

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)
  
[Configurar una consola de salas de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

