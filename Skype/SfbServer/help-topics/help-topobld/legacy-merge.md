---
title: Combinar información heredada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El FQDN externo de las conferencias web permite a los usuarios externos unirse a reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor perimetral heredado.
ms.openlocfilehash: 19e508bdaaf44f64b3d907070d96a3691ce611c0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819692"
---
# <a name="legacy-merge"></a><span data-ttu-id="94082-104">Combinar información heredada</span><span class="sxs-lookup"><span data-stu-id="94082-104">Legacy Merge</span></span>

<span data-ttu-id="94082-105">El **FQDN externo de las conferencias web** permite a los usuarios externos unirse a reuniones locales.</span><span class="sxs-lookup"><span data-stu-id="94082-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="94082-106">Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="94082-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="94082-107">El valor de **Puerto externo de conferencias web externas** de **443** es el puerto de protocolo de inicio de sesión (SIP) del Protocolo de control de transmisión predeterminado (TCP) configurado para los clientes de conferencia.</span><span class="sxs-lookup"><span data-stu-id="94082-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="94082-108">Si no se usó el valor predeterminado, actualice el valor del **Puerto externo de las conferencias web externas** .</span><span class="sxs-lookup"><span data-stu-id="94082-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="94082-109">Seleccione la casilla **este grupo de bordes se usa para la Federación y conectividad de mensajería instantánea pública** si tiene previsto usar este servidor perimetral para la Federación.</span><span class="sxs-lookup"><span data-stu-id="94082-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="94082-110">Si tiene varios servidores perimetrales implementados, solo uno de ellos estará habilitado para la Federación.</span><span class="sxs-lookup"><span data-stu-id="94082-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="94082-111">Si no activa esta casilla y decide más tarde que desea habilitar la Federación, debe volver a ejecutar el Asistente para la combinación del generador de topología, así como publicar su topología.</span><span class="sxs-lookup"><span data-stu-id="94082-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="94082-112">Para obtener más información, consulte [fase 4: combinar topologías](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="94082-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


