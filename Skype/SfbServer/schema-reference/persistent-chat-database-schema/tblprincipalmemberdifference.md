---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no se han procesado en los pasos de sincronización de servicios de dominio de Active Directory posteriores.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809710"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="39f2b-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="39f2b-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="39f2b-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no se han procesado en los pasos de sincronización de servicios de dominio de Active Directory posteriores.</span><span class="sxs-lookup"><span data-stu-id="39f2b-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="39f2b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="39f2b-105">**Columns**</span></span>

|<span data-ttu-id="39f2b-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="39f2b-106">**Column**</span></span>|<span data-ttu-id="39f2b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39f2b-107">**Type**</span></span>|<span data-ttu-id="39f2b-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39f2b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39f2b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="39f2b-109">prinGuid</span></span>  <br/> |<span data-ttu-id="39f2b-110">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="39f2b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="39f2b-111">GUID de entidad de seguridad del grupo modificado.</span><span class="sxs-lookup"><span data-stu-id="39f2b-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="39f2b-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="39f2b-112">memberADPath</span></span>  <br/> |<span data-ttu-id="39f2b-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="39f2b-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="39f2b-114">Nombre distintivo del miembro.</span><span class="sxs-lookup"><span data-stu-id="39f2b-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="39f2b-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="39f2b-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="39f2b-116">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="39f2b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="39f2b-p101">False si se agregó el miembro. True si se quitó el miembro.</span><span class="sxs-lookup"><span data-stu-id="39f2b-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="39f2b-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="39f2b-119">**Key**</span></span>

|<span data-ttu-id="39f2b-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="39f2b-120">**Column**</span></span>|<span data-ttu-id="39f2b-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39f2b-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="39f2b-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="39f2b-122">Primary key.</span></span>  <br/> |
   

