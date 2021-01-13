---
title: Configurar la participación en reuniones sin PIN en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumen: obtenga información sobre cómo configurar la opción de participación en reuniones sin PIN en Skype Empresarial Server.'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827990"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar la participación en reuniones sin PIN en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar la opción de participación en reuniones sin PIN en Skype Empresarial Server.
  
Cuando un autor de llamada de acceso telefónico intenta unirse a una reunión, el servicio de Operador automático de conferencia (CAA) coloca al autor de la llamada en un lápiz en espera que es diferente de la sala de espera &#x2014; si un moderador no está en una llamada y el autor de la llamada de acceso telefónico no ha escrito un PIN de líder. La opción de unirse a una reunión sin PIN permite que los autores de llamadas de acceso telefónico se unan a una reunión sin escribir un PIN de líder, incluso si son la primera persona en una llamada. 
  
Tenga en cuenta lo siguiente al configurar esta característica:
  
- Solo se aplica a reuniones privadas.
    
- Permite a los autores de llamadas RTC permanecer en reuniones privadas sin la presencia de usuarios autenticados.
    
- Después de cambiar la configuración, se aplica a todas las reuniones privadas existentes y nuevas.
    
- Se puede habilitar en el sitio del organizador o en el nivel global.
    
- Las opciones para quién puede omitir la sala de espera se pueden establecer para cualquiera de las siguientes opciones: 
    
  - **Cualquier persona de mi organización con autores de llamadas se mete directamente**
    
  - **Cualquiera (sin restricciones) con** autores de llamadas se mete directamente (esta es la configuración predeterminada).
    
- Cuando se configura para habilitar la unión sin PIN, el servicio caa sigue solicitando un PIN de líder. Los usuarios pueden unirse a la reunión independientemente de si se introduce o no un PIN. Sin embargo, conservar la capacidad de especificar un PIN de líder permite que el autor de la llamada de acceso telefónico se autentique como líder y administre la reunión si es necesario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar la participación en reuniones sin PIN

Para habilitar la unión a reuniones sin PIN para los usuarios, use el cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation de la siguiente manera:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por ejemplo, el siguiente comando habilita la unión a reuniones sin PIN para el sitio Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Por motivos de seguridad, cuando se ha activado la participación en reuniones sin PIN, es posible que desee restringir la salida de los usuarios anónimos asegurándose de que ConferencingPolicy esté establecido de la siguiente manera:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obtener más información, [vea Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

