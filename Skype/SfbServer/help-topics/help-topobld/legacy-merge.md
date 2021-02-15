---
title: Combinar información heredada
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El nombre de dominio completo externo de conferencia web permite a los usuarios externos participar de reuniones locales. Especifique el nombre de dominio completo (FQDN) de la interfaz externa de la conferencia web del servidor perimetral heredado.
ms.openlocfilehash: b49d8ed17bdc56050e00216c5506b85db2b1d3aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833000"
---
# <a name="legacy-merge"></a><span data-ttu-id="d14c0-104">Combinar información heredada</span><span class="sxs-lookup"><span data-stu-id="d14c0-104">Legacy Merge</span></span>

<span data-ttu-id="d14c0-p102">El **nombre de dominio completo externo de conferencia web** permite a los usuarios externos participar de reuniones locales. Especifique el nombre de dominio completo (FQDN) de la interfaz externa de la conferencia web del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="d14c0-p102">The **Web Conferencing external FQDN** permits external users to join on-premises meetings. Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="d14c0-p103">El valor de **Puerto de conferencia web externo** de **443** es el puerto TCP (protocolo de control de transmisión) de SIP (protocolo de inicio de sesión) predeterminado para clientes de conferencia. Si no se usó el valor predeterminado, actualice el valor de **Puerto de conferencia web externo**.</span><span class="sxs-lookup"><span data-stu-id="d14c0-p103">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients. If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="d14c0-109">Marque la casilla que indica que **este grupo de servidores perimetrales se usa para federación y conectividad de IM pública** si tiene previsto usar este servidor perimetral para federación.</span><span class="sxs-lookup"><span data-stu-id="d14c0-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="d14c0-110">Si tiene implementados varios servidores perimetrales, solo se habilitará uno de ellos para la federación.</span><span class="sxs-lookup"><span data-stu-id="d14c0-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="d14c0-111">Si no marca esta casilla y más adelante decide que desea habilitar la federación, es necesario volver a ejecutar el asistente de Topology Builder, además de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="d14c0-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="d14c0-112">Para obtener información detallada, consulte [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="d14c0-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


