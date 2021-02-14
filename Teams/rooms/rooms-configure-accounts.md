---
title: Configurar cuentas de Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo configurar las cuentas de salas de Microsoft Teams en Exchange y Skype Empresarial.
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662525"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar cuentas de Salas de Microsoft Teams
 
Lea este tema para obtener información sobre salas de Microsoft Teams y cómo se integra con Exchange y Skype Empresarial.
  
Este tema presenta cómo crear cuentas usadas por salas de Microsoft Teams en Microsoft Exchange y Skype Empresarial. Las instrucciones de implementación para dispositivos de Salas de Microsoft Teams se tratan [en Configurar una consola de Salas de Microsoft Teams.](console.md) Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: el entorno de su organización se implementa completamente en Microsoft 365 u Office 365. Para obtener más información, [vea Implementar salas de Microsoft Teams con Microsoft 365 u Office 365.](with-office-365.md)
    
- Implementación local: la organización tiene servidores que controla, donde se hospedan Active Directory, Exchange y Skype Empresarial Server. Para obtener más información, vea [Implementar salas de Microsoft Teams con Skype Empresarial Server](with-skype-for-business-server-2015.md)
    
- Implementaciones híbridas: su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea a través de Microsoft 365 u Office 365. Con Salas de Microsoft Teams, se admiten los siguientes escenarios híbridos:
    
  - Exchange Online con Skype Empresarial Server local. Para obtener más información, vea [Implementar salas de Microsoft Teams con Exchange Online (híbrido).](with-exchange-online.md)
    
  - Exchange local con Microsoft Teams o Skype Empresarial Online. Para obtener más información, vea [Implementar salas de Microsoft Teams con Exchange local (híbrido).](with-exchange-on-premises.md)
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Los salas de Microsoft Teams deben tener asignada una "cuenta de dispositivo" en Active Directory, Exchange y Skype Empresarial. La cuenta se usa para acceder a su calendario de reuniones y establecer la conectividad de Microsoft Teams o Skype Empresarial. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Los salas de Microsoft Teams podrán unirse a la reunión y proporcionar diversas características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de dispositivo, ninguna de estas características funcionará. 
  
Cada cuenta de dispositivo es única a un único dispositivo de Salas de Microsoft Teams y requiere alguna configuración:
  
- La cuenta del dispositivo debe estar configurada correctamente.
    
- Su infraestructura debe configurarse para permitir que Salas de Microsoft Teams valide la cuenta del dispositivo y llegue a los servicios Microsoft adecuados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación. 

En entornos híbridos, la cuenta que se usa para los salas de Microsoft Teams debe tener habilitada la sincronización de contraseñas en Sincronización de Azure Active Directory (AAD) porque la autenticación de Salas de Microsoft Teams requiere autenticación de Microsoft 365 u Office 365. Al configurar la cuenta, asegúrese de que la dirección SIP de la cuenta coincida con el nombre principal de usuario (UPN) en AAD. 
  
Puede pensar en una cuenta de dispositivo como la cuenta de recursos que los usuarios reconocen como cuenta de una sala de conferencias o un espacio de reunión. Cuando desee programar una reunión en esa sala de conferencias, invitará a la cuenta a esa reunión. Para usar los salas de Microsoft Teams de la manera más eficaz, haga lo mismo con la cuenta de dispositivo que se asigna a cada uno de ellos.
  
Si ya tiene una cuenta de buzón de recursos configurada para el espacio de reunión donde va a instalar Salas de Microsoft Teams, puede cambiar esa cuenta de recurso a una cuenta de dispositivo. Una vez que haya terminado, todo lo que debe hacer es agregar la cuenta del dispositivo a un dispositivo de Microsoft Teams Rooms. Vea los ejemplos de configuración de la cuenta de dispositivo que se proporcionan a continuación.
  
Con la configuración adicional, la administración remota es posible con Microsoft Azure Monitor, como se describe en Planear la administración de salas de Microsoft Teams con [Azure Monitor,](azure-monitor-plan.md)Implementar la administración de salas de Microsoft Teams con [Azure Monitor](azure-monitor-deploy.md)y administrar dispositivos de Salas de Microsoft Teams con Azure [Monitor.](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para que una cuenta de dispositivo funcione con Microsoft Teams Rooms. Es posible que la cuenta del dispositivo requiera una configuración más avanzada.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Buzón de Exchange (Exchange 2013 SP1 o versiones posteriores, o Exchange Online)  <br/> |Habilitar la cuenta con un buzón de Exchange proporciona a la cuenta del dispositivo la capacidad de recibir y enviar solicitudes de correo y de reuniones, así como de mostrar un calendario de reuniones en el dispositivo de Salas de Microsoft Teams. El buzón de Salas de Microsoft Teams debe ser un buzón de sala.  <br/> |
|Skype Empresarial está habilitado  <br/> |Skype Empresarial debe estar habilitado para poder usar varias características de conferencia, como videollamadas, mensajería instantánea y pantalla compartida. Se admiten Tanto Skype Empresarial Online como Skype Empresarial Server.  <br/> |
|Habilitada con contraseña  <br/> |La cuenta del dispositivo debe estar habilitada con una contraseña o no se puede autenticar con Exchange o Skype Empresarial Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Aunque las propiedades de la configuración básica permitirán configurar la cuenta del dispositivo en un entorno sencillo, es posible que su entorno tenga otras restricciones en las cuentas de directorio que deben cumplirse para que Microsoft Teams Rooms pueda usar correctamente la cuenta del dispositivo.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Es posible que se requieran certificados para Exchange y Skype Empresarial Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
   
La manera más sencilla de configurar las cuentas de dispositivo es configurarlas con cuentas de Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de dispositivo o validar las cuentas de recursos existentes que tiene para poder ayudarle a convertirlas en cuentas de dispositivo compatibles con Salas de Microsoft Teams.
  
Si prefiere usar la interfaz de usuario de Microsoft 365 u Office 365 Windows PowerShell cmdlets, algunos pasos se pueden realizar manualmente. Consulte [Crear una cuenta de dispositivo con Microsoft 365 u Office 365.](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Consulte también

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

