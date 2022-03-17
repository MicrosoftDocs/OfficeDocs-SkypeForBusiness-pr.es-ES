---
title: Configurar cuentas para Salas de Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: Lea este tema para obtener información sobre cómo configurar cuentas para Salas de Microsoft Teams (incluidos Surface Hub) y teléfonos de área común.
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514735"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar cuentas para Salas de Microsoft Teams
 
En este tema se presenta cómo crear cuentas usadas por Salas de Microsoft Teams. Es probable que su infraestructura esté incluida en una de las siguientes configuraciones:
  
- Implementación en línea: el entorno de su organización se implementa por completo en Microsoft 365 o Office 365.
    
- Implementación local: su organización tiene servidores que controla, donde active directory, Exchange y Skype Empresarial Server están hospedados. Para obtener más información, [vea Implementar Salas de Microsoft Teams con Skype Empresarial Server](with-skype-for-business-server-2015.md)
    
- Implementaciones híbridas: su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea a través de Microsoft 365 o Office 365. Con Salas de Microsoft Teams, se admiten los siguientes escenarios híbridos:
    
  - Exchange Online con Skype Empresarial Server local.
    
  - Exchange local con Microsoft Teams.
    
La configuración que tenga influirá en la forma de preparar la configuración del dispositivo.
  
Salas de Microsoft Teams tener una "cuenta de recursos" en Active Directory, Exchange y (si es necesario) Skype Empresarial. La cuenta se usa para obtener acceso al calendario de la reunión y establecer Microsoft Teams y/o Skype Empresarial de reuniones. Los usuarios pueden programar una reunión con esta cuenta y de esta manera reservarla. Salas de Microsoft Teams podrá unirse a esa reunión y proporcionar varias características a los asistentes a la reunión.
  
> [!IMPORTANT]
> Sin una cuenta de recursos, ninguna de estas características funcionará.
  
Todas las cuentas de recursos son únicas para una única Salas de Microsoft Teams instalación.
  
- La cuenta de recursos debe configurarse correctamente.
    
- La infraestructura debe configurarse para permitir que Salas de Microsoft Teams la cuenta de recursos y que llegue a las servicios Microsoft.

> [!NOTE] 
> Si usa Microsoft Teams paneles, la cuenta Salas de Teams de recursos inicia sesión tanto en Salas de Teams como en los paneles Teams asociados.
    
> [!IMPORTANT]
> Es recomendable crear la cuenta mucho antes de instalar el hardware. Idealmente, la preparación de la cuenta debe comenzar de dos a tres semanas antes de la instalación.
> 
En entornos híbridos que no usan Skype Empresarial, se recomienda crear la cuenta de forma nativa en Azure Active Directory. Si la cuenta debe crearse con Active Directory local, la sincronización de contraseñas debe estar habilitada en una sincronización Azure Active Directory (AAD) Conectar porque Salas de Microsoft Teams autenticación requiere Microsoft 365 o Office 365  autenticación. Al configurar la cuenta, asegúrese de que la dirección de correo electrónico de la cuenta coincida con su nombre principal de usuario (UPN) en AAD. 
  
Puede pensar en una cuenta de recursos como la cuenta que los usuarios reconocen como el nombre del espacio compartido o de una sala de conferencias. Cuando desee programar una reunión con ese espacio, invite a la cuenta de recursos a esa reunión.
  
Si ya tiene una cuenta de buzón de Exchange de recursos configurada para el espacio donde va a instalar Salas de Microsoft Teams, puede cambiar esa cuenta a una cuenta de Salas de Teams recurso. Una vez que haya terminado, todo lo que tiene que hacer es iniciar sesión Salas de Microsoft Teams con esa cuenta.
  
## <a name="basic-configuration"></a>Configuración básica

Estas propiedades representan la configuración mínima para que una cuenta de recursos funcione con Salas de Microsoft Teams. Es posible que su cuenta de recursos requiera una configuración adicional.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Exchange buzón (Exchange 2013 SP1 o posterior, o Exchange Online)  <br/> |El Exchange de correo electrónico proporciona a la cuenta de recursos la capacidad de recibir y enviar solicitudes de correo y reunión, y para mostrar un calendario de reunión en Salas de Microsoft Teams. El Salas de Microsoft Teams de correo debe ser un buzón de recursos de tipo "sala".  <br/> |
|Skype Empresarial está habilitado  <br/> |Skype Empresarial se puede habilitar para usar varias Skype Empresarial de conferencia, como videollamadas, mensajería instantánea y uso compartido de pantalla.  <br/> |
|Habilitada con contraseña  <br/> |La cuenta de recursos debe estar habilitada con una contraseña o no puede autenticarse con Microsoft Teams, Exchange o Skype Empresarial Server. La expiración de la contraseña debe estar deshabilitada en todas Salas de Teams de recursos.   <br/> |
   
## <a name="advanced-configuration"></a>Configuración avanzada

Aunque las propiedades de la configuración básica permitirán que la cuenta de recursos se configure en un entorno sencillo, es posible que su entorno tenga otras restricciones en las cuentas que deben cumplirse para que Salas de Microsoft Teams use correctamente la cuenta de recursos.
  
|**Propiedad**|**Finalidad**|
|:-----|:-----|
|Autenticación basada en certificados  <br/> |Es posible que se requieran certificados para Exchange y Skype Empresarial Server. Para implementar certificados, puede cargarlos cuando haya iniciado sesión como administrador.  <br/> |

## <a name="see-also"></a>Vea también

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)
