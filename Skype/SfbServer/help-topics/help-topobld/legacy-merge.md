---
title: Combinación heredado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El FQDN externo de conferencias Web permite a los usuarios externos puedan unirse a reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor de borde heredada.
ms.openlocfilehash: 09bba6fa5532e85572a1272fde59dc0a1f7a9c1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="legacy-merge"></a><span data-ttu-id="c0129-104">Combinación heredado</span><span class="sxs-lookup"><span data-stu-id="c0129-104">Legacy Merge</span></span>
 
<span data-ttu-id="c0129-105">El **FQDN externo de conferencias Web** permite a los usuarios externos puedan unirse a reuniones locales.</span><span class="sxs-lookup"><span data-stu-id="c0129-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="c0129-106">Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor de borde heredada.</span><span class="sxs-lookup"><span data-stu-id="c0129-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>
  
<span data-ttu-id="c0129-107">El valor de **puerto externo de conferencias Web externas** de **443** es el puerto de protocolo de inicio de sesión (SIP) de protocolo de Control de transmisión (TCP) predeterminado configurado para los clientes de conferencias.</span><span class="sxs-lookup"><span data-stu-id="c0129-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="c0129-108">Si no se utilizó el valor predeterminado, actualizar el valor de **puerto externo de conferencias Web externas** .</span><span class="sxs-lookup"><span data-stu-id="c0129-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>
  
<span data-ttu-id="c0129-109">Active la casilla de verificación **borde de este grupo se utiliza para la federación y la conectividad con IM pública** si piensa utilizar este servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="c0129-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="c0129-110">Si tiene varios servidores Edge implementados, sólo uno de ellos se habilitará para la federación.</span><span class="sxs-lookup"><span data-stu-id="c0129-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="c0129-111">Si no activa esta casilla y más adelante decide que desea habilitar la federación, debe ejecutar nuevamente el Asistente de combinación de generador de topología, así como publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="c0129-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="c0129-112">Para obtener más información, consulte [fase 4: topologías de mezcla](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0129-112">For details, see [Phase 4: Merge Topologies](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>
  

