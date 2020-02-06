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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento para todo el grupo.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814638"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="6bf22-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="6bf22-103">tblComplianceState</span></span>
 
<span data-ttu-id="6bf22-104">tblComplianceState contiene información de estado de cumplimiento para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="6bf22-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="6bf22-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="6bf22-105">**Columns**</span></span>

|<span data-ttu-id="6bf22-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6bf22-106">**Column**</span></span>|<span data-ttu-id="6bf22-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6bf22-107">**Type**</span></span>|<span data-ttu-id="6bf22-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6bf22-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6bf22-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="6bf22-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="6bf22-110">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="6bf22-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="6bf22-111">IDENTIFICADOR del último evento de cumplimiento procesado.</span><span class="sxs-lookup"><span data-stu-id="6bf22-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="6bf22-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="6bf22-112">activeServerID</span></span>  <br/> |<span data-ttu-id="6bf22-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="6bf22-113">int, not null</span></span>  <br/> |<span data-ttu-id="6bf22-114">IDENTIFICADOR del servidor de cumplimiento que contiene el bloqueo exclusivo de la base de datos, o bien-1 si no hay ninguno.</span><span class="sxs-lookup"><span data-stu-id="6bf22-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="6bf22-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="6bf22-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="6bf22-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="6bf22-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="6bf22-117">Fecha de expiración de bloqueo (si activeServerID no es-1).</span><span class="sxs-lookup"><span data-stu-id="6bf22-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

