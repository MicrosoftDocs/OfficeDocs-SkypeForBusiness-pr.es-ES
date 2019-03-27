---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento de todo el grupo de servidores.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899295"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="7a9d1-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="7a9d1-103">tblComplianceState</span></span>
 
<span data-ttu-id="7a9d1-104">tblComplianceState contiene información de estado de cumplimiento de todo el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9d1-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="7a9d1-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="7a9d1-105">**Columns**</span></span>

|<span data-ttu-id="7a9d1-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7a9d1-106">**Column**</span></span>|<span data-ttu-id="7a9d1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7a9d1-107">**Type**</span></span>|<span data-ttu-id="7a9d1-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7a9d1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a9d1-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="7a9d1-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="7a9d1-110">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7a9d1-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="7a9d1-111">Identificador del último evento de cumplimiento procesado.</span><span class="sxs-lookup"><span data-stu-id="7a9d1-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="7a9d1-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="7a9d1-112">activeServerID</span></span>  <br/> |<span data-ttu-id="7a9d1-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7a9d1-113">int, not null</span></span>  <br/> |<span data-ttu-id="7a9d1-114">Identificador del servidor de cumplimiento de normas que mantiene el bloqueo exclusivo en la base de datos, o -1 si no hay ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a9d1-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="7a9d1-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="7a9d1-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="7a9d1-116">DateTime2, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7a9d1-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="7a9d1-117">Bloquear el tiempo de expiración (si activeServerID no es -1).</span><span class="sxs-lookup"><span data-stu-id="7a9d1-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

