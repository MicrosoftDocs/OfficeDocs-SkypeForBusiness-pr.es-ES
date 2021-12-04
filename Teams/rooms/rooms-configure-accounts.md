---
title: Configurar cuentas para Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo configurar cuentas para Salas de Microsoft Teams en Exchange y Skype Empresarial.
ms.openlocfilehash: 77e1dbe097bbb75697ec52ef7d472df4707ac9cb
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306125"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar cuentas para Salas de Microsoft Teams
 
Lea este tema para obtener información sobre Salas de Microsoft Teams y cómo se integra con Exchange y Skype Empresarial.
  
En este tema se presenta cómo crear cuentas usadas por Salas de Microsoft Teams en Microsoft Exchange y Skype Empresarial. Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: el entorno de su organización se implementa por completo en Microsoft 365 o Office 365. Para obtener más información, vea [Implementar Salas de Microsoft Teams con Microsoft 365 o Office 365](with-office-365.md).
    
- Implementación local: su organización tiene servidores que controla, donde active directory, Exchange y Skype Empresarial Server están hospedados. Para obtener más información, [vea Implementar Salas de Microsoft Teams con Skype Empresarial Server](with-skype-for-business-server-2015.md)
    
- Implementaciones híbridas: su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea a través de Microsoft 365 o Office 365. Con Salas de Microsoft Teams, se admiten los siguientes escenarios híbridos:
    
  - Exchange Online con Skype Empresarial Server local. Para obtener más información, vea [Implementar Salas de Microsoft Teams con Exchange Online (híbrido).](with-exchange-online.md)
    
  - Exchange local con Microsoft Teams. Para obtener más información, vea [Implementar Salas de Microsoft Teams con Exchange local (híbrido).](with-exchange-on-premises.md)
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Salas de Microsoft Teams debe asignarse una "cuenta de recursos" en Active Directory, Exchange y Skype Empresarial. La cuenta se usa para obtener acceso a su calendario de reuniones y establecer Microsoft Teams o Skype Empresarial conectividad. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Salas de Microsoft Teams podrá unirse a esa reunión y proporcionar varias características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de recursos, ninguna de estas características funcionará. 
  
Cada cuenta de recurso es única para una sola instalación Salas de Microsoft Teams y requiere una configuración:
  
- La cuenta de recursos debe configurarse correctamente.
    
- La infraestructura debe configurarse para permitir a Salas de Microsoft Teams validar la cuenta de recursos y para llegar a las servicios Microsoft.

> [!NOTE] 
> Si usa Microsoft Teams paneles, la cuenta Salas de Teams de recursos inicia sesión tanto en Salas de Teams como en los paneles Teams asociados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación.
> 

En entornos híbridos, la cuenta usada para Salas de Microsoft Teams debe tener habilitada la sincronización de contraseñas en Azure Active Directory (AAD) Sync porque Salas de Microsoft Teams autenticación requiere Microsoft 365 o Office 365 autenticación. Al configurar la cuenta, asegúrese de que la dirección SIP de la cuenta coincida con su nombre principal de usuario (UPN) en AAD. 
  
Puede pensar en una cuenta de recursos como la cuenta de recursos que los usuarios reconocen como cuenta de una sala de conferencias o de espacio compartido. Cuando desee programar una reunión con ese espacio, invite a la cuenta a esa reunión.
  
Si ya tiene una cuenta de buzón de recursos configurada para el espacio donde va a instalar Salas de Microsoft Teams, puede cambiar esa cuenta a una cuenta de Salas de Teams recursos. Una vez que haya terminado, todo lo que necesita hacer es iniciar sesión en Salas de Microsoft Teams con esa cuenta.
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para que una cuenta de recursos funcione con Salas de Microsoft Teams. Es posible que su cuenta de recursos requiera una configuración adicional.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Exchange buzón (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |Habilitar la cuenta con un buzón de Exchange proporciona a la cuenta de recursos la capacidad de recibir y enviar tanto solicitudes de correo como de reunión, así como para mostrar un calendario de reuniones en el Salas de Microsoft Teams dispositivo. El Salas de Microsoft Teams debe ser un buzón de sala.  <br/> |
|Skype Empresarial está habilitado  <br/> |Skype Empresarial se puede habilitar para usar varias Skype Empresarial de conferencia, como videollamadas, mensajería instantánea y uso compartido de pantalla.  <br/> |
|Habilitada con contraseña  <br/> |La cuenta de recurso debe estar habilitada con una contraseña o no puede autenticarse con Microsoft Teams, Exchange o Skype Empresarial Server. La expiración de la contraseña debe deshabilitarse en todas Salas de Teams de recursos.   <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Aunque las propiedades de la configuración básica permitirán configurar la cuenta de recursos en un entorno sencillo, es posible que su entorno tenga otras restricciones en las cuentas de directorio que deben cumplirse para que Salas de Microsoft Teams use correctamente la cuenta de recursos.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Es posible que se requieran certificados para Exchange y Skype Empresarial Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |
  
## <a name="see-also"></a>Vea también

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)
