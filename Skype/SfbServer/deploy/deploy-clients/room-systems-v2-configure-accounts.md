---
title: Configurar cuentas para sistemas de salón de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ''
description: Lea este tema para obtener más información sobre cómo configurar cuentas para sistemas de salón de Skype v2 en Exchange e Skype para Business Server 2015.
ms.openlocfilehash: 0514d1b542e8fa53f7210992d5cb219f7e9a7719
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="configure-accounts-for-skype-room-systems-v2"></a>Configurar cuentas para sistemas de salón de Skype v2
 
Lea este tema para obtener más información acerca de sistemas de salón de Skype v2 y cómo se integra con Exchange y Skype para Business Server 2015.
  
En este tema se explica cómo crear las cuentas usadas por v2 de sistemas de salón de Skype en Microsoft Exchange y Skype para Business Server 2015. Las instrucciones de implementación para dispositivos de sistemas de salón de Skype v2 se aborda en [Configure una consola de v2 de sistemas de salón de Skype](console.md). Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: entorno de su organización se implementa completamente en Office 365. Para obtener más información, vea [implementar sistemas de salón de Skype v2 con Office 365](with-office-365.md).
    
- Implementación local: su organización tiene servidores que controla, donde se hospedan Active Directory, Exchange y Skype para Business Server 2015. Para obtener más información, vea [implementar sistemas de salón de Skype v2 con Skype para Business Server 2015](with-skype-for-business-server-2015.md)
    
- Implementación híbrida: su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea a través de Office 365. Con sistemas de salas de Skype v2, se admiten los siguientes escenarios híbrida: 
    
  - Exchange Online con Skype para Business Server 2015 local. Para obtener más información, vea [implementar sistemas de salón de Skype v2 con Exchange Online (híbrido)](with-exchange-online.md).
    
  - Exchange local con Skype para profesionales en línea. Para obtener más información, vea [implementar sistemas de salón de Skype v2 con Exchange local (híbrido)](with-exchange-on-premises.md).
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Sistemas de salón de Skype v2 debe asignarse una "cuenta de usuario" en Active Directory, Exchange y Skype para la empresa. La cuenta se usa para tener acceso a su calendario de reuniones y establecer Skype para la conectividad de negocio. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Sistemas de salón de Skype v2 podrán unirse a esa reunión y proporcionar varias características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de usuario, no funcionará ninguna de estas características. 
  
Cada cuenta de usuario es único a un único dispositivo v2 de sistemas de salón de Skype y requiere algunas el programa de instalación:
  
- La cuenta de usuario se debe configurar correctamente.
    
- La infraestructura debe configurarse para permitir que los sistemas de la sala de Skype v2 para validar la cuenta de usuario y ponerse en contacto con los servicios de Microsoft apropiados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación. 
  
Una cuenta de usuario se puede considerar como la cuenta del recurso que personas reconocen como cuenta de una conferencia de la sala o reunión del espacio. Cuando desee programar una reunión en esa sala de conferencias, invitará a la cuenta a esa reunión. Para poder usar sistemas de salón de Skype v2 más eficaz, hace lo mismo con la cuenta de usuario que se asigna a cada uno de ellos.
  
Si ya tiene una cuenta de buzón de recursos establecer para el espacio de reunión donde va a instalar sistemas de salón de Skype v2, puede cambiar esa cuenta del recurso en una cuenta de usuario. Una vez que se realiza, todo lo que necesita hacer es agregar la cuenta de usuario a un dispositivo de v2 de sistemas de salón de Skype. Vea los ejemplos de configuración de cuentas de usuario que se ofrecen a continuación.
  
Con una configuración adicional, es posible mediante el conjunto de aplicaciones de administración de operaciones de Microsoft (OMS) tal como se describe la [administración de sistemas de planeación de las salas Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), implementar sistemas de salón de Skype v2 con OMS y la [administración](with-oms.md)de [administrar administración remota Dispositivos de sistemas de salón de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md). 
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para una cuenta de usuario trabajar con sistemas de salas de Skype v2. Es posible que la cuenta de usuario requiera una mayor configuración.
  
|**Propiedad**|**Propósito**|
|:-----|:-----|
|Buzón de Exchange (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |Habilitar la cuenta con un buzón de Exchange proporciona a la cuenta de usuario la capacidad para recibir y enviar correo y las convocatorias de reunión y para mostrar un calendario de reuniones en el dispositivo de v2 de sistemas de salón de Skype. El buzón de correo de sistemas de salón de Skype v2 debe ser un buzón de sala.  <br/> |
|Skype para la empresa está habilitado  <br/> |Skype para la empresa debe estar habilitado para poder usar distintas características de conferencia, como las llamadas de vídeo, mensajería instantánea y uso compartido de pantalla. Skype para profesionales en línea y Skype para Business Server son compatibles.  <br/> |
|Habilitada con contraseña  <br/> |Se debe habilitar la cuenta de usuario con una contraseña, o no se puede autenticar con Exchange o Skype para Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Mientras que las propiedades para la configuración básica permitirá la cuenta de usuario se puede configurar en un entorno simple, es posible que su entorno tiene otras restricciones en las cuentas de Active directory que se deben cumplir en orden para sistemas de salón de Skype v2 usar de forma correcta el cuenta de usuario.
  
|**Propiedad**|**Propósito**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Los certificados pueden ser necesarios para Exchange y Skype para Business Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
   
Es la mejor forma de configurar las cuentas de usuario configurarlos con Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](room-systems-v2-scripts.md), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de usuario de v2 de Skype salón sistemas compatibles.
  
Si prefiere usar la interfaz de usuario de Office 365 a través de los cmdlets de Windows PowerShell, pueden realizar manualmente algunos pasos. Consulte [creación de una cuenta de dispositivo con Office 365](https://technet.microsoft.com/itpro/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Vea también

#### 

[Planeación de la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurar una consola de v2 de sistemas de salón de Skype](console.md)
  
[Administración de salón de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

