---
title: Escriba-CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: El cmdlet Enter-CcUpdate prepara el servidor host de Skype Empresarial Cloud Connector Edition para el proceso de actualización poniéndolo en modo de mantenimiento. El dispositivo isdrained, es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.
ms.openlocfilehash: f9b789bbd76bd3405617dc170af0695f9cbe94ed
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450514"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="f4e69-104">Escriba-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="f4e69-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="f4e69-105">El cmdlet Enter-CcUpdate prepara el servidor host de Skype Empresarial Cloud Connector Edition para el proceso de actualización poniéndolo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="f4e69-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="f4e69-106">El dispositivo se "vacía", es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.</span><span class="sxs-lookup"><span data-stu-id="f4e69-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="f4e69-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4e69-107">Parameters</span></span>

<span data-ttu-id="f4e69-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f4e69-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f4e69-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f4e69-109">Examples</span></span>
<span data-ttu-id="f4e69-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f4e69-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="f4e69-111">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f4e69-111">Example 1</span></span>

<span data-ttu-id="f4e69-112">En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización mediante la entrada en el modo de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="f4e69-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="f4e69-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="f4e69-113">Detailed Description</span></span>
<span data-ttu-id="f4e69-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f4e69-114"></span></span>

<span data-ttu-id="f4e69-115">El cmdlet ENTRAR CcUpdate detendrá inmediatamente todos los servicios que terminan las llamadas en curso y el dispositivo rechazará las llamadas nuevo, que se transfieren a otros dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="f4e69-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="f4e69-116">Deberá asegurarse de que los dispositivos de producción restantes tengan la suficiente capacidad para gestionar las llamadas del dispositivo en el que está preparando la actualización.</span><span class="sxs-lookup"><span data-stu-id="f4e69-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="f4e69-p104">El modo de mantenimiento es útil si, por ejemplo, el dispositivo tiene habilitada la actualización automática y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="f4e69-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="f4e69-119">Después de instalar las actualizaciones, el dispositivo puede regresar al modo de producción con el cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="f4e69-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4e69-120">Si decide actualizar manualmente un dispositivo de conector en la nube, debe actualizar dentro de 60 días después de que Microsoft lance la siguiente versión.</span><span class="sxs-lookup"><span data-stu-id="f4e69-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="f4e69-121">Microsoft admite la versión publicada anteriormente del conector en la nube para 60 días después de que se publique la nueva versión</span><span class="sxs-lookup"><span data-stu-id="f4e69-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="f4e69-122">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f4e69-122">Input Types</span></span>
<span data-ttu-id="f4e69-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f4e69-123"></span></span>

<span data-ttu-id="f4e69-p106">Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="f4e69-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f4e69-126">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="f4e69-126">Return Types</span></span>
<span data-ttu-id="f4e69-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f4e69-127"></span></span>

<span data-ttu-id="f4e69-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f4e69-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f4e69-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4e69-129">See also</span></span>
<span data-ttu-id="f4e69-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f4e69-130"></span></span>

[<span data-ttu-id="f4e69-131">Salir CcUpdate</span><span class="sxs-lookup"><span data-stu-id="f4e69-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

