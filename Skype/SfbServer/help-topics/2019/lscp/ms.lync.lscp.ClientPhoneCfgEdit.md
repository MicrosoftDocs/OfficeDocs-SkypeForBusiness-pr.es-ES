---
title: Configuración del dispositivo crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: En la página Configuración de nuevo dispositivo o configuración de dispositivo de edición, puede crear o modificar una colección de configuraciones utilizadas para administrar Skype empresarial Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo o los ajustes de calidad de servicio de voz (QoS), así como especificar si el teléfono se bloquea automáticamente después de un periodo especificado de inactividad.
ms.openlocfilehash: 772463b5816c4ce40b70be8cb38af2fee8daa0bf
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794489"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuración de dispositivo: Crear nueva o editar existente
 
En la página **configuración de nuevo dispositivo** o configuración de **dispositivo de edición** , puede crear o modificar una colección de configuraciones utilizadas para administrar Skype empresarial Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo o los ajustes de calidad de servicio de voz (QoS), así como especificar si el teléfono se bloquea automáticamente después de un periodo especificado de inactividad.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de dispositivo** o **Editar configuración de dispositivo** puede realizar las siguientes tareas:
  
- Agregar una nueva configuración de dispositivo.
    
- Modificar las propiedades de una configuración de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (global o de sitio) de la configuración del dispositivo.
    
- **Nombre** Puede Agregar o modificar el nombre de la configuración del dispositivo.
    
- **Seguridad SIP** Puede configurar los requisitos de transporte y autenticación para los dispositivos de Skype empresarial Phone Edition. Puede seleccionar entre las siguientes opciones:
    
  - **Bajo** Permitir cualquier tipo de autorización o transporte.
    
  - **Medio** Se requiere NTLM o Kerberos para la autenticación de usuario.
    
  - **Alto** Se requiere NTLM o Kerberos para la autenticación de usuario y la TLS es necesaria para las conexiones SIP.
    
- **Nivel de registro** Puede habilitar el registro en el dispositivo UC. Los valores válidos son: Desactivado, Bajo, Medio y Alto. El valor predeterminado es Desactivado.
    
- **Calidad de servicio (QoS) de voz** Puede especificar el valor de DSCP asignado al tráfico de voz que emana de un dispositivo de Skype empresarial Phone Edition. El valor predeterminado es 40. Pero, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP. Para mantener la coherencia en la red, necesita cambiar este valor a 46.
    
- **Bloqueo de teléfono** Puede especificar si los teléfonos de comunicaciones unificados se bloquearán automáticamente tras un período de inactividad especificado. A continuación se incluyen los valores que puede configurar:
    
  - **Exigir bloqueo de dispositivo** Puede exigir el bloqueo de dispositivos activando esta casilla.
    
  - **Longitud mínima del PIN** Puede especificar la longitud mínima del número de identificación personal (PIN) que se usa para desbloquear el teléfono. La longitud del PIN puede oscilar entre cuatro y 15 dígitos. La longitud predeterminada es de seis dígitos.
    
  - **Tiempo de espera de bloqueo telefónico** Puede especificar la cantidad mínima de tiempo antes de que el teléfono se bloquee por sí mismo. El intervalo para el tiempo de espera va de 0 a 60 minutos; el valor predeterminado es de 10 minutos. Especifique el valor con el formato HH:MM:SS.
    
## <a name="see-also"></a>Vea también

[Configuración de dispositivos](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
