---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión detecta de la página de participación de cliente que ya esté instalado en el equipo del usuario. Si ya está instalado un cliente, que el cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada que se abre la aplicación Web.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879943"
---
# <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión detecta de la página de participación de cliente que ya esté instalado en el equipo del usuario. Si ya está instalado un cliente, que el cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada que se abre la aplicación Web.
  
Puede modificar el comportamiento de la participación en reuniones de página si desea permitir a los usuarios participar en reuniones. Estas opciones de configuración se han quitado del Panel de Control, pero se configuran mediante el cmdlet de CsWebServiceConfiguration.
  
**Parámetros CsWebServiceConfiguration de la página unirse a la reunión**

|**Parámetro CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Si se establece en True, los usuarios unirse a una reunión mediante el uso de una aplicación de cliente que no sea Lync se le dará la oportunidad de unirse a la reunión. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Cuando se establece en True, se alternan las opciones para unirse a una conferencia en línea automáticamente que se expande y se muestra a los usuarios. Cuando se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones para sí mismos.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar la reunión mediante el uso de Skype para Shell de administración de Business Server 2019 la página de participación

1. Iniciar el Skype para Shell de administración de Business Server 2019: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
2. Ejecute el siguiente cmdlet: 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    Este cmdlet devuelve la configuración del servicio de la web.
    
3. Ejecute el siguiente comando, con el conjunto de parámetros en True o False, según su preferencia (para obtener información detallada sobre los parámetros de este cmdlet, vea la documentación de [Skype para Business Server Management Shell](../../SfbServer/manage/management-shell.md) ):
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


