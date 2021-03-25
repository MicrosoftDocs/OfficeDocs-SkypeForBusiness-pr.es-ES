---
title: Configuración del dispositivo Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: En la página Nueva configuración de dispositivo o Editar configuración de dispositivo, puede crear o modificar una colección de configuraciones usadas para administrar Skype Empresarial Phone Edition. Estos valores le permiten configurar aspectos como el modo de seguridad requerido, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y especificar si el teléfono se bloquea automáticamente después de un periodo especificado de inactividad.
ms.openlocfilehash: b0973c73580aee3cfc81dfb79ac65613ddfcf204
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119929"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuración de dispositivo: Crear nuevos o editar los existentes
 
En la **página Nueva configuración de** dispositivo o **Editar** configuración de dispositivo, puede crear o modificar una colección de configuraciones usadas para administrar Skype Empresarial Phone Edition. Estos valores le permiten configurar aspectos como el modo de seguridad requerido, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y especificar si el teléfono se bloquea automáticamente después de un periodo especificado de inactividad.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Nueva configuración de dispositivo** o **Editar configuración de dispositivo**:
  
- Agregar una nueva configuración de dispositivo.
    
- Modificar las propiedades de una configuración de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (Global o Site) de la configuración del dispositivo.
    
- **Nombre** Puedes agregar o modificar el nombre de la configuración del dispositivo.
    
- **Seguridad SIP** Puede configurar los requisitos de transporte y autenticación para dispositivos Skype Empresarial Phone Edition. Puede seleccionar entre las siguientes opciones:
    
  - **Bajo** Permitir cualquier tipo de autorización o transporte.
    
  - **Medium** Se requiere NTLM o Kerberos para la autenticación de usuario.
    
  - **Alto** NTLM o Kerberos es necesario para la autenticación de usuario y TLS es necesario para las conexiones SIP.
    
- **Nivel de registro** Puedes habilitar el registro en el dispositivo UC. Los valores válidos son: Off; Low; Medium; and High. El valor predeterminado es Off.
    
- **Calidad de servicio de voz (QoS)** Puede especificar el valor DSCP asignado al tráfico de voz que proviene de un dispositivo Skype Empresarial Phone Edition. El valor predeterminado es 40. No obstante, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP. Para mantener la coherencia en la red, debe cambiar este valor a 46.
    
- **Bloqueo de teléfono** Puedes especificar si los teléfonos UC se bloquearán automáticamente después de un período de inactividad especificado. A continuación se incluyen los valores que puede configurar:
    
  - **Exigir el bloqueo de dispositivos** Puedes aplicar el bloqueo de dispositivos si seleccionas esta casilla.
    
  - **Longitud mínima del PIN** Puede especificar la longitud mínima del número de identificación personal (PIN) que se usa para desbloquear el teléfono. La longitud del PIN puede oscilar entre cuatro y 15 dígitos. La longitud predeterminada es de seis dígitos.
    
  - **Tiempo de espera de bloqueo de teléfono** Puede especificar el período mínimo de tiempo antes de que el teléfono se bloquee. El intervalo para el tiempo de espera va de 0 a 60 minutos; el valor predeterminado es de 10 minutos. Especifique el valor en el formato HH:MM:SS.
    
## <a name="see-also"></a>Ver también

[Configuración de dispositivos](device-configuration.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)