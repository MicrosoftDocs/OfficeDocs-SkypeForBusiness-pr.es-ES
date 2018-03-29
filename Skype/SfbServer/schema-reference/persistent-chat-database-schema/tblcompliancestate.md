---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento de normas de todo el grupo.
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a><span data-ttu-id="787d6-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="787d6-103">tblComplianceState</span></span>
 
<span data-ttu-id="787d6-104">tblComplianceState contiene información de estado de cumplimiento de normas de todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="787d6-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="787d6-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="787d6-105">**Columns**</span></span>

|<span data-ttu-id="787d6-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="787d6-106">**Column**</span></span>|<span data-ttu-id="787d6-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="787d6-107">**Type**</span></span>|<span data-ttu-id="787d6-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="787d6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="787d6-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="787d6-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="787d6-110">bigint, no nulo</span><span class="sxs-lookup"><span data-stu-id="787d6-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="787d6-111">Id. del evento transformados de conformidad más reciente.</span><span class="sxs-lookup"><span data-stu-id="787d6-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="787d6-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="787d6-112">activeServerID</span></span>  <br/> |<span data-ttu-id="787d6-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="787d6-113">int, not null</span></span>  <br/> |<span data-ttu-id="787d6-114">Identificador del servidor de cumplimiento mantiene el bloqueo exclusivo en la base de datos, o -1 si no hay ninguno.</span><span class="sxs-lookup"><span data-stu-id="787d6-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="787d6-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="787d6-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="787d6-116">DateTime2, no nulo</span><span class="sxs-lookup"><span data-stu-id="787d6-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="787d6-117">Bloquear tiempo de caducidad (si activeServerID no es -1).</span><span class="sxs-lookup"><span data-stu-id="787d6-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

