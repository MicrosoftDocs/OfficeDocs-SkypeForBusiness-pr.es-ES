---
title: Configurar la página de unión a la reunión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: obtenga información sobre cómo configurar la página de unión a la reunión en Skype Empresarial Server.'
ms.openlocfilehash: ba90c771321732956b38f5f07af10798829fc54f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587096"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurar la página de unión a la reunión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar la página de unión a la reunión en Skype Empresarial Server.
  
Cuando un usuario hace clic en un vínculo de reunión en una solicitud de reunión, la página de unión a la reunión detecta si un cliente de Skype Empresarial ya está instalado en el equipo del usuario. Si hay uno instalado, el cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre Skype Empresarial cliente de forma predeterminada. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

Puede modificar el comportamiento de la página de unión a la reunión si desea permitir que los usuarios se unan a reuniones con otras versiones del cliente. Estas opciones de configuración se han quitado del Panel de control Skype Empresarial Server, pero se configuran mediante el cmdlet Set-CsWebServiceConfiguration configuración.
  
**Parámetros de página de Set-CsWebServiceConfiguration reunión**

|**Parámetro Set-CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Este parámetro ha quedado en desuso para su uso con la versión local de Skype Empresarial Server.  <br/> Si se establece en True, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Skype Empresarial tendrán la oportunidad de unirse a la reunión mediante su aplicación cliente actual. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Este parámetro ha quedado en desuso para su uso con la versión local de Skype Empresarial Server.  <br/>  Si se establece en True, las opciones alternativas para unirse a una conferencia en línea se expanden automáticamente y se muestran a los usuarios. Si se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.  <br/> |
   

