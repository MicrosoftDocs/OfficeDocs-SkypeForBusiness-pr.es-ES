---
title: Expansor de configuración del servidor de mediación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para Servidor de mediación, puede especificar lo siguiente:'
ms.openlocfilehash: b3b22cfbe4b85a237dfffbce1c22da3abde75f57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819510"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="3abb9-103">Expansor de configuración del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="3abb9-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="3abb9-104">Para **Servidor de mediación**, puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3abb9-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="3abb9-105">Si va a colocar el servidor de mediación en el grupo de servidores front-end o en el servidor Standard Edition, active la casilla de verificación Servidor de mediación combinado **habilitado.**</span><span class="sxs-lookup"><span data-stu-id="3abb9-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="3abb9-106">Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción que se deba configurar.</span><span class="sxs-lookup"><span data-stu-id="3abb9-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="3abb9-p102">Si ha habilitado la combinación del servidor de mediación, el intervalo de puertos de escucha del servidor debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto del Protocolo de control de transmisión (TCP) para el servidor de mediación combinado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la red telefónica conmutada (RTC) para saber si realmente lo necesita. De forma predeterminada, el valor de este puerto es 5068.</span><span class="sxs-lookup"><span data-stu-id="3abb9-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="3abb9-p103">Defina las puertas de enlace de RTC asociadas con el servidor de mediación combinado. Si ya ha definido puertas de enlace, se podrán asociar inmediatamente con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3abb9-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="3abb9-p104">Si tiene asociada más de una puerta de enlace con un servidor de mediación, la primera puerta de enlace que esté asociada será la predeterminada. Si debe establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Convertir en predeterminada**. Para anular la selección de la puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="3abb9-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="3abb9-117">Para obtener más información sobre cómo definir y configurar las opciones para el grupo de servidores front-end Enterprise Edition o el servidor Standard Edition, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="3abb9-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


