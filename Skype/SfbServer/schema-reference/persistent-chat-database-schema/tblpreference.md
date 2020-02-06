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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Lo usan generalmente los clientes anteriores a Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814558"
---
# <a name="tblpreference"></a><span data-ttu-id="b2662-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="b2662-104">tblPreference</span></span>

<span data-ttu-id="b2662-105">tblPreference contiene las preferencias de cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b2662-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="b2662-106">Lo usan generalmente los clientes anteriores a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b2662-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="b2662-107">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b2662-107">**Columns**</span></span>


| <span data-ttu-id="b2662-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b2662-108">**Column**</span></span>            | <span data-ttu-id="b2662-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b2662-109">**Type**</span></span>                        | <span data-ttu-id="b2662-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b2662-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="b2662-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="b2662-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="b2662-112">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b2662-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="b2662-113">Etiqueta con un formato como: \<URI del SIP del usuario\></span><span class="sxs-lookup"><span data-stu-id="b2662-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="b2662-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="b2662-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="b2662-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="b2662-115">int, not null</span></span>  <br/>            | <span data-ttu-id="b2662-116">Un número secuencial (por etiqueta) para fines de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="b2662-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="b2662-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="b2662-117">prefContent</span></span>  <br/>    | <span data-ttu-id="b2662-118">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="b2662-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="b2662-119">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="b2662-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="b2662-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="b2662-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="b2662-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="b2662-121">int, not null</span></span>  <br/>            | <span data-ttu-id="b2662-122">IDENTIFICADOR de la identidad que actualizó la preferencia.</span><span class="sxs-lookup"><span data-stu-id="b2662-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="b2662-123">**Clave**</span><span class="sxs-lookup"><span data-stu-id="b2662-123">**Key**</span></span>

|<span data-ttu-id="b2662-124">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b2662-124">**Column**</span></span>|<span data-ttu-id="b2662-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b2662-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2662-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="b2662-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="b2662-127">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b2662-127">Primary key.</span></span>  <br/> |


