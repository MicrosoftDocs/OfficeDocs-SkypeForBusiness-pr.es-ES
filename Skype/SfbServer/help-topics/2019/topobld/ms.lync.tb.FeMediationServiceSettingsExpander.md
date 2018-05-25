---
title: Expansor de configuración del servidor de mediación
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para el servidor de mediación, puede especificar lo siguiente:'
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="mediation-service-settings-expander"></a>Expansor de configuración del servidor de mediación
 
Puede especificar lo siguiente en relación con un **servidor de mediación**:
  
Si está combinando el servidor de mediación en el grupo de servidores Front-End o el servidor Standard Edition, active la casilla de verificación **servidor de mediación combinado habilitado**. Si decide no instalar el servidor de mediación, no hay ninguna configuración arquitectónico en esta sección. 
  
Si ha habilitado la colocación del servidor de mediación, debe definir el intervalo de puertos de escucha en el servidor de seguridad de capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos consultar los requisitos de la puerta de enlace o los de la RTC para saber si esto es realmente necesario. El valor de este puerto es 5068 de forma predeterminada.
  
Definir las puertas de enlace de RTC que están asociados con el servidor de mediación combinado. Si ya se han definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación. 
  
Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la puerta de enlace predeterminada. Si necesita establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Establecer como predeterminado**. Para anular la selección de la puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.
  
Para obtener información detallada sobre cómo definir y configurar las opciones para el servidor Standard Edition o grupo de servidores Front-End de Enterprise Edition, consulte [definir y configurar la topología](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).
  

