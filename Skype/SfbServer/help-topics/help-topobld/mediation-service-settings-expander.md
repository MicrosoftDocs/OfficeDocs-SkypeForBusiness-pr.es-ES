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
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para Servidor de mediación, puede especificar lo siguiente:'
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215151"
---
# <a name="mediation-service-settings-expander"></a>Expansor de configuración del servidor de mediación

Para **Servidor de mediación**, puede especificar lo siguiente:

Si está combinar el servidor de mediación en el grupo de servidores front-end o el servidor Standard Edition, seleccione la casilla **servidor de mediación combinado habilitada**. Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción que se deba configurar.

Si ha habilitado la combinación del servidor de mediación, el intervalo de puertos de escucha del servidor debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto del Protocolo de control de transmisión (TCP) para el servidor de mediación combinado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la red telefónica conmutada (RTC) para saber si realmente lo necesita. De forma predeterminada, el valor de este puerto es 5068.

Defina las puertas de enlace de RTC asociadas con el servidor de mediación combinado. Si ya ha definido puertas de enlace, se podrán asociar inmediatamente con el servidor de mediación.

Si tiene asociada más de una puerta de enlace con un servidor de mediación, la primera puerta de enlace que esté asociada será la predeterminada. Si debe establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Convertir en predeterminada**. Para anular la selección de la puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**.

Para obtener información detallada sobre cómo definir y configurar las opciones del grupo de servidores front-end Enterprise Edition o del servidor Standard Edition, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


