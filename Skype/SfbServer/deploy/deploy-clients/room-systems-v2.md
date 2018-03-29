---
title: Implementar Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este tema para obtener información acerca de los sistemas de salas de Skype v2 y cómo se integra con Exchange y Skype para Business Server 2015.
ms.openlocfilehash: 54dc3d42d406fea2bdefcac5eb726dd77fde078f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2"></a>Implementar Sistemas de salas de Skype v2
 
Lea este tema para obtener información acerca de los sistemas de salas de Skype v2 y cómo se integra con Exchange y Skype para Business Server 2015.
  
En este tema se explica cómo crear cuentas utilizadas por los sistemas de salas de Skype v2 de Microsoft Exchange y Skype para Business Server 2015. Instrucciones de implementación para dispositivos de sistemas de salas de Skype v2 se describe en [Configurar una consola de sistemas de salas de Skype v2](console.md). Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implantación en línea: entorno de la organización se implementa completamente en Office 365. Para obtener más información, vea [implementar sistemas de salas de Skype v2 con Office 365](with-office-365.md).
    
- Implementación local: su organización tiene servidores que controla, donde se hospedan Skype para Business Server 2015, Exchange y Active Directory. Para obtener más información, vea [implementar sistemas de salas de Skype v2 con Skype para Business Server 2015](with-skype-for-business-server-2015.md)
    
- Implementación híbrida: su organización tiene una mezcla de servicios, con algunas alojadas en locales y algunos alojan en línea mediante Office 365. Con sistemas de salas de Skype v2, se admiten los siguientes escenarios de híbrido: 
    
  - Exchange Online con Skype para Business Server 2015 en locales. Para obtener más información, vea [implementar sistemas de salas de Skype v2 con Exchange Online (híbrido)](with-exchange-online.md).
    
  - Exchange en instalaciones con Skype para los negocios en línea. Para obtener más información, vea [implementar sistemas de salas de Skype v2 con Exchange en las instalaciones (híbrido)](with-exchange-on-premises.md).
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Sistemas de salas de Skype v2 debe asignarse a una cuenta de usuario"" en Active Directory, Exchange y Skype para el negocio. La cuenta se utiliza para tener acceso a su calendario de reuniones y establecer Skype para conectividad de negocio. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Sistemas de salas de Skype v2 será capaz de unirse a esa reunión y proporcionar diferentes características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de usuario, no funcionará ninguna de estas características. 
  
Cada cuenta de usuario es exclusivo de un único dispositivo v2 de sistemas de salas de Skype y es necesario configurar:
  
- La cuenta de usuario se debe configurar correctamente.
    
- La infraestructura debe configurarse para permitir que los sistemas de salas de Skype v2 para validar la cuenta de usuario y para llegar a los servicios apropiados de Microsoft.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación. 
  
Una cuenta de usuario se puede considerar como la cuenta del recurso que la gente reconoce como cuenta de una conferencia de la sala o reunión del espacio. Cuando desee programar una reunión en esa sala de conferencias, invitará a la cuenta a esa reunión. Para poder utilizar sistemas de salas de Skype v2 más eficazmente, hacer lo mismo con la cuenta de usuario que se asigna a cada uno de ellos.
  
Si ya tiene una cuenta de buzón de recursos establecido para el área de encuentro de donde va a instalar sistemas de salas de Skype v2, puede cambiar esa cuenta de recurso a una cuenta de usuario. Una vez hecho esto, todo lo que necesita hacer es agregar la cuenta de usuario a un dispositivo de sistemas de salas de Skype v2. Vea los ejemplos de configuración de cuentas de usuario que se ofrecen a continuación.
  
Con una configuración adicional, es posible usar Microsoft Operations Management Suite (OMS) como se describe en la [administración de sistemas de salas de Skype Plan v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [implementar sistemas de salas de Skype v2 administración con OMS](with-oms.md)y [administrar administración remota Dispositivos de sistemas de salas de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md). 
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para una cuenta de usuario trabajar con sistemas de salas de Skype v2. Es posible que la cuenta de usuario requiera una mayor configuración.
  
|**Propiedad**|**Propósito**|
|:-----|:-----|
|Buzón de Exchange (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |Habilitando la cuenta con un buzón de Exchange, la cuenta de usuario le ofrece la capacidad para recibir y enviar correo electrónico y las convocatorias de reunión y para mostrar un calendario de reuniones en el dispositivo de los sistemas de salas de Skype v2. El buzón de sistemas de salas de Skype v2 debe ser un buzón de la sala.  <br/> |
|Skype para empresas está habilitado  <br/> |Skype para el negocio debe estar habilitado para poder utilizar distintas características de conferencia, como llamadas de vídeo, mensajería instantánea y uso compartido de pantalla. Skype para los negocios en línea y Skype para Business Server son compatibles.  <br/> |
|Habilitada con contraseña  <br/> |Debe estar habilitada la cuenta de usuario con una contraseña o no puede autenticar con Exchange o Skype para Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Si bien las propiedades para la configuración básica permitirá configurar en un entorno simple, la cuenta de usuario es posible su entorno tiene otras restricciones sobre las cuentas de directorio que deben cumplirse en orden para sistemas de salas de Skype v2 utilizar correctamente el cuenta de usuario.
  
|**Propiedad**|**Propósito**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Los certificados pueden ser necesarios para Exchange y Skype para Business Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
   
La mejor forma de configurar las cuentas de usuario es configurarlas mediante remota de Windows PowerShell. [Microsoft proporciona secuencias de comandos](https://go.microsoft.com/fwlink/?linkid=870105) que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existente tiene con el fin de ayudarle a convertirlas en cuentas de usuario de compatible con sistemas de salas de Skype v2.
  
Si prefiere usar la interfaz de usuario de Office 365 sobre los cmdlets de Windows PowerShell, pueden realizar algunos pasos manualmente. Consulte [creación de una cuenta de dispositivo mediante Office 365](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Vea también

#### 

[Plan para la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurar una consola de sistemas de salas de Skype v2](console.md)
  
[Administrar espacio de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

