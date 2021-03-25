---
title: Configurar cuentas para salas de Microsoft Teams
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
description: Lea este tema para obtener información sobre cómo configurar cuentas para salas de Microsoft Teams en Exchange y Skype Empresarial.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117478"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar cuentas para salas de Microsoft Teams
 
Lea este tema para obtener información sobre salas de Microsoft Teams y cómo se integra con Exchange y Skype Empresarial.
  
En este tema se presenta cómo crear cuentas usadas por Salas de Microsoft Teams en Microsoft Exchange y Skype Empresarial. Las instrucciones de implementación para dispositivos Microsoft Teams Rooms se tratan [en Configurar una consola de Salas de Microsoft Teams.](console.md) Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: el entorno de su organización se implementa por completo en Microsoft 365 u Office 365. Para obtener más información, vea [Implementar salas de Microsoft Teams con Microsoft 365 u Office 365.](with-office-365.md)
    
- Implementación local: su organización tiene servidores que controla, donde se hospedan Active Directory, Exchange y Skype Empresarial Server. Para obtener más información, vea [Implementar salas de Microsoft Teams con Skype Empresarial Server](with-skype-for-business-server-2015.md)
    
- Implementaciones híbridas: su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea a través de Microsoft 365 u Office 365. Con Salas de Microsoft Teams, se admiten los siguientes escenarios híbridos:
    
  - Exchange Online con Skype Empresarial Server local. Para obtener más información, vea [Implementar salas de Microsoft Teams con Exchange Online (híbrido).](with-exchange-online.md)
    
  - Exchange local con Microsoft Teams o Skype Empresarial Online. Para obtener más información, vea [Implementar salas de Microsoft Teams con Exchange local (híbrido).](with-exchange-on-premises.md)
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Microsoft Teams Rooms debe tener asignada una "cuenta de dispositivo" en Active Directory, Exchange y Skype Empresarial. La cuenta se usa para acceder a su calendario de reuniones y establecer la conectividad de Microsoft Teams o Skype Empresarial. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Microsoft Teams Rooms podrá unirse a esa reunión y proporcionar varias características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de dispositivo, ninguna de estas características funcionará. 
  
Cada cuenta de dispositivo es única para un único dispositivo de Salas de Microsoft Teams y requiere una configuración:
  
- La cuenta del dispositivo debe estar configurada correctamente.
    
- La infraestructura debe configurarse para permitir que Microsoft Teams Rooms valide la cuenta del dispositivo y llegue a los servicios de Microsoft adecuados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación. 

En entornos híbridos, la cuenta usada para salas de Microsoft Teams debe tener habilitada la sincronización de contraseñas en Azure Active Directory (AAD) Sync porque la autenticación de Salas de Microsoft Teams requiere autenticación de Microsoft 365 u Office 365. Al configurar la cuenta, asegúrese de que la dirección SIP de la cuenta coincida con su nombre principal de usuario (UPN) en AAD. 
  
Puede pensar en una cuenta de dispositivo como la cuenta de recursos que los usuarios reconocen como cuenta de una sala de conferencias o espacio de reunión. Cuando desee programar una reunión en esa sala de conferencias, invitará a la cuenta a esa reunión. Para usar salas de Microsoft Teams de forma más eficaz, haga lo mismo con la cuenta de dispositivo asignada a cada uno de ellos.
  
Si ya tiene una cuenta de buzón de recursos configurada para el espacio de reunión donde va a instalar Salas de Microsoft Teams, puede cambiar esa cuenta de recursos a una cuenta de dispositivo. Una vez que haya terminado, todo lo que tiene que hacer es agregar la cuenta del dispositivo a un dispositivo de Salas de Microsoft Teams. Vea los ejemplos de configuración de la cuenta de dispositivo que se proporcionan a continuación.
  
Con una configuración adicional, la administración remota es posible con Microsoft Azure Monitor, como se describe en Planear la administración de salas de Microsoft Teams con [Azure Monitor,](azure-monitor-plan.md)Implementar la administración de salas de Microsoft Teams con [Azure Monitor](azure-monitor-deploy.md)y Administrar dispositivos de Salas de Microsoft Teams con Azure [Monitor.](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para que una cuenta de dispositivo funcione con Salas de Microsoft Teams. Es posible que tu cuenta de dispositivo requiera una configuración adicional.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Buzón de Exchange (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |Habilitar la cuenta con un buzón de Exchange proporciona a la cuenta del dispositivo la capacidad de recibir y enviar tanto solicitudes de correo como de reunión, así como para mostrar un calendario de reuniones en el dispositivo Salas de Microsoft Teams. El buzón salas de Microsoft Teams debe ser un buzón de sala.  <br/> |
|Skype Empresarial está habilitado  <br/> |Skype Empresarial debe estar habilitado para poder usar varias características de conferencia, como videollamadas, mensajería instantánea y uso compartido de pantalla. Tanto Skype Empresarial Online como Skype Empresarial Server son compatibles.  <br/> |
|Habilitada con contraseña  <br/> |La cuenta del dispositivo debe estar habilitada con una contraseña o no puede autenticarse con Exchange o Skype Empresarial Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Aunque las propiedades de la configuración básica permitirán configurar la cuenta del dispositivo en un entorno sencillo, es posible que su entorno tenga otras restricciones en las cuentas de directorio que deben cumplirse para que salas de Microsoft Teams puedan usar correctamente la cuenta del dispositivo.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Es posible que se requieran certificados para Exchange y Skype Empresarial Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
   
La forma más sencilla de configurar las cuentas de dispositivo es configurarlas mediante la configuración Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de dispositivo o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de dispositivos de Salas de Microsoft Teams compatibles.
  
Si prefiere usar la interfaz de usuario de Microsoft 365 u Office 365 Windows PowerShell cmdlets, puede realizar algunos pasos manualmente. Consulte [Crear una cuenta de dispositivo con Microsoft 365 u Office 365.](/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Vea también

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)