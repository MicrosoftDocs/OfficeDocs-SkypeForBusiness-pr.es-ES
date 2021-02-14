---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta la configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801470"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="c5edd-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c5edd-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="c5edd-104">Exporta la configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c5edd-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c5edd-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c5edd-105">Examples</span></span>
<span data-ttu-id="c5edd-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5edd-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c5edd-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="c5edd-107">Example 1</span></span>

<span data-ttu-id="c5edd-108">En el siguiente ejemplo se establece el parámetro Path como una ruta de acceso de archivo completa y se exportan las configuraciones a ese archivo.</span><span class="sxs-lookup"><span data-stu-id="c5edd-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="c5edd-109">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="c5edd-109">Detailed Description</span></span>
<span data-ttu-id="c5edd-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5edd-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="c5edd-111">El cmdlet Export-CcConfiguration permite guardar la configuración de Cloud Connector en un archivo en una ruta de acceso seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c5edd-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="c5edd-112">Este comando se introdujo en la versión 2.0 de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c5edd-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c5edd-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5edd-113">Parameters</span></span>
<span data-ttu-id="c5edd-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5edd-114"><a name="Examples"> </a></span></span>

|<span data-ttu-id="c5edd-115">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="c5edd-115">**Parameter**</span></span>|<span data-ttu-id="c5edd-116">**Required**</span><span class="sxs-lookup"><span data-stu-id="c5edd-116">**Required**</span></span>|<span data-ttu-id="c5edd-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c5edd-117">**Type**</span></span>|<span data-ttu-id="c5edd-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c5edd-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c5edd-119">Path</span><span class="sxs-lookup"><span data-stu-id="c5edd-119">Path</span></span>  <br/> |<span data-ttu-id="c5edd-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c5edd-120">Required</span></span>  <br/> |<span data-ttu-id="c5edd-121">System.String</span><span class="sxs-lookup"><span data-stu-id="c5edd-121">System.String</span></span>  <br/> |<span data-ttu-id="c5edd-122">Ruta de acceso completa al archivo donde se almacenarán las configuraciones de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c5edd-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c5edd-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="c5edd-123">Input Types</span></span>
<span data-ttu-id="c5edd-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5edd-124"><a name="Examples"> </a></span></span>

<span data-ttu-id="c5edd-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c5edd-125">None.</span></span> <span data-ttu-id="c5edd-126">El Export-CcConfiguration no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5edd-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c5edd-127">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c5edd-127">Return Types</span></span>
<span data-ttu-id="c5edd-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5edd-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="c5edd-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c5edd-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c5edd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5edd-130">See also</span></span>
<span data-ttu-id="c5edd-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5edd-131"><a name="Examples"> </a></span></span>

<span data-ttu-id="c5edd-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c5edd-132">Import-CcConfiguration</span></span>
  

