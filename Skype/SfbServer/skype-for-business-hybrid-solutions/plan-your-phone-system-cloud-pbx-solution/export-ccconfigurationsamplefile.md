---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración de ejemplo (.ini) de Skype Empresarial Cloud Connector Edition al directorio de dispositivos de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará para la implementación.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801010"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="39ccc-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="39ccc-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="39ccc-105">El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración de ejemplo (.ini) de Skype Empresarial Cloud Connector Edition al directorio de dispositivos de un dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="39ccc-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="39ccc-106">Puede modificar y cambiar el nombre del archivo que se usará para la implementación.</span><span class="sxs-lookup"><span data-stu-id="39ccc-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="39ccc-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="39ccc-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="39ccc-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39ccc-108">Parameters</span></span>

<span data-ttu-id="39ccc-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="39ccc-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="39ccc-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="39ccc-110">Examples</span></span>
<span data-ttu-id="39ccc-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39ccc-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="39ccc-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="39ccc-112">Example 1</span></span>

<span data-ttu-id="39ccc-113">En el siguiente ejemplo se descarga un archivo de configuración de ejemplo del sitio de Microsoft y se escribe en el directorio de dispositivos del dispositivo de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="39ccc-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="39ccc-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="39ccc-114">Detailed Description</span></span>
<span data-ttu-id="39ccc-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="39ccc-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="39ccc-116">La versión actual de Cloud Connector requiere que proporcione varios parámetros en el archivo .ini; por ejemplo, parámetros como las direcciones IP de las máquinas virtuales para los componentes de Cloud Connector, los nombres de componentes, los parámetros de puerta de enlace, entre otros.</span><span class="sxs-lookup"><span data-stu-id="39ccc-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="39ccc-117">Este cmdlet, cuando se ejecuta en el equipo host de Cloud Connector, descarga un archivo .ini de ejemplo con ejemplos de configuración del sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39ccc-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="39ccc-118">El cmdlet escribe el archivo en el directorio de dispositivos del dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="39ccc-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="39ccc-119">El directorio de dispositivos se especifica mediante el cmdlet Set-CcApplianceDirectory aplicación.</span><span class="sxs-lookup"><span data-stu-id="39ccc-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="39ccc-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="39ccc-120">Input Types</span></span>
<span data-ttu-id="39ccc-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39ccc-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="39ccc-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="39ccc-122">None.</span></span> <span data-ttu-id="39ccc-123">El Export-CcConfigurationSampleFile no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="39ccc-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="39ccc-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="39ccc-124">Return Types</span></span>
<span data-ttu-id="39ccc-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39ccc-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="39ccc-126">Ninguno</span><span class="sxs-lookup"><span data-stu-id="39ccc-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39ccc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="39ccc-127">See also</span></span>
<span data-ttu-id="39ccc-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39ccc-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="39ccc-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="39ccc-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

