---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han procesado los pasos de sincronización de servicios de dominio de Active Directory más recientes.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814078"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="c6c05-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="c6c05-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="c6c05-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han procesado los pasos de sincronización de servicios de dominio de Active Directory más recientes.</span><span class="sxs-lookup"><span data-stu-id="c6c05-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="c6c05-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c6c05-105">**Columns**</span></span>

|<span data-ttu-id="c6c05-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c6c05-106">**Column**</span></span>|<span data-ttu-id="c6c05-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6c05-107">**Type**</span></span>|<span data-ttu-id="c6c05-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c6c05-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6c05-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c6c05-109">prinGuid</span></span>  <br/> |<span data-ttu-id="c6c05-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="c6c05-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c6c05-111">GUID principal del grupo que cambió.</span><span class="sxs-lookup"><span data-stu-id="c6c05-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="c6c05-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="c6c05-112">memberADPath</span></span>  <br/> |<span data-ttu-id="c6c05-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c6c05-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="c6c05-114">Nombre distintivo del miembro.</span><span class="sxs-lookup"><span data-stu-id="c6c05-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="c6c05-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="c6c05-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="c6c05-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="c6c05-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c6c05-117">False si se agregó el miembro.</span><span class="sxs-lookup"><span data-stu-id="c6c05-117">False if the member was added.</span></span> <span data-ttu-id="c6c05-118">True si se ha quitado el miembro.</span><span class="sxs-lookup"><span data-stu-id="c6c05-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="c6c05-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="c6c05-119">**Key**</span></span>

|<span data-ttu-id="c6c05-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c6c05-120">**Column**</span></span>|<span data-ttu-id="c6c05-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c6c05-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6c05-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="c6c05-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="c6c05-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="c6c05-123">Primary key.</span></span>  <br/> |
   

