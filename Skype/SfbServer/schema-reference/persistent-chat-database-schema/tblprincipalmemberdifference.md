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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han procesado los pasos de sincronización de servicios de dominio de Active Directory más recientes.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295303"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="13a67-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="13a67-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="13a67-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han procesado los pasos de sincronización de servicios de dominio de Active Directory más recientes.</span><span class="sxs-lookup"><span data-stu-id="13a67-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="13a67-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="13a67-105">**Columns**</span></span>

|<span data-ttu-id="13a67-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="13a67-106">**Column**</span></span>|<span data-ttu-id="13a67-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="13a67-107">**Type**</span></span>|<span data-ttu-id="13a67-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13a67-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13a67-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="13a67-109">prinGuid</span></span>  <br/> |<span data-ttu-id="13a67-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="13a67-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="13a67-111">GUID principal del grupo que cambió.</span><span class="sxs-lookup"><span data-stu-id="13a67-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="13a67-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="13a67-112">memberADPath</span></span>  <br/> |<span data-ttu-id="13a67-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="13a67-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="13a67-114">Nombre distintivo del miembro.</span><span class="sxs-lookup"><span data-stu-id="13a67-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="13a67-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="13a67-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="13a67-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="13a67-116">bit, not null</span></span>  <br/> |<span data-ttu-id="13a67-117">False si se agregó el miembro.</span><span class="sxs-lookup"><span data-stu-id="13a67-117">False if the member was added.</span></span> <span data-ttu-id="13a67-118">True si se ha quitado el miembro.</span><span class="sxs-lookup"><span data-stu-id="13a67-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="13a67-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="13a67-119">**Key**</span></span>

|<span data-ttu-id="13a67-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="13a67-120">**Column**</span></span>|<span data-ttu-id="13a67-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13a67-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13a67-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="13a67-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="13a67-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="13a67-123">Primary key.</span></span>  <br/> |
   

