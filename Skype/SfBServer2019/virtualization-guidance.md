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
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565959"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="f40d2-103">Compatibilidad con la virtualización en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="f40d2-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="f40d2-104">Skype empresarial Server 2019 es compatible con la virtualización.</span><span class="sxs-lookup"><span data-stu-id="f40d2-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="f40d2-105">Aunque se admite la virtualización, hay algunos puntos clave que hay que recordar:</span><span class="sxs-lookup"><span data-stu-id="f40d2-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="f40d2-106">Mantener una relación 1:1 de CPU virtual a CPU física.</span><span class="sxs-lookup"><span data-stu-id="f40d2-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="f40d2-107">No mueva un servidor invitado mientras está en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="f40d2-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="f40d2-108">No se admite la migración de un sistema activo y la portabilidad de una máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="f40d2-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="f40d2-109">Deshabilite la tecnología Hyper-Threading en todos los hosts.</span><span class="sxs-lookup"><span data-stu-id="f40d2-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="f40d2-110">No configure la memoria dinámica en los servidores host.</span><span class="sxs-lookup"><span data-stu-id="f40d2-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="f40d2-111">Use discos fijos o de paso a través en lugar de discos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f40d2-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="f40d2-112">Permitir una sobrecarga del 6-10 por ciento para los hipervisores aparte de lo que requiere el invitado virtual.</span><span class="sxs-lookup"><span data-stu-id="f40d2-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="f40d2-113">Hipervisores compatibles</span><span class="sxs-lookup"><span data-stu-id="f40d2-113">Supported hypervisors</span></span>

<span data-ttu-id="f40d2-114">SfB Server 2019 es compatible con Windows Server 2016 y Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f40d2-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="f40d2-115">Para los hipervisores de terceros, necesita un hipervisor que haya pasado las pruebas del programa de validación de virtualización del servidor (SVVP) para el sistema operativo relevante.</span><span class="sxs-lookup"><span data-stu-id="f40d2-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="f40d2-116">Consulte las [versiones de Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) en la lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="f40d2-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="f40d2-117">Consulte las [versiones de Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) en la lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="f40d2-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
