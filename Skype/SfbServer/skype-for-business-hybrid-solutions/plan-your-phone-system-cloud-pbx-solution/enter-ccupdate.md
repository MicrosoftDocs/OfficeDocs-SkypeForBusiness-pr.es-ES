---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 'El cmdlet Enter-CcUpdate prepara el servidor host de la edición Cloud Connector de Skype empresarial para el proceso de actualización al ponerlo en el modo de mantenimiento. El dispositivo isdrained: es decir, todas las llamadas existentes se completarán, pero se rechazarán nuevas llamadas.'
ms.openlocfilehash: be57261b35cf5b5e6e8118c2a751eee1c8b5f2a7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287443"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="e9e4b-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e9e4b-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="e9e4b-105">El cmdlet Enter-CcUpdate prepara el servidor host de la edición Cloud Connector de Skype empresarial para el proceso de actualización al ponerlo en el modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="e9e4b-106">El dispositivo está "drenado", es decir, se completan todas las llamadas existentes, pero se rechazan nuevas llamadas.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="e9e4b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9e4b-107">Parameters</span></span>

<span data-ttu-id="e9e4b-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e9e4b-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e9e4b-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e9e4b-109">Examples</span></span>
<span data-ttu-id="e9e4b-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e4b-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="e9e4b-111">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e9e4b-111">Example 1</span></span>

<span data-ttu-id="e9e4b-112">En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización mediante la entrada en el modo de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="e9e4b-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="e9e4b-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e9e4b-113">Detailed Description</span></span>
<span data-ttu-id="e9e4b-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e4b-114"></span></span>

<span data-ttu-id="e9e4b-115">El cmdlet Enter-CcUpdate detendrá inmediatamente todos los servicios que finalizan cualquier llamada en curso y el dispositivo rechazará las llamadas nuevas, que se transfieren a otros dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="e9e4b-116">Debes asegurarte de que el resto de los dispositivos de producción tengan capacidad suficiente para manejar las llamadas desde el dispositivo que estás preparando para actualizar.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="e9e4b-p104">El modo de mantenimiento es útil si, por ejemplo, el dispositivo tiene habilitada la actualización automática y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="e9e4b-119">Después de instalar las actualizaciones, el dispositivo puede volver al modo de producción ejecutando el cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9e4b-120">Si decide actualizar manualmente un dispositivo de conector de nube, tendrá que actualizarlo dentro de 60 días después de que Microsoft publique la versión siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="e9e4b-121">Microsoft admite la versión publicada anteriormente del conector en la nube para 60 días después de que se publique la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="e9e4b-122">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e9e4b-122">Input Types</span></span>
<span data-ttu-id="e9e4b-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e4b-123"></span></span>

<span data-ttu-id="e9e4b-p106">Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e9e4b-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e9e4b-126">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e9e4b-126">Return Types</span></span>
<span data-ttu-id="e9e4b-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e4b-127"></span></span>

<span data-ttu-id="e9e4b-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e9e4b-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e9e4b-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9e4b-129">See also</span></span>
<span data-ttu-id="e9e4b-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e4b-130"></span></span>

[<span data-ttu-id="e9e4b-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e9e4b-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

