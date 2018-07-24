---
title: Configuración de la reunión de la página de participación en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: Obtenga información sobre cómo configurar la reunión página de participación en Skype para Business Server.'
ms.openlocfilehash: 7574dee341e0226a6a6e2ee8c77cdfb2353beb5a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977617"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configuración de la reunión de la página de participación en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo configurar la reunión página de participación en Skype para Business Server.
  
Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión de la página de participación detecta si un Skype para Business client ya está instalado en el equipo del usuario. Si un cliente ya está instalado, el cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada la Skype para la empresa cliente se abre. 
  
## <a name="configure-the-meeting-join-page"></a>Configuración de la reunión de la página de participación

Puede modificar el comportamiento de la participación en reuniones de página si desea permitir que los usuarios puedan unirse a reuniones con otras versiones del cliente. Estas opciones de configuración se han quitado de la Skype para el Panel de Control de servidor empresarial, pero configurarlas mediante el cmdlet Set-CsWebServiceConfiguration.
  
**Parámetros de Set-CsWebServiceConfiguration de página unirse a la reunión**

|**Parámetro SET-CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Este parámetro ha quedado obsoleto para su uso con la versión local de Skype Business Server.  <br/> Si establecido en True, los usuarios unirse a una reunión mediante el uso de una aplicación cliente distinto de Skype para la empresa se le dará la oportunidad de unirse a la reunión mediante el uso de su aplicación de cliente actual. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Este parámetro ha quedado obsoleto para su uso con la versión local de Skype Business Server.  <br/>  Si se establece en True, alternativa opciones para unirse a una conferencia en línea se amplían automáticamente y se muestra a los usuarios. Si se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones para sí mismos.  <br/> |
   

