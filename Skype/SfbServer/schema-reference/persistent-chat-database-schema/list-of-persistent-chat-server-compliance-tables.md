---
title: Lista de tablas de cumplimiento del servidor de chat persistente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de chat persistente consta de las siguientes tablas.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814768"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="a5a3e-103">Lista de tablas de cumplimiento del servidor de chat persistente en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a5a3e-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="a5a3e-104">El esquema de base de datos de cumplimiento de chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="a5a3e-105">Lista de tablas de cumplimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a5a3e-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="a5a3e-106">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="a5a3e-106">**Table**</span></span>|<span data-ttu-id="a5a3e-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5a3e-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a5a3e-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="a5a3e-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="a5a3e-109">Contiene los eventos de cumplimiento que el adaptador configurado aún no ha procesado.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="a5a3e-110">Esta tabla incluye eventos persistentes relacionados con el chat, como mensajes instantáneos y descargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="a5a3e-111">(Los eventos de participantes se controlan en la tabla tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="a5a3e-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="a5a3e-112">(Los servidores que procesaron los eventos de esta tabla se muestran en la tabla tblComplianceFanout).</span><span class="sxs-lookup"><span data-stu-id="a5a3e-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="a5a3e-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="a5a3e-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="a5a3e-114">Contiene los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="a5a3e-115">Esta tabla está estrechamente acoplada a la tabla tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="a5a3e-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="a5a3e-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="a5a3e-117">Contiene participantes actuales por servicio de chat y por servidor.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="a5a3e-118">Se mantiene según los eventos de conformidad con la Unión y la parte recibidos del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="a5a3e-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="a5a3e-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="a5a3e-120">Contiene información de estado de cumplimiento para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

