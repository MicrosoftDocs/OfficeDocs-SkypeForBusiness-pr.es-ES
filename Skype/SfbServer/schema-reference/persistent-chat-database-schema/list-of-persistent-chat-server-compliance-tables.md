---
title: Lista de tablas de cumplimiento de normas de servidor de charla persistente en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de normas Chat persistente consta de las siguientes tablas.
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="e5c41-103">Lista de tablas de cumplimiento de normas de servidor de charla persistente en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e5c41-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="e5c41-104">El esquema de base de datos de cumplimiento de normas Chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="e5c41-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="e5c41-105">Lista de tablas de cumplimiento de normas del servidor de Chat persistentes</span><span class="sxs-lookup"><span data-stu-id="e5c41-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="e5c41-106">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="e5c41-106">**Table**</span></span>|<span data-ttu-id="e5c41-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e5c41-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e5c41-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e5c41-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="e5c41-109">Contiene los eventos de cumplimiento de normas que aún no se han procesado por el adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="e5c41-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="e5c41-110">Esta tabla incluye los eventos relacionados con el Chat persistente, como mensajes de chat y descargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="e5c41-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="e5c41-111">(Eventos de participante se hace un seguimiento en la tabla tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="e5c41-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="e5c41-112">(Los servidores que procesan los eventos en esta tabla se enumeran en la tabla de tblComplianceFanout).</span><span class="sxs-lookup"><span data-stu-id="e5c41-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="e5c41-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="e5c41-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="e5c41-114">Contiene los servidores que se procesan un evento de conformidad.</span><span class="sxs-lookup"><span data-stu-id="e5c41-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="e5c41-115">Esta tabla está estrechamente emparejada con la tabla tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="e5c41-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="e5c41-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e5c41-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="e5c41-117">Contiene a los participantes actuales por servidor y el servicio de charla.</span><span class="sxs-lookup"><span data-stu-id="e5c41-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="e5c41-118">Se mantiene según los eventos de conformidad join y parte recibidos del servicio Charla persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c41-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="e5c41-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="e5c41-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="e5c41-120">Contiene información de estado de cumplimiento de normas de todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="e5c41-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

