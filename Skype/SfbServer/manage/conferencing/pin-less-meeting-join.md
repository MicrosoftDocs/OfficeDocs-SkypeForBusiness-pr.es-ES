---
title: Configurar una reunión sin PIN en Skype Empresarial Server
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
description: 'Summary: Learn how to configure the PIN-less meeting join option in Skype for Business Server.'
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119399"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar una reunión sin PIN en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar la opción de unión a reuniones sin PIN en Skype Empresarial Server.
  
Cuando un autor de llamada de acceso telefónico intenta unirse a una reunión, el servicio de conferencia Operador automático (CAA) coloca al autor de la llamada en un lápiz de retención que es diferente del &#x2014; de la sala de espera si un moderador no está ya en una llamada y el autor de la llamada de acceso telefónico no ha escrito un PIN de líder. La opción de combinación de reuniones sin PIN permite a los autores de llamadas de acceso telefónico que se unan a una reunión sin escribir un PIN de líder incluso si son la primera persona en una llamada. 
  
Tenga en cuenta lo siguiente al configurar esta característica:
  
- Solo se aplica a reuniones privadas.
    
- Permite que los autores de llamadas RTC permanezcan en reuniones privadas sin la presencia de usuarios autenticados.
    
- Después de cambiar la configuración, se aplica a todas las reuniones privadas existentes y nuevas.
    
- Se puede habilitar en el sitio del organizador o en el nivel global.
    
- Las opciones para quién puede omitir la sala de espera se pueden establecer para cualquiera de las siguientes opciones: 
    
  - **Cualquier persona de mi organización con autores de llamadas se mete directamente**
    
  - **Cualquier persona (sin restricciones) con autores de llamadas se mete directamente** (esta es la configuración predeterminada).
    
- Cuando se configura para habilitar la unión sin PIN, el servicio CAA sigue solicitando un PIN de líder. Los usuarios pueden unirse a la reunión tanto si se introduce un PIN como si no. Sin embargo, conservar la capacidad de escribir un PIN de líder permite que un llamador de acceso telefónico se autentique como líder y administre la reunión si es necesario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar la unión a reuniones sin PIN

Para habilitar la unión a reuniones sin PIN para los usuarios, use el cmdlet [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con el parámetro AllowAnonymousPstnActivation de la siguiente manera:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por ejemplo, el siguiente comando habilita la combinación de reuniones sin PIN para el sitio Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Por motivos de seguridad, cuando la unión a reuniones sin PIN está activada, es posible que desee restringir la llamada de los usuarios anónimos al asegurarse de que ConferencingPolicy está establecido de la siguiente manera:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obtener más información, [vea Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
