---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento para todo el grupo.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295478"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="b23bd-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="b23bd-103">tblComplianceState</span></span>
 
<span data-ttu-id="b23bd-104">tblComplianceState contiene información de estado de cumplimiento para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="b23bd-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="b23bd-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b23bd-105">**Columns**</span></span>

|<span data-ttu-id="b23bd-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b23bd-106">**Column**</span></span>|<span data-ttu-id="b23bd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b23bd-107">**Type**</span></span>|<span data-ttu-id="b23bd-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b23bd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b23bd-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="b23bd-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="b23bd-110">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="b23bd-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="b23bd-111">IDENTIFICADOR del último evento de cumplimiento procesado.</span><span class="sxs-lookup"><span data-stu-id="b23bd-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="b23bd-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="b23bd-112">activeServerID</span></span>  <br/> |<span data-ttu-id="b23bd-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="b23bd-113">int, not null</span></span>  <br/> |<span data-ttu-id="b23bd-114">IDENTIFICADOR del servidor de cumplimiento que contiene el bloqueo exclusivo de la base de datos, o bien-1 si no hay ninguno.</span><span class="sxs-lookup"><span data-stu-id="b23bd-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="b23bd-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="b23bd-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="b23bd-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="b23bd-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="b23bd-117">Fecha de expiración de bloqueo (si activeServerID no es-1).</span><span class="sxs-lookup"><span data-stu-id="b23bd-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

