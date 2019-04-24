---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de servicios de dominio de Active Directory.
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212449"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="ec33e-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="ec33e-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="ec33e-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec33e-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="ec33e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="ec33e-105">**Columns**</span></span>

|<span data-ttu-id="ec33e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ec33e-106">**Column**</span></span>|<span data-ttu-id="ec33e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ec33e-107">**Type**</span></span>|<span data-ttu-id="ec33e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ec33e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ec33e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ec33e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="ec33e-110">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="ec33e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="ec33e-111">Entidad de seguridad el GUID del grupo que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="ec33e-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="ec33e-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="ec33e-112">memberADPath</span></span>  <br/> |<span data-ttu-id="ec33e-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec33e-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="ec33e-114">Nombre distintivo (DN) del miembro.</span><span class="sxs-lookup"><span data-stu-id="ec33e-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="ec33e-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="ec33e-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="ec33e-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="ec33e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ec33e-117">False si se ha agregado el miembro.</span><span class="sxs-lookup"><span data-stu-id="ec33e-117">False if the member was added.</span></span> <span data-ttu-id="ec33e-118">Es True si se ha quitado el miembro.</span><span class="sxs-lookup"><span data-stu-id="ec33e-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="ec33e-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="ec33e-119">**Key**</span></span>

|<span data-ttu-id="ec33e-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ec33e-120">**Column**</span></span>|<span data-ttu-id="ec33e-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ec33e-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec33e-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="ec33e-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="ec33e-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="ec33e-123">Primary key.</span></span>  <br/> |
   

