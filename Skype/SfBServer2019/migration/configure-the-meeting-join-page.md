---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de reunión en una solicitud de reunión, la página de unión a la reunión detecta qué cliente ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre la aplicación web de forma predeterminada.
ms.openlocfilehash: c90e8afa95a73618eb1aa95b3d8d174e950e7e92a49988cb6146209f49cc0e58
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295127"
---
# <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

Cuando un usuario hace clic en un vínculo de reunión en una solicitud de reunión, la página de unión a la reunión detecta qué cliente ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre la aplicación web de forma predeterminada.
  
Puede modificar el comportamiento de la página de unión a la reunión si desea permitir que los usuarios se unan a reuniones. Estas opciones de configuración se han quitado del Panel de control, pero se configuran mediante el cmdlet CsWebServiceConfiguration.
  
**Parámetros de CsWebServiceConfiguration de la página para unirse a la reunión**

|**Parámetro de CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Si se establece en True, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Lync tendrán la oportunidad de unirse a la reunión. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Cuando se establece en True, las opciones alternativas para unirse a una conferencia en línea se expandirán automáticamente y se mostrarán a los usuarios. Cuando se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar la página de unión a la reunión mediante Skype Empresarial Server Shell de administración de 2019

1. Inicie el Shell de administración Skype Empresarial Server 2019: haga clic en Inicio **,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, haga clic en **Skype Empresarial Server Shell** de administración .
    
2. Ejecute el siguiente cmdlet: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Este cmdlet devuelve las opciones de configuración del servicio web.
    
3. Ejecute el siguiente comando, con los parámetros establecidos en True o False, según su preferencia (para obtener más información sobre los parámetros de este cmdlet, consulte la documentación del Shell de administración de [Skype Empresarial Server):](../../SfbServer/manage/management-shell.md)
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


