---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de servicios de dominio de Active Directory.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902239"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="9a9db-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="9a9db-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="9a9db-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a9db-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="9a9db-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="9a9db-105">**Columns**</span></span>

|<span data-ttu-id="9a9db-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9a9db-106">**Column**</span></span>|<span data-ttu-id="9a9db-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9a9db-107">**Type**</span></span>|<span data-ttu-id="9a9db-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9a9db-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a9db-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9a9db-109">prinGuid</span></span>  <br/> |<span data-ttu-id="9a9db-110">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="9a9db-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="9a9db-111">Entidad de seguridad el GUID del grupo que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="9a9db-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="9a9db-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="9a9db-112">memberADPath</span></span>  <br/> |<span data-ttu-id="9a9db-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9a9db-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="9a9db-114">Nombre distintivo (DN) del miembro.</span><span class="sxs-lookup"><span data-stu-id="9a9db-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="9a9db-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="9a9db-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="9a9db-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="9a9db-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9a9db-117">False si se ha agregado el miembro.</span><span class="sxs-lookup"><span data-stu-id="9a9db-117">False if the member was added.</span></span> <span data-ttu-id="9a9db-118">Es True si se ha quitado el miembro.</span><span class="sxs-lookup"><span data-stu-id="9a9db-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="9a9db-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9a9db-119">**Key**</span></span>

|<span data-ttu-id="9a9db-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9a9db-120">**Column**</span></span>|<span data-ttu-id="9a9db-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9a9db-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a9db-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="9a9db-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="9a9db-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9a9db-123">Primary key.</span></span>  <br/> |
   

