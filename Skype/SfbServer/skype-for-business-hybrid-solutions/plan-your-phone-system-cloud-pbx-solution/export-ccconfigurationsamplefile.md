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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003430"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="ed653-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="ed653-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="ed653-p102">El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.</span><span class="sxs-lookup"><span data-stu-id="ed653-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="ed653-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ed653-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="ed653-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed653-108">Parameters</span></span>

<span data-ttu-id="ed653-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ed653-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ed653-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ed653-110">Examples</span></span>
<span data-ttu-id="ed653-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ed653-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="ed653-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ed653-112">Example 1</span></span>

<span data-ttu-id="ed653-113">En el ejemplo siguiente se descarga un archivo de configuración de ejemplo del sitio de Microsoft y se escribe en el directorio del equipo del dispositivo de conector de nube:</span><span class="sxs-lookup"><span data-stu-id="ed653-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="ed653-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="ed653-114">Detailed Description</span></span>
<span data-ttu-id="ed653-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ed653-115"></span></span>

<span data-ttu-id="ed653-116">La versión actual del conector de nube requiere que proporcione varios parámetros en el archivo. ini; por ejemplo, parámetros como las direcciones IP de las máquinas virtuales para los componentes del conector de nube, los nombres de componentes, los parámetros de puerta de enlace, etc.</span><span class="sxs-lookup"><span data-stu-id="ed653-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="ed653-117">Este cmdlet, cuando se ejecuta en la máquina host del conector de nube, descarga un archivo. ini de ejemplo con ejemplos de configuración del sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed653-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="ed653-118">El cmdlet escribe el archivo en el directorio del equipo del dispositivo de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="ed653-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="ed653-119">El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="ed653-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ed653-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ed653-120">Input Types</span></span>
<span data-ttu-id="ed653-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed653-121"></span></span>

<span data-ttu-id="ed653-p104">Ninguno. El cmdlet Export-CcConfigurationSampleFile no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="ed653-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="ed653-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ed653-124">Return Types</span></span>
<span data-ttu-id="ed653-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed653-125"></span></span>

<span data-ttu-id="ed653-126">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ed653-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed653-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed653-127">See also</span></span>
<span data-ttu-id="ed653-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed653-128"></span></span>

[<span data-ttu-id="ed653-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ed653-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

