---
title: Configurar la página de combinación de reuniones en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: Aprenda a configurar la página de la combinación de reuniones en Skype empresarial Server.'
ms.openlocfilehash: 30e220f2a1745aea0a77e3ec3ff491b842a2b221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283728"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurar la página de combinación de reuniones en Skype empresarial Server
 
**Resumen:** Aprenda a configurar la página de la combinación de reuniones en Skype empresarial Server.
  
Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de unirse a la reunión detecta si un cliente de Skype empresarial ya está instalado en el equipo del usuario. Si un cliente ya está instalado, el cliente se abre y se une a la reunión. Si un cliente no está instalado, el cliente de Skype empresarial se abre de forma predeterminada. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a reuniones con otras versiones del cliente. Estas opciones de configuración se han eliminado del panel de control de Skype empresarial Server, pero se configuran mediante el cmdlet Set-CsWebServiceConfiguration.
  
**Conjunto de páginas de combinación de reuniones-parámetros de CsWebServiceConfiguration**

|**Parámetro Set-CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Este parámetro ha quedado obsoleto para usarse con la versión local de Skype empresarial Server.  <br/> Si se establece en true, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Skype empresarial tendrán la oportunidad de unirse a la reunión mediante la aplicación de cliente actual. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Este parámetro ha quedado obsoleto para usarse con la versión local de Skype empresarial Server.  <br/>  Si se establece en true, las opciones alternativas para unirse a una conferencia en línea se expanden y se muestran automáticamente a los usuarios. Si se establece en falso (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismo.  <br/> |
   

