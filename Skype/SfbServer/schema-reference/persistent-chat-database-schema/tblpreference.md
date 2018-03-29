---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias del cliente de los usuarios. Generalmente se utiliza por los clientes anteriores a Lync de 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="ca89b-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="ca89b-104">tblPreference</span></span>
 
<span data-ttu-id="ca89b-105">tblPreference contiene las preferencias del cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ca89b-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="ca89b-106">Generalmente se utiliza por los clientes anteriores a Lync de 2013.</span><span class="sxs-lookup"><span data-stu-id="ca89b-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="ca89b-107">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="ca89b-107">**Columns**</span></span>

|<span data-ttu-id="ca89b-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ca89b-108">**Column**</span></span>|<span data-ttu-id="ca89b-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ca89b-109">**Type**</span></span>|<span data-ttu-id="ca89b-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ca89b-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca89b-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="ca89b-111">prefLabel</span></span>  <br/> |<span data-ttu-id="ca89b-112">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="ca89b-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ca89b-113">Etiquetar con un formato como: \<uri de sip del usuario\></span><span class="sxs-lookup"><span data-stu-id="ca89b-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="ca89b-114">nombre de usuario. \<conjunto de preferencias\>.</span><span class="sxs-lookup"><span data-stu-id="ca89b-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="ca89b-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="ca89b-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="ca89b-116">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="ca89b-116">int, not null</span></span>  <br/> |<span data-ttu-id="ca89b-117">Un número secuencial (por etiqueta) para control de versiones.</span><span class="sxs-lookup"><span data-stu-id="ca89b-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="ca89b-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="ca89b-118">prefContent</span></span>  <br/> |<span data-ttu-id="ca89b-119">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ca89b-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ca89b-120">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="ca89b-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="ca89b-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="ca89b-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="ca89b-122">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="ca89b-122">int, not null</span></span>  <br/> |<span data-ttu-id="ca89b-123">Identificador de la entidad de seguridad que se actualiza la preferencia.</span><span class="sxs-lookup"><span data-stu-id="ca89b-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="ca89b-124">**Clave**</span><span class="sxs-lookup"><span data-stu-id="ca89b-124">**Key**</span></span>

|<span data-ttu-id="ca89b-125">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ca89b-125">**Column**</span></span>|<span data-ttu-id="ca89b-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ca89b-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca89b-127">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="ca89b-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="ca89b-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="ca89b-128">Primary key.</span></span>  <br/> |
   

