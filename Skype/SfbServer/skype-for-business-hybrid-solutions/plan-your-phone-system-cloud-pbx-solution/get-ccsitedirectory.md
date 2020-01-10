---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: El cmdlet Get-CcSiteDirectory muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de conector de nube.
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003370"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="81d9e-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="81d9e-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="81d9e-106">El cmdlet Get-CcSiteDirectory muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="81d9e-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="81d9e-107">La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="81d9e-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="81d9e-108">Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="81d9e-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="81d9e-109">Este cmdlet se aplica a Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="81d9e-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="81d9e-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81d9e-110">Parameters</span></span>

<span data-ttu-id="81d9e-111">Ninguno</span><span class="sxs-lookup"><span data-stu-id="81d9e-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="81d9e-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="81d9e-112">Examples</span></span>
<span data-ttu-id="81d9e-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="81d9e-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="81d9e-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="81d9e-114">Example 1</span></span>

<span data-ttu-id="81d9e-115">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de configuración y máquinas virtuales de los componentes del conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="81d9e-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="81d9e-116">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="81d9e-116">Detailed Description</span></span>
<span data-ttu-id="81d9e-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81d9e-117"></span></span>

<span data-ttu-id="81d9e-118">Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos del conector de nube se pueden combinar en sitios.</span><span class="sxs-lookup"><span data-stu-id="81d9e-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="81d9e-119">Los usuarios se asignan a sitios en lugar de a los dispositivos de conexión de la nube.</span><span class="sxs-lookup"><span data-stu-id="81d9e-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="81d9e-120">Cada sitio tiene una carpeta compartida en la que se almacenan los archivos de instalación del VHD básico y del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="81d9e-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="81d9e-121">Los dispositivos usan esta carpeta durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="81d9e-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="81d9e-122">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="81d9e-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="81d9e-123">Puede cambiar la ruta de acceso mediante el cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="81d9e-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="81d9e-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="81d9e-124">Input Types</span></span>
<span data-ttu-id="81d9e-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81d9e-125"></span></span>

<span data-ttu-id="81d9e-p104">Ninguno. El cmdlet Get-CcSiteDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="81d9e-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="81d9e-128">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="81d9e-128">Return Types</span></span>
<span data-ttu-id="81d9e-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81d9e-129"></span></span>

<span data-ttu-id="81d9e-130">Este comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="81d9e-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81d9e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81d9e-131">See also</span></span>
<span data-ttu-id="81d9e-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81d9e-132"></span></span>

[<span data-ttu-id="81d9e-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="81d9e-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

