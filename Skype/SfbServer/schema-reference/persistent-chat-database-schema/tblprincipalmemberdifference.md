---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (agregar y quitar a miembros) que aún no se han procesado por los pasos de Active Sync de servicios de dominio de directorio posterior.
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="afe2c-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="afe2c-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="afe2c-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (agregar y quitar a miembros) que aún no se han procesado por los pasos de Active Sync de servicios de dominio de directorio posterior.</span><span class="sxs-lookup"><span data-stu-id="afe2c-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="afe2c-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="afe2c-105">**Columns**</span></span>

|<span data-ttu-id="afe2c-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="afe2c-106">**Column**</span></span>|<span data-ttu-id="afe2c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="afe2c-107">**Type**</span></span>|<span data-ttu-id="afe2c-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="afe2c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afe2c-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="afe2c-109">prinGuid</span></span>  <br/> |<span data-ttu-id="afe2c-110">GUID, no nulo</span><span class="sxs-lookup"><span data-stu-id="afe2c-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="afe2c-111">GUID principal del grupo que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="afe2c-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="afe2c-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="afe2c-112">memberADPath</span></span>  <br/> |<span data-ttu-id="afe2c-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="afe2c-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="afe2c-114">Nombre completo del miembro.</span><span class="sxs-lookup"><span data-stu-id="afe2c-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="afe2c-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="afe2c-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="afe2c-116">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="afe2c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="afe2c-117">False si se ha agregado el miembro.</span><span class="sxs-lookup"><span data-stu-id="afe2c-117">False if the member was added.</span></span> <span data-ttu-id="afe2c-118">True si se ha quitado el miembro.</span><span class="sxs-lookup"><span data-stu-id="afe2c-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="afe2c-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="afe2c-119">**Key**</span></span>

|<span data-ttu-id="afe2c-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="afe2c-120">**Column**</span></span>|<span data-ttu-id="afe2c-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="afe2c-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="afe2c-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="afe2c-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="afe2c-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="afe2c-123">Primary key.</span></span>  <br/> |
   

