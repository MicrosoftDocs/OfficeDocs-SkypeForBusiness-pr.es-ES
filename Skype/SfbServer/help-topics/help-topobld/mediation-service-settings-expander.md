---
title: Expansor de configuración del servidor de mediación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Puede especificar lo siguiente en relación con un servidor de mediación:'
ms.openlocfilehash: e6b89c61e84577af86576850f5c675861cfa3a80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819562"
---
# <a name="mediation-service-settings-expander"></a>Expansor de configuración del servidor de mediación

Puede especificar lo siguiente en relación con un **servidor de mediación**:

Si collocating el servidor de mediación en el grupo de servidores front-end o el servidor Standard Edition, seleccione la casilla **servidor de mediación**con el que se ha habilitado. Si decide no collocater el servidor de mediación, no hay ninguna configuración que se pueda definir en esta sección.

Si ha habilitado la collocation del servidor de mediación, debe definir el intervalo de puertos de escucha en el servidor para seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos consultar los requisitos de la puerta de enlace o los de la RTC para saber si esto es realmente necesario. El valor de este puerto es 5068 de forma predeterminada.

Las puertas de enlace RTC se definen con el servidor de mediación de anuncios. Si ya ha definido las puertas de enlace, estarán disponibles para asociarlas con el servidor de mediación.

Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la predeterminada. Si necesita establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Establecer como predeterminado**. Para anular la selección de la puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.

Para obtener detalles sobre la definición y configuración de la configuración del grupo de servidores front-end Enterprise Edition o del servidor Standard Edition, consulte [definir y configurar la topología](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [implementar servidores de mediación y definir pares](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


