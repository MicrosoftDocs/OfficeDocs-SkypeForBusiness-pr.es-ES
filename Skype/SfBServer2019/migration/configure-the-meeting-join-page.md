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
description: Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta el cliente que ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre de forma predeterminada la aplicación Web.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754030"
---
# <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta el cliente que ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre de forma predeterminada la aplicación Web.
  
Puede modificar el comportamiento de la página de participación en la reunión si desea permitir que los usuarios se unan a reuniones. Estas opciones de configuración se han quitado del panel de control, pero puede configurarlas mediante el cmdlet CsWebServiceConfiguration.
  
**Parámetros de CsWebServiceConfiguration de la página para unirse a la reunión**

|**Parámetro de CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|Showjoinusinglegacyclientlink establecidos  <br/> |Si se establece en true, los usuarios que se unan a una reunión con una aplicación cliente distinta de Lync tendrán la oportunidad de unirse a la reunión. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Cuando se establece en true, las opciones alternativas para unirse a una conferencia en línea se expanden automáticamente y se muestran a los usuarios. Cuando se establece en false (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar la página de participación en la reunión con el shell de administración de Skype empresarial Server 2019

1. Inicie el shell de administración de Skype empresarial Server 2019: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
2. Ejecute el siguiente cmdlet: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Este cmdlet devuelve las opciones de configuración del servicio web.
    
3. Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de sus preferencias (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación del [Shell de administración de Skype empresarial Server](../../SfbServer/manage/management-shell.md) ):
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


