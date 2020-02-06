---
title: Tabla de cuadros de diálogo en Skype empresarial Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815278"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0822e-103">Tabla de cuadros de diálogo en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0822e-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0822e-104">La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="0822e-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="0822e-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0822e-105">**Column**</span></span>|<span data-ttu-id="0822e-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0822e-106">**Data Type**</span></span>|<span data-ttu-id="0822e-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0822e-107">**Key/Index**</span></span>|<span data-ttu-id="0822e-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0822e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0822e-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="0822e-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="0822e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0822e-110">datetime</span></span>  <br/> |<span data-ttu-id="0822e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="0822e-111">Primary</span></span>  <br/> |<span data-ttu-id="0822e-112">Hora de la solicitud de sesión; se usa en conjunción con SessionIDSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="0822e-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="0822e-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="0822e-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="0822e-114">int</span><span class="sxs-lookup"><span data-stu-id="0822e-114">int</span></span>  <br/> |<span data-ttu-id="0822e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="0822e-115">Primary</span></span>  <br/> |<span data-ttu-id="0822e-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="0822e-116">ID number to identify the session.</span></span> <span data-ttu-id="0822e-117">Se usa en conjunción con SessionIDTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="0822e-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="0822e-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="0822e-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="0822e-119">int</span><span class="sxs-lookup"><span data-stu-id="0822e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="0822e-120">Suma de comprobación de la ExternalID.</span><span class="sxs-lookup"><span data-stu-id="0822e-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="0822e-121">Este campo se usa para aumentar la velocidad de las búsquedas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0822e-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="0822e-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="0822e-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="0822e-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="0822e-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="0822e-124">IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario.</span><span class="sxs-lookup"><span data-stu-id="0822e-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="0822e-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="0822e-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="0822e-126">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="0822e-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="0822e-127">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0822e-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

