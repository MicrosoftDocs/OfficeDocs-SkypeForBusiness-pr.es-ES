---
title: Configurar unión a la reunión sin PIN para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumen: Aprenda a configurar la opción de unión de reunión sin PIN en Skype empresarial Server.'
ms.openlocfilehash: 5b8ad452f54785a916ac70acd468458215135934
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991795"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar unión a la reunión sin PIN para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar la opción de unión de reunión sin PIN en Skype empresarial Server.
  
Cuando un autor de llamada de acceso telefónico intenta unirse a una reunión, el servicio operador automático de la Conferencia (CAA) coloca al autor de la llamada en un lápiz que es diferente al de la sala de espera &#x2014; si aún no está en una llamada, y si la persona que llama de acceso telefónico no ha entrado en un PIN de línea directriz. La opción de unión a una reunión sin PIN permite que los autores de llamadas de acceso telefónico local puedan unirse a una reunión sin indicar un PIN de líder incluso si son la primera persona en una llamada. 
  
Tenga en cuenta lo siguiente al configurar esta característica:
  
- Solo se aplica a reuniones privadas.
    
- Permite que los autores de llamadas RTC permanezcan en reuniones privadas sin la presencia de usuarios autenticados.
    
- Después de cambiar la opción, se aplica a todas las reuniones privadas existentes y nuevas.
    
- Puede activarse en el sitio del organizador o a nivel global.
    
- Se pueden establecer opciones para personas que pueden omitir la sala de espera en los casos siguientes: 
    
  - **Cualquier persona de mi organización con autores de llamada entran directamente**
    
  - **Cualquier persona (sin restricciones) con autores de llamada entran directamente** (Este es el valor predeterminado).
    
- Al configurar la habilitación de la unión sin pin, el servicio CAA solicitará un PIN de líder. Los usuarios pueden unirse a la reunión dispongan o no del PIN. Sin embargo, mantener la posibilidad de introducir un PIN de relleno permite a una persona que llama de acceso telefónico autenticar como un líder y administrar la reunión si es necesario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar la unión a reuniones sin PIN

Para habilitar la combinación de reuniones sin PIN para los usuarios, use el cmdlet [set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation de la siguiente manera:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por ejemplo, el comando siguiente habilita la unión a reuniones sin PIN para el sitio Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Por motivos de seguridad, cuando se activa la unión a reuniones sin PIN, es posible que quiera restringir que los usuarios anónimos accedan por aceptación de llamada asegurándose de que ConferencingPolicy está configurado de la siguiente forma:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obtener más información, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

