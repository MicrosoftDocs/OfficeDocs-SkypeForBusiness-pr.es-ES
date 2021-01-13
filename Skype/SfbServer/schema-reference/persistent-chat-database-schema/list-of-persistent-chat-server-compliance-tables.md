---
title: Lista de tablas de cumplimiento del servidor de chat persistente en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de chat persistente consta de las tablas siguientes.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813060"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="62d79-103">Lista de tablas de cumplimiento del servidor de chat persistente en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="62d79-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="62d79-104">El esquema de base de datos de cumplimiento de chat persistente consta de las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="62d79-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="62d79-105">Lista de tablas de cumplimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="62d79-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="62d79-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="62d79-106">**Table**</span></span>|<span data-ttu-id="62d79-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="62d79-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="62d79-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="62d79-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="62d79-109">Contiene los eventos de cumplimiento que aún no fueron procesados por el adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="62d79-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="62d79-110">Esta tabla incluye eventos relacionados con el chat persistente, como mensajes de chat y descargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="62d79-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="62d79-111">(Los eventos participantes son seguidos por la tabla tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="62d79-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="62d79-112">(Los servidores que procesaron los eventos en esta tabla se enumeran en la tabla tblComplianceFanout).</span><span class="sxs-lookup"><span data-stu-id="62d79-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="62d79-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="62d79-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="62d79-114">Contiene los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="62d79-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="62d79-115">Esta tabla está fuertemente vinculada con la tabla tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="62d79-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="62d79-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="62d79-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="62d79-117">Contiene los participantes actuales por servicio de chat y por servidor.</span><span class="sxs-lookup"><span data-stu-id="62d79-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="62d79-118">Se mantiene en función de los eventos de unión y cumplimiento de partes recibidos del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="62d79-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="62d79-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="62d79-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="62d79-120">Contiene información de estado de cumplimiento de todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="62d79-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

