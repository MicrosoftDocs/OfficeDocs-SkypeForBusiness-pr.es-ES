---
title: 'Compatibilidad con la virtualización en Skype empresarial Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Obtenga información sobre la compatibilidad de la virtualización con Skype empresarial Server 2019.'
ms.openlocfilehash: b4524b1284a85e7ab372b415d45c2005f8212887
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755814"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="c45db-103">Compatibilidad con la virtualización en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c45db-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="c45db-104">Skype empresarial Server 2019 es compatible con la virtualización.</span><span class="sxs-lookup"><span data-stu-id="c45db-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="c45db-105">Aunque se admite la virtualización, hay algunos puntos clave que hay que recordar:</span><span class="sxs-lookup"><span data-stu-id="c45db-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="c45db-106">Mantener una relación 1:1 de CPU virtual a CPU física.</span><span class="sxs-lookup"><span data-stu-id="c45db-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="c45db-107">No mueva un servidor invitado mientras está en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="c45db-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="c45db-108">No se admite la migración de un sistema activo y la portabilidad de una máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="c45db-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="c45db-109">Deshabilite la tecnología Hyper-Threading en todos los hosts.</span><span class="sxs-lookup"><span data-stu-id="c45db-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="c45db-110">No configure la memoria dinámica en los servidores host.</span><span class="sxs-lookup"><span data-stu-id="c45db-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="c45db-111">Use discos fijos o de paso a través en lugar de discos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="c45db-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="c45db-112">Permitir una sobrecarga del 6-10 por ciento para los hipervisores aparte de lo que requiere el invitado virtual.</span><span class="sxs-lookup"><span data-stu-id="c45db-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="c45db-113">Hipervisores compatibles</span><span class="sxs-lookup"><span data-stu-id="c45db-113">Supported hypervisors</span></span>

<span data-ttu-id="c45db-114">SfB Server 2019 es compatible con Windows Server 2016 y Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c45db-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="c45db-115">Para los hipervisores de terceros, necesita un hipervisor que haya pasado las pruebas del programa de validación de virtualización del servidor (SVVP) para el sistema operativo relevante.</span><span class="sxs-lookup"><span data-stu-id="c45db-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="c45db-116">Consulte las [versiones de Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) en la lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="c45db-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="c45db-117">Consulte las [versiones de Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) en la lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="c45db-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="c45db-118">Herramienta stress and Performance</span><span class="sxs-lookup"><span data-stu-id="c45db-118">Stress and performance tool</span></span>

<span data-ttu-id="c45db-119">La herramienta de esfuerzo y rendimiento de Skype empresarial Server 2019 incluye herramientas que simplifican la planeación de la capacidad de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c45db-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="c45db-120">La herramienta de esfuerzo y rendimiento de Skype empresarial Server 2019 le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="c45db-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="c45db-121">Simplificar la planeación de hardware para Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c45db-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="c45db-122">Proporcionar un mayor conocimiento y procedimientos recomendados para ajustar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="c45db-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="c45db-123">Medir el rendimiento de las implementaciones previstas de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c45db-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="c45db-124">Puede descargar la herramienta desde [aquí](https://www.microsoft.com/download/details.aspx?id=101447).</span><span class="sxs-lookup"><span data-stu-id="c45db-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
