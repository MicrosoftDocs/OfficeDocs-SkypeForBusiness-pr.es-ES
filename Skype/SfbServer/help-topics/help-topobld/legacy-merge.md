---
title: Combinar información heredada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El FQDN externo de conferencia Web permite a los usuarios externos participar en las reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.
ms.openlocfilehash: b67ea667f2b354f7981d3bc289e63b0cf8b4e704
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888579"
---
# <a name="legacy-merge"></a><span data-ttu-id="bbbce-104">Combinar información heredada</span><span class="sxs-lookup"><span data-stu-id="bbbce-104">Legacy Merge</span></span>

<span data-ttu-id="bbbce-105">El **FQDN externo de conferencia Web** permite a los usuarios externos participar en las reuniones locales.</span><span class="sxs-lookup"><span data-stu-id="bbbce-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="bbbce-106">Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="bbbce-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="bbbce-107">El valor de **puerto externo de conferencia Web externo** de **443** es el puerto de protocolo de inicio de sesión (SIP) de protocolo de Control de transmisión (TCP) predeterminado configurado para los clientes de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bbbce-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="bbbce-108">Si no se utilizó el valor predeterminado, actualice el valor del **puerto externo de conferencias Web externas** .</span><span class="sxs-lookup"><span data-stu-id="bbbce-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="bbbce-109">Active la casilla de verificación **grupo de servidores perimetrales esta se usa para la federación y la conectividad de mensajería instantánea pública** si piensa usar este servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="bbbce-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="bbbce-110">Si tiene varios servidores perimetrales implementados, sólo uno de ellos se habilitará para la federación.</span><span class="sxs-lookup"><span data-stu-id="bbbce-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="bbbce-111">Si no se activa esta casilla y más adelante decide que desea habilitar la federación, debe volver a ejecutar al Asistente para la combinación de generador de topología, así como publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="bbbce-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="bbbce-112">Para obtener información detallada, vea [fase 4: combinar topologías](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbbce-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


