---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Lo usan generalmente los clientes anteriores a Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295345"
---
# <a name="tblpreference"></a><span data-ttu-id="03ad1-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="03ad1-104">tblPreference</span></span>

<span data-ttu-id="03ad1-105">tblPreference contiene las preferencias de cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="03ad1-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="03ad1-106">Lo usan generalmente los clientes anteriores a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03ad1-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="03ad1-107">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="03ad1-107">**Columns**</span></span>


| <span data-ttu-id="03ad1-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="03ad1-108">**Column**</span></span>            | <span data-ttu-id="03ad1-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="03ad1-109">**Type**</span></span>                        | <span data-ttu-id="03ad1-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="03ad1-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="03ad1-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="03ad1-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="03ad1-112">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="03ad1-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="03ad1-113">Etiqueta con un formato como: \<URI del SIP del usuario\></span><span class="sxs-lookup"><span data-stu-id="03ad1-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="03ad1-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="03ad1-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="03ad1-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="03ad1-115">int, not null</span></span>  <br/>            | <span data-ttu-id="03ad1-116">Un número secuencial (por etiqueta) para fines de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="03ad1-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="03ad1-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="03ad1-117">prefContent</span></span>  <br/>    | <span data-ttu-id="03ad1-118">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="03ad1-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="03ad1-119">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="03ad1-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="03ad1-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="03ad1-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="03ad1-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="03ad1-121">int, not null</span></span>  <br/>            | <span data-ttu-id="03ad1-122">IDENTIFICADOR de la identidad que actualizó la preferencia.</span><span class="sxs-lookup"><span data-stu-id="03ad1-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="03ad1-123">**Clave**</span><span class="sxs-lookup"><span data-stu-id="03ad1-123">**Key**</span></span>

|<span data-ttu-id="03ad1-124">**Columna**</span><span class="sxs-lookup"><span data-stu-id="03ad1-124">**Column**</span></span>|<span data-ttu-id="03ad1-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="03ad1-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03ad1-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="03ad1-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="03ad1-127">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="03ad1-127">Primary key.</span></span>  <br/> |


