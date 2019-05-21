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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa la configuración de Skype empresarial Cloud Connector Edition de un archivo local al servidor host del conector de nube.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287282"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="a9954-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="a9954-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="a9954-104">Importa la configuración de Skype empresarial Cloud Connector Edition de un archivo local al servidor host del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="a9954-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a9954-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a9954-105">Examples</span></span>
<span data-ttu-id="a9954-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a9954-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="a9954-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a9954-107">Example 1</span></span>

<span data-ttu-id="a9954-108">En el ejemplo siguiente se copia el CloudConnector. ini del directorio del dispositivo de la instancia de Cloud Connector en el directorio%SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="a9954-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="a9954-109">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="a9954-109">Detailed Description</span></span>
<span data-ttu-id="a9954-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a9954-110"></span></span>

<span data-ttu-id="a9954-111">Este cmdlet copia el CloudConnector. ini desde el directorio del equipo del dispositivo del conector de nube en el directorio de%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="a9954-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="a9954-112">El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="a9954-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="a9954-113">El cmdlet sobrescribirá cualquier archivo existente en%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="a9954-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="a9954-114">Este comando se aplica a la versión 2.0.1 de Cloud Connector Edition y posteriores.</span><span class="sxs-lookup"><span data-stu-id="a9954-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a9954-115">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9954-115">Parameters</span></span>
<span data-ttu-id="a9954-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a9954-116"></span></span>

|<span data-ttu-id="a9954-117">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a9954-117">**Parameter**</span></span>|<span data-ttu-id="a9954-118">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="a9954-118">**Required**</span></span>|<span data-ttu-id="a9954-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a9954-119">**Type**</span></span>|<span data-ttu-id="a9954-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a9954-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9954-121">Force</span><span class="sxs-lookup"><span data-stu-id="a9954-121">Force</span></span>  <br/> |<span data-ttu-id="a9954-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="a9954-122">Optional</span></span>  <br/> |<span data-ttu-id="a9954-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a9954-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a9954-124">Sobrescribir el archivo existente en%SystemDrive%\ProgramData\CloudConnector sin notificación.</span><span class="sxs-lookup"><span data-stu-id="a9954-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a9954-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a9954-125">Input Types</span></span>
<span data-ttu-id="a9954-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a9954-126"></span></span>

<span data-ttu-id="a9954-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9954-127">None.</span></span> <span data-ttu-id="a9954-128">El cmdlet Import-CcConfiguration no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="a9954-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a9954-129">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a9954-129">Return Types</span></span>
<span data-ttu-id="a9954-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a9954-130"></span></span>

<span data-ttu-id="a9954-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9954-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9954-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9954-132">See also</span></span>
<span data-ttu-id="a9954-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a9954-133"></span></span>

<span data-ttu-id="a9954-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="a9954-134">Export-CcConfiguration</span></span>
  

