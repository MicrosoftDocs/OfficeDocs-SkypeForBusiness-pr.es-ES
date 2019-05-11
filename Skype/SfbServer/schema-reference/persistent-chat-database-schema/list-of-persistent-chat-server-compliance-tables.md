---
title: Lista de tablas de cumplimiento del servidor de Chat persistente en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de normas de Chat persistente consta de las siguientes tablas.
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929892"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="662c3-103">Lista de tablas de cumplimiento del servidor de Chat persistente en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="662c3-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="662c3-104">El esquema de base de datos de cumplimiento de normas de Chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="662c3-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="662c3-105">Lista de tablas de cumplimiento del servidor de Chat en grupo</span><span class="sxs-lookup"><span data-stu-id="662c3-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="662c3-106">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="662c3-106">**Table**</span></span>|<span data-ttu-id="662c3-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="662c3-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="662c3-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="662c3-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="662c3-109">Contiene los eventos de cumplimiento que aún no se han procesado por el adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="662c3-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="662c3-110">Esta tabla incluye los eventos relacionados con el Chat persistente, como mensajes de chat y descargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="662c3-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="662c3-111">(Eventos de participante se realiza un seguimiento de la tabla tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="662c3-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="662c3-112">(Los servidores que procesaron los eventos de esta tabla se enumeran en la tabla tblComplianceFanout).</span><span class="sxs-lookup"><span data-stu-id="662c3-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="662c3-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="662c3-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="662c3-114">Contiene los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="662c3-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="662c3-115">En esta tabla se complementa con la tabla tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="662c3-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="662c3-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="662c3-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="662c3-117">Contiene a los participantes actuales por el servicio de chat y por servidor.</span><span class="sxs-lookup"><span data-stu-id="662c3-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="662c3-118">Se mantiene en función de eventos de cumplimiento de combinación y elemento recibidos desde el servicio de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="662c3-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="662c3-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="662c3-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="662c3-120">Contiene información de estado de cumplimiento de todo el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="662c3-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

