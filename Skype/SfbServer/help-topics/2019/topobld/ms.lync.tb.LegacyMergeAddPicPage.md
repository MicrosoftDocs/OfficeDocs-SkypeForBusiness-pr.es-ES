---
title: Combinar información heredada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: El FQDN externo de conferencia Web permite a los usuarios externos participar en las reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.
ms.openlocfilehash: 5402508ac733eb7a550fe4984850f8e889ae3929
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220434"
---
# <a name="legacy-merge"></a><span data-ttu-id="6efaa-104">Combinar información heredada</span><span class="sxs-lookup"><span data-stu-id="6efaa-104">Legacy Merge</span></span>

<span data-ttu-id="6efaa-105">El **FQDN externo de conferencia Web** permite a los usuarios externos participar en las reuniones locales.</span><span class="sxs-lookup"><span data-stu-id="6efaa-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="6efaa-106">Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="6efaa-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="6efaa-107">El valor de **puerto externo de conferencia Web externo** de **443** es el puerto de protocolo de inicio de sesión (SIP) de protocolo de Control de transmisión (TCP) predeterminado configurado para los clientes de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6efaa-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="6efaa-108">Si no se utilizó el valor predeterminado, actualice el valor del **puerto externo de conferencias Web externas** .</span><span class="sxs-lookup"><span data-stu-id="6efaa-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="6efaa-109">Active la casilla de verificación **grupo de servidores perimetrales esta se usa para la federación y la conectividad de mensajería instantánea pública** si piensa usar este servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="6efaa-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="6efaa-110">Si tiene varios servidores perimetrales implementados, sólo uno de ellos se habilitará para la federación.</span><span class="sxs-lookup"><span data-stu-id="6efaa-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="6efaa-111">Si no se activa esta casilla y más adelante decide que desea habilitar la federación, debe volver a ejecutar al Asistente para la combinación de generador de topología, así como publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="6efaa-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="6efaa-112">Para obtener información detallada, vea [fase 4: combinar topologías](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="6efaa-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


