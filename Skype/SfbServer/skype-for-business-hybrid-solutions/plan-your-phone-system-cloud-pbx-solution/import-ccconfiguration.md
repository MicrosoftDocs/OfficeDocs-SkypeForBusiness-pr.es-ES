---
title: CcConfiguration de importación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector en la nube.
ms.openlocfilehash: c48ce321b4cf40626cc67de8ff32107bf08e5443
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569729"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="1361e-103">CcConfiguration de importación</span><span class="sxs-lookup"><span data-stu-id="1361e-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="1361e-104">Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="1361e-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="1361e-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1361e-105">Examples</span></span>
<span data-ttu-id="1361e-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1361e-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="1361e-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="1361e-107">Example 1</span></span>

<span data-ttu-id="1361e-108">El siguiente ejemplo copia la CloudConnector.ini desde el directorio de dispositivo de la instancia del conector en la nube al directorio %SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="1361e-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="1361e-109">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="1361e-109">Detailed Description</span></span>
<span data-ttu-id="1361e-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1361e-110"></span></span>

<span data-ttu-id="1361e-111">Este cmdlet copia la CloudConnector.ini desde el directorio de dispositivo del dispositivo conector en la nube en el directorio %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="1361e-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="1361e-112">El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="1361e-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="1361e-113">El cmdlet sobrescribirá los archivos existentes en % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="1361e-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="1361e-114">Este comando se aplica a la nube conector Edition versión 2.0.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1361e-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1361e-115">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1361e-115">Parameters</span></span>
<span data-ttu-id="1361e-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1361e-116"></span></span>

|<span data-ttu-id="1361e-117">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="1361e-117">**Parameter**</span></span>|<span data-ttu-id="1361e-118">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="1361e-118">**Required**</span></span>|<span data-ttu-id="1361e-119">**Tipo de**</span><span class="sxs-lookup"><span data-stu-id="1361e-119">**Type**</span></span>|<span data-ttu-id="1361e-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1361e-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1361e-121">Force</span><span class="sxs-lookup"><span data-stu-id="1361e-121">Force</span></span>  <br/> |<span data-ttu-id="1361e-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="1361e-122">Optional</span></span>  <br/> |<span data-ttu-id="1361e-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1361e-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1361e-124">Sobrescribir archivo existente en %SystemDrive%\ProgramData\CloudConnector sin notificación.</span><span class="sxs-lookup"><span data-stu-id="1361e-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1361e-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="1361e-125">Input Types</span></span>
<span data-ttu-id="1361e-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1361e-126"></span></span>

<span data-ttu-id="1361e-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1361e-127">None.</span></span> <span data-ttu-id="1361e-128">El cmdlet Import-CcConfiguration no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="1361e-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1361e-129">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="1361e-129">Return Types</span></span>
<span data-ttu-id="1361e-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1361e-130"></span></span>

<span data-ttu-id="1361e-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1361e-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1361e-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1361e-132">See also</span></span>
<span data-ttu-id="1361e-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1361e-133"></span></span>

<span data-ttu-id="1361e-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="1361e-134">Export-CcConfiguration</span></span>
  

