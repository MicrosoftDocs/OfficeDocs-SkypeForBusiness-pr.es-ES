---
title: Configurar las cuentas para salas de equipos de Microsoft
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: Lea este tema para obtener más información sobre cómo configurar cuentas para salas de equipos de Microsoft en Exchange e Skype para la empresa.
ms.openlocfilehash: cbff055a80a156deab0446e5da08fa4fe9bb3808
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012894"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar las cuentas para salas de equipos de Microsoft
 
Lea este tema para obtener más información acerca de salas de equipos de Microsoft y cómo se integra con Exchange y Skype para la empresa.
  
En este tema se explica cómo crear las cuentas usadas por salas de equipos de Microsoft en Microsoft Exchange y Skype para la empresa. Las instrucciones de implementación para dispositivos de salas de equipos de Microsoft se describe en [Configurar una consola de salas de equipos de Microsoft](console.md). Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: entorno de su organización se implementa completamente en Office 365. Para obtener más información, vea [Implementar Microsoft los equipos locales con Office 365](with-office-365.md).
    
- Implementación local: su organización tiene servidores que controla, donde se hospedan Skype para Business Server, Exchange y Active Directory. Para obtener más información, vea [Implementar salones de los equipos de Microsoft con Skype para Business Server](with-skype-for-business-server-2015.md)
    
- Las implementaciones híbridas: su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea a través de Office 365. Con salas de equipos de Microsoft, se admiten los siguientes escenarios híbrida: 
    
  - Exchange Online con Skype para Business Server local. Para obtener más información, vea [Implementar salones de los equipos de Microsoft con Exchange Online (híbrido)](with-exchange-online.md).
    
  - Exchange local con Skype para profesionales en línea. Para obtener más información, vea [Implementar salones de los equipos de Microsoft con Exchange local (híbrido)](with-exchange-on-premises.md).
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Salones de los equipos de Microsoft debe asignarse una "cuenta de dispositivo" en Active Directory, Exchange y Skype para la empresa. La cuenta se usa para tener acceso a su calendario de reuniones y establecer Skype para la conectividad de negocio. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Salones de los equipos de Microsoft podrán unirse a esa reunión y proporcionar varias características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de dispositivo, ninguna de estas características funcionarán. 
  
Cada cuenta de dispositivo es único a un único dispositivo de salas de equipos de Microsoft y requiere algunas el programa de instalación:
  
- La cuenta del dispositivo debe configurarse correctamente.
    
- La infraestructura debe configurarse para permitir que los salones de los equipos de Microsoft para validar la cuenta del dispositivo y ponerse en contacto con los servicios de Microsoft apropiados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación. 
  
Una cuenta de dispositivo se puede considerar como la cuenta del recurso que personas reconocen como cuenta de una conferencia de la sala o reunión del espacio. Cuando desee programar una reunión en esa sala de conferencias, invitará a la cuenta a esa reunión. Para poder usar salones de los equipos de Microsoft de manera más eficaz, hace lo mismo con la cuenta del dispositivo que se asigna a cada uno de ellos.
  
Si ya tiene una cuenta de buzón de recursos establecer para el espacio de reunión donde está instalando salones de los equipos de Microsoft, puede cambiar esa cuenta del recurso en una cuenta de dispositivo. Una vez que se realiza, todo lo que necesita hacer es agregar la cuenta del dispositivo a un dispositivo de salas de equipos de Microsoft. Consulte los ejemplos de dispositivo cuenta el programa de instalación proporcionados a continuación.
  
Con una configuración adicional, es posible usar el Monitor de Azure de Microsoft como se describe en [administración de planeación de salas de equipos de Microsoft con el Monitor de Azure](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [administración de implementación de salas de equipos de Microsoft con el Monitor de Azure](azure-monitor.md)y [administración remota Administrar dispositivos de salas de equipos de Microsoft con el Monitor de Azure](../../manage/skype-room-systems-v2/azure-monitor.md). 
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para una cuenta de dispositivo para que funcione con Microsoft los equipos locales. Su cuenta de dispositivo puede ser necesario el programa de instalación.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Buzón de Exchange (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |Habilitar la cuenta con un buzón de Exchange, la cuenta del dispositivo le proporciona la capacidad para recibir y enviar correo y las convocatorias de reunión y para mostrar un calendario de reuniones en el dispositivo de salas de equipos de Microsoft. El buzón de correo de salas de equipos de Microsoft debe ser un buzón de sala.  <br/> |
|Skype para la empresa está habilitado  <br/> |Skype para la empresa debe estar habilitado para poder usar distintas características de conferencia, como las llamadas de vídeo, mensajería instantánea y uso compartido de pantalla. Skype para profesionales en línea y Skype para Business Server son compatibles.  <br/> |
|Habilitada con contraseña  <br/> |La cuenta del dispositivo debe estar habilitada con una contraseña, o no se puede autenticar con Exchange o Skype para Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Mientras que las propiedades para la configuración básica permitirá la cuenta del dispositivo a establecerse en un entorno simple, es posible que su entorno tiene otras restricciones en las cuentas de Active directory que se deben cumplir en orden para salas de equipos de Microsoft usar de forma correcta el cuenta del dispositivo.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Los certificados pueden ser necesarios para Exchange y Skype para Business Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
   
La forma más sencilla de configurar las cuentas de dispositivo es configurarlas mediante Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de dispositivo o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de dispositivos compatibles con salas de equipos de Microsoft.
  
Si prefiere usar la interfaz de usuario de Office 365 a través de los cmdlets de Windows PowerShell, pueden realizar manualmente algunos pasos. Consulte [creación de una cuenta de dispositivo con Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Consulte también

[Plan para salas de equipos de Microsoft](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurar una consola de salas de equipos de Microsoft](console.md)
  
[Administrar las salas de equipos de Microsoft](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

