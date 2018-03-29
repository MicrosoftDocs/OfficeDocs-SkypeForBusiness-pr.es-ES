---
title: Configurar la reunión página join en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: Aprender a configurar la reunión página join en Skype para Business Server 2015.'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a>Configurar la reunión página join en Skype para Business Server 2015
 
**Resumen:** Aprenda a configurar la reunión página join en Skype para Business Server 2015.
  
Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la reunión página combinación detecta si un Skype para Business client ya está instalado en el equipo del usuario. Si un cliente ya está instalado, el cliente se abre y une a la reunión. Si un cliente no está instalado, de forma predeterminada la versión 2015 de Skype para Business client abre. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar la reunión página de combinación

Puede modificar el comportamiento de la combinación de reunión si desea permitir que los usuarios puedan unirse a reuniones con otras versiones del cliente de la página. Estas opciones de configuración se han quitado de la Skype para Panel de Control de servidor empresarial, pero configurarlos mediante el cmdlet Set-CsWebServiceConfiguration.
  
**Parámetros de CsWebServiceConfiguration de conjunto página unirse a reuniones**

|**Parámetro del conjunto de CsWebServiceConfiguration**|**Descripción**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Este parámetro está desusado para su uso con la versión local de Skype para Business Server 2015.  <br/> Si se establece en True, unirse a una reunión mediante una aplicación de cliente distinto de Skype para empresas se ofrecerá la oportunidad de incorporarse a la reunión mediante su aplicación de cliente actual. El valor predeterminado es False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Este parámetro está desusado para su uso con la versión local de Skype para Business Server 2015.  <br/>  Si se establece en True, alternativo opciones para unirse a una conferencia en línea se expande y muestra a los usuarios automáticamente. Si se establece en False (valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.  <br/> |
   

