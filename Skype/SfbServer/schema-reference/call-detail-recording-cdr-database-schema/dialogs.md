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
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296325"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="82219-103">Tabla de cuadros de diálogo en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="82219-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82219-104">La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="82219-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="82219-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="82219-105">**Column**</span></span>|<span data-ttu-id="82219-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="82219-106">**Data Type**</span></span>|<span data-ttu-id="82219-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="82219-107">**Key/Index**</span></span>|<span data-ttu-id="82219-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="82219-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82219-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="82219-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="82219-110">datetime</span><span class="sxs-lookup"><span data-stu-id="82219-110">datetime</span></span>  <br/> |<span data-ttu-id="82219-111">Primary</span><span class="sxs-lookup"><span data-stu-id="82219-111">Primary</span></span>  <br/> |<span data-ttu-id="82219-112">Hora de la solicitud de sesión; se usa en conjunción con SessionIDSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="82219-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="82219-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="82219-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="82219-114">int</span><span class="sxs-lookup"><span data-stu-id="82219-114">int</span></span>  <br/> |<span data-ttu-id="82219-115">Primary</span><span class="sxs-lookup"><span data-stu-id="82219-115">Primary</span></span>  <br/> |<span data-ttu-id="82219-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="82219-116">ID number to identify the session.</span></span> <span data-ttu-id="82219-117">Se usa en conjunción con SessionIDTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="82219-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="82219-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="82219-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="82219-119">int</span><span class="sxs-lookup"><span data-stu-id="82219-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="82219-120">Suma de comprobación de la ExternalID.</span><span class="sxs-lookup"><span data-stu-id="82219-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="82219-121">Este campo se usa para aumentar la velocidad de las búsquedas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="82219-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="82219-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="82219-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="82219-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="82219-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="82219-124">IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario.</span><span class="sxs-lookup"><span data-stu-id="82219-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="82219-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="82219-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="82219-126">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="82219-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="82219-127">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="82219-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

