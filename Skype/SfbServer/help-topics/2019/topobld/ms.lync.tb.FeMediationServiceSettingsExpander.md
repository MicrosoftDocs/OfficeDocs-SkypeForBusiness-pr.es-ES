---
title: Expansor de configuración del servidor de mediación
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para Servidor de mediación, puede especificar lo siguiente:'
ms.openlocfilehash: 649f4ac74280564fc53182b9bf627f566781c2eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850233"
---
# <a name="mediation-service-settings-expander"></a>Expansor de configuración del servidor de mediación

Para **Servidor de mediación**, puede especificar lo siguiente:

Si va a colocar el servidor de mediación en el grupo de servidores front-end o en el servidor Standard Edition, active la casilla Servidor de mediación combinado **habilitado**. Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción que se deba configurar.

Si ha habilitado la combinación del servidor de mediación, el intervalo de puertos de escucha del servidor debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto del Protocolo de control de transmisión (TCP) para el servidor de mediación combinado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la red telefónica conmutada (RTC) para saber si realmente lo necesita. De forma predeterminada, el valor de este puerto es 5068.

Defina las puertas de enlace de RTC asociadas con el servidor de mediación combinado. Si ya ha definido puertas de enlace, se podrán asociar inmediatamente con el servidor de mediación.

Si tiene asociada más de una puerta de enlace con un servidor de mediación, la primera puerta de enlace que esté asociada será la predeterminada. Si debe establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Convertir en predeterminada**. Para anular la selección de la puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**.

Para obtener más información sobre cómo definir y configurar las opciones del grupo de servidores front-end de Enterprise Edition o el servidor Standard Edition, vea [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).