---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta qué cliente ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. De forma predeterminada, si un cliente no está instalado, se abre la aplicación Web.
ms.openlocfilehash: 1bab2dff25db94b36c41e5824401777006760bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239329"
---
# <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta qué cliente ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. De forma predeterminada, si un cliente no está instalado, se abre la aplicación Web.
  
Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a las reuniones. Estas opciones de configuración se han eliminado del panel de control, pero se configuran mediante el cmdlet CsWebServiceConfiguration.
  
**Página de combinación de reuniones CsWebServiceConfiguration parámetros**

|**Parámetro CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Si se establece en true, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Lync tendrán la oportunidad de unirse a la reunión. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Si se establece en true, las opciones alternativas para unirse a una conferencia en línea se expandirán y se mostrarán automáticamente a los usuarios. Cuando se establece en false (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismo.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar la página de la combinación de reuniones con el shell de administración de Skype empresarial Server 2019

1. Inicie el shell de administración de Skype empresarial Server 2019: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.
    
2. Ejecute el siguiente cmdlet: 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    Este cmdlet devuelve los parámetros de configuración del servicio Web.
    
3. Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de su preferencia (para obtener información detallada sobre los parámetros para este cmdlet, consulte la documentación del [Shell de administración de Skype empresarial](../../SfbServer/manage/management-shell.md) ):
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


