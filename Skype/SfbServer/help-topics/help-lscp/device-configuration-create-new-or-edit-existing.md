---
title: Configuración de dispositivo crear nuevo o editar existente
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: En la página Configuración de dispositivo nuevo o editar la configuración del dispositivo, puede crear o modificar una colección de valores utilizados para administrar Skype para Business Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y, asimismo, especificar si el teléfono se bloquea automáticamente después de un periodo de inactividad específico.
ms.openlocfilehash: c6d8f291b6602ad41ca2942e2d4b507d2727bcd1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuración de dispositivo: Crear nueva o editar existente
 
En la página **Configuración de dispositivo nuevo** o **Editar la configuración del dispositivo** , puede crear o modificar una colección de valores utilizados para administrar Skype para Business Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y, asimismo, especificar si el teléfono se bloquea automáticamente después de un periodo de inactividad específico.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de dispositivo** o **Editar configuración de dispositivo** puede realizar las siguientes tareas:
  
- Agregar una nueva configuración de dispositivo.
    
- Modificar las propiedades de una configuración de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito de aplicación** Identifica el ámbito (Global o sitio) de la configuración del dispositivo.
    
- **Nombre** Puede agregar o modificar el nombre de la configuración del dispositivo.
    
- **Seguridad de SIP** Puede configurar los requisitos de autenticación y transporte para Skype para dispositivos Business Phone Edition. Puede seleccionar entre las siguientes opciones:
    
  - **Bajo** Permitir a cualquier tipo de autorización o de transporte.
    
  - **Medio** Es necesario para la autenticación de usuario NTLM o Kerberos.
    
  - **Alta** Se requiere autenticación de usuario NTLM o Kerberos y se requiere TLS para las conexiones SIP.
    
- **Nivel de registro** Puede habilitar el registro en el dispositivo de comunicaciones unificadas. Los valores válidos son: Desactivado, Bajo, Medio y Alto. El valor predeterminado es Desactivado.
    
- **Voz de calidad de servicio (QoS)** Puede especificar el valor DSCP asignado al tráfico de voz que emana de un Skype para dispositivo Business Phone Edition. El valor predeterminado es 40. Pero, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP. Para mantener la coherencia en la red, necesita cambiar este valor a 46.
    
- **Bloqueo del teléfono** Puede especificar si se permite o no UC teléfonos bloquearán automáticamente a sí mismos después de un período especificado de inactividad. A continuación se incluyen los valores que puede configurar:
    
  - **Exigir el bloqueo de dispositivo** Puede exigir el dispositivo de bloqueo activando esta casilla de verificación.
    
  - **Longitud de PIN mínimo** Puede especificar la longitud mínima para el número de identificación personal (PIN) que se utiliza para desbloquear el teléfono. La longitud del PIN puede oscilar entre cuatro y 15 dígitos. La longitud predeterminada es de seis dígitos.
    
  - **Tiempo de espera de bloqueo de teléfono** Puede especificar la longitud mínima de tiempo antes de los bloqueos de teléfono propio. El intervalo para el tiempo de espera va de 0 a 60 minutos; el valor predeterminado es de 10 minutos. Especifique el valor con el formato HH:MM:SS.
    
## <a name="see-also"></a>Vea también

#### 

[Configuración del dispositivo](device-configuration.md)
#### 

[Conjunto de CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

