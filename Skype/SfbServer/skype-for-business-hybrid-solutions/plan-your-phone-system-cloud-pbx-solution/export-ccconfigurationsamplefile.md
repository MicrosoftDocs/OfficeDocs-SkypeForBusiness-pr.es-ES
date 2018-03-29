---
title: CcConfigurationSampleFile de exportación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="72cca-104">CcConfigurationSampleFile de exportación</span><span class="sxs-lookup"><span data-stu-id="72cca-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="72cca-p102">El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.</span><span class="sxs-lookup"><span data-stu-id="72cca-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="72cca-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="72cca-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="72cca-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72cca-108">Parameters</span></span>

<span data-ttu-id="72cca-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72cca-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="72cca-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="72cca-110">Examples</span></span>
<span data-ttu-id="72cca-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="72cca-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="72cca-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="72cca-112">Example 1</span></span>

<span data-ttu-id="72cca-113">En el ejemplo siguiente se descarga un archivo de configuración de ejemplo desde el sitio de Microsoft y lo escribe en el directorio de dispositivo del dispositivo conector de nube:</span><span class="sxs-lookup"><span data-stu-id="72cca-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="72cca-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="72cca-114">Detailed Description</span></span>
<span data-ttu-id="72cca-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="72cca-115"></span></span>

<span data-ttu-id="72cca-116">La versión actual de nube conector requiere que se especifique varios parámetros en el archivo. ini. Por ejemplo, parámetros tales como las direcciones IP de máquinas virtuales para los componentes del conector de la nube, nombres de componentes, parámetros de puerta de enlace y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="72cca-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="72cca-117">Este cmdlet, cuando se ejecuta en el equipo host del conector de la nube, descarga un archivo .ini de ejemplo con ejemplos de configuración desde el sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72cca-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="72cca-118">El cmdlet escribe el archivo en el directorio de dispositivo del dispositivo conector de nube.</span><span class="sxs-lookup"><span data-stu-id="72cca-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="72cca-119">El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="72cca-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="72cca-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="72cca-120">Input Types</span></span>
<span data-ttu-id="72cca-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="72cca-121"></span></span>

<span data-ttu-id="72cca-p104">Ninguno. El cmdlet Export-CcConfigurationSampleFile no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="72cca-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="72cca-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="72cca-124">Return Types</span></span>
<span data-ttu-id="72cca-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="72cca-125"></span></span>

<span data-ttu-id="72cca-126">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72cca-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72cca-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72cca-127">See also</span></span>
<span data-ttu-id="72cca-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="72cca-128"></span></span>

[<span data-ttu-id="72cca-129">Conjunto de CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="72cca-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

