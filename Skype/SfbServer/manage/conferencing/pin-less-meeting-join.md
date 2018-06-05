---
title: Configurar unión a la reunión sin PIN para Skype Empresarial Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumen: Obtenga información sobre cómo configurar el PIN-menor opción de unión en Skype para Business Server 2015 de la reunión.'
ms.openlocfilehash: 375c008cd8cec072e9d2b71de1765756e4c0f881
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569344"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar unión a la reunión sin PIN para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar el PIN-menor opción de unión en Skype para Business Server 2015 de la reunión.
  
Cuando un autor de la llamada telefónico intenta unirse a una reunión, el servicio de operador automático de conferencia (CAA) coloca el autor de la llamada en una pluma de explotación que es diferente de la sala de espera & #x 2014; Si un moderador no está ya en una llamada y el autor de marcado en la llamada no ha entrado un responsable de PIN. La opción de unión a una reunión sin PIN permite que los autores de llamadas de acceso telefónico local puedan unirse a una reunión sin indicar un PIN de líder incluso si son la primera persona en una llamada. 
  
Tenga en cuenta lo siguiente al configurar esta característica:
  
- Solo se aplica a reuniones privadas.
    
- Permite que los autores de llamadas RTC permanezcan en reuniones privadas sin la presencia de usuarios autenticados.
    
- Después de cambiar la opción, se aplica a todas las reuniones privadas existentes y nuevas.
    
- Puede activarse en el sitio del organizador o a nivel global.
    
- Se pueden establecer opciones para personas que pueden omitir la sala de espera en los casos siguientes: 
    
  - **Cualquier persona de mi organización con autores de llamada entran directamente**
    
  - **Cualquier persona (sin restricciones) con autores de llamada entran directamente** (Este es el valor predeterminado).
    
- Al configurar la habilitación de la unión sin pin, el servicio CAA solicitará un PIN de líder. Los usuarios pueden unirse a la reunión dispongan o no del PIN. Sin embargo, conservar la capacidad de escribir un PIN de coordinador permite que un llamador telefónico autenticar como coordinador y administrar la reunión si es necesario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar la unión a reuniones sin PIN

Para habilitar la participación en la reunión de menor de PIN para los usuarios, utilice el cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation como se indica a continuación:
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por ejemplo, el comando siguiente habilita la unión a reuniones sin PIN para el sitio Redmond:
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Por motivos de seguridad, cuando se activa la unión a reuniones sin PIN, es posible que quiera restringir que los usuarios anónimos accedan por aceptación de llamada asegurándose de que ConferencingPolicy está configurado de la siguiente forma:
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obtener más información, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

