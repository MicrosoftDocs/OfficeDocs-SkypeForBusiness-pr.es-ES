---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa la configuración de Skype Empresarial Cloud Connector Edition desde un archivo local al servidor host de Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799860"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="3d3f8-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d3f8-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="3d3f8-104">Importa la configuración de Skype Empresarial Cloud Connector Edition desde un archivo local al servidor host de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3d3f8-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3d3f8-105">Examples</span></span>
<span data-ttu-id="3d3f8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3f8-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3d3f8-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="3d3f8-107">Example 1</span></span>

<span data-ttu-id="3d3f8-108">En el siguiente ejemplo se copia la CloudConnector.ini del directorio de dispositivos de la instancia de Cloud Connector al directorio %SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="3d3f8-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="3d3f8-109">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="3d3f8-109">Detailed Description</span></span>
<span data-ttu-id="3d3f8-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3f8-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="3d3f8-111">Este cmdlet copia la CloudConnector.ini del directorio de dispositivos del dispositivo de Cloud Connector al directorio %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="3d3f8-112">El directorio de dispositivos se especifica mediante el cmdlet Set-CcApplianceDirectory aplicación.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="3d3f8-113">El cmdlet sobrescribirá cualquier archivo existente en %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="3d3f8-114">Este comando se aplica a Cloud Connector Edition versión 2.0.1 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3d3f8-115">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d3f8-115">Parameters</span></span>
<span data-ttu-id="3d3f8-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3f8-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="3d3f8-117">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3d3f8-117">**Parameter**</span></span>|<span data-ttu-id="3d3f8-118">**Required**</span><span class="sxs-lookup"><span data-stu-id="3d3f8-118">**Required**</span></span>|<span data-ttu-id="3d3f8-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d3f8-119">**Type**</span></span>|<span data-ttu-id="3d3f8-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3d3f8-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d3f8-121">Force</span><span class="sxs-lookup"><span data-stu-id="3d3f8-121">Force</span></span>  <br/> |<span data-ttu-id="3d3f8-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="3d3f8-122">Optional</span></span>  <br/> |<span data-ttu-id="3d3f8-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3d3f8-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3d3f8-124">Sobrescribir el archivo existente en %SystemDrive%\ProgramData\CloudConnector sin notificación.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3d3f8-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="3d3f8-125">Input Types</span></span>
<span data-ttu-id="3d3f8-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3f8-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="3d3f8-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-127">None.</span></span> <span data-ttu-id="3d3f8-128">El Import-CcConfiguration no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3d3f8-129">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="3d3f8-129">Return Types</span></span>
<span data-ttu-id="3d3f8-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3f8-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="3d3f8-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d3f8-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d3f8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d3f8-132">See also</span></span>
<span data-ttu-id="3d3f8-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3f8-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="3d3f8-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d3f8-134">Export-CcConfiguration</span></span>
  

