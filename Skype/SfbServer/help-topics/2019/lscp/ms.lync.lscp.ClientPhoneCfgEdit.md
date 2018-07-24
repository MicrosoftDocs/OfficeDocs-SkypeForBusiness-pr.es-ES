---
title: Configuración de dispositivo crear nuevos o editar los existentes
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: En la página Configuración de dispositivo nuevo o editar configuración de dispositivo, puede crear o modificar una colección de opciones que se usan para administrar Skype para Business Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y, asimismo, especificar si el teléfono se bloquea automáticamente después de un periodo de inactividad específico.
ms.openlocfilehash: 9e91313db84a870ef4f85105ddf2b2138d8948aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997933"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuración de dispositivo: Crear nueva o editar existente
 
En la página **Configuración de dispositivo nuevo** o **Editar configuración de dispositivo** , puede crear o modificar una colección de opciones que se usan para administrar Skype para Business Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y, asimismo, especificar si el teléfono se bloquea automáticamente después de un periodo de inactividad específico.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de dispositivo** o **Editar configuración de dispositivo** puede realizar las siguientes tareas:
  
- Agregar una nueva configuración de dispositivo.
    
- Modificar las propiedades de una configuración de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (Global o sitio) de la configuración de dispositivo.
    
- **Nombre** Puede agregar o modificar el nombre de la configuración de dispositivo.
    
- **Seguridad SIP** Puede configurar los requisitos de transporte y autenticación de Skype para dispositivos Business Phone Edition. Puede seleccionar entre las siguientes opciones:
    
  - **Baja** Permitir a cualquier tipo de autorización o transporte.
    
  - **Medio** NTLM o Kerberos es necesario para la autenticación de usuario.
    
  - **Alta** NTLM o Kerberos es necesario para la autenticación de usuario y se requiere TLS para conexiones SIP.
    
- **Nivel de registro** Puede habilitar el registro en el dispositivo de comunicaciones unificadas. Los valores válidos son: Desactivado, Bajo, Medio y Alto. El valor predeterminado es Desactivado.
    
- **Calidad de voz del servicio (QoS)** Puede especificar el valor DSCP asignado para el tráfico de voz procedentes de un Skype para dispositivo Business Phone Edition. El valor predeterminado es 40. Pero, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP. Para mantener la coherencia en la red, necesita cambiar este valor a 46.
    
- **Bloqueo del teléfono** Puede especificar si o no teléfonos de comunicaciones unificadas se bloquearán de forma automática a sí mismos después de un período de inactividad especificado. A continuación se incluyen los valores que puede configurar:
    
  - **Exigir el bloqueo de dispositivos** Puede aplicar el bloqueo mediante la selección de esta casilla de verificación del dispositivo.
    
  - **Longitud mínima de PIN** Puede especificar la longitud mínima para el número de identificación personal (PIN) que se utiliza para desbloquear el teléfono. La longitud del PIN puede oscilar entre cuatro y 15 dígitos. La longitud predeterminada es de seis dígitos.
    
  - **Tiempo de espera de bloqueo de teléfono** Puede especificar la longitud mínima de tiempo antes de los bloqueos de teléfono propio. El intervalo para el tiempo de espera va de 0 a 60 minutos; el valor predeterminado es de 10 minutos. Especifique el valor con el formato HH:MM:SS.
    
## <a name="see-also"></a>Vea también

[Configuración de dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)