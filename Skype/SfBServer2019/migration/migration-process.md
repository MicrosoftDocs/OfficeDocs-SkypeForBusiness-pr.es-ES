---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre las pruebas de coexistencia.
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813418"
---
# <a name="migration-process"></a><span data-ttu-id="1eba3-104">Proceso de migración</span><span class="sxs-lookup"><span data-stu-id="1eba3-104">Migration process</span></span>

<span data-ttu-id="1eba3-105">El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="1eba3-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="1eba3-106">En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre las pruebas de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="1eba3-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="1eba3-107">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="1eba3-107">Side-By-Side Migration</span></span>

<span data-ttu-id="1eba3-108">En casi todas las migraciones, debe usar la ruta de migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="1eba3-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="1eba3-109">En una migración en paralelo, se implementa un nuevo servidor con Skype empresarial Server 2019 junto con un servidor correspondiente que ejecuta una versión anterior y, a continuación, se transfieren las operaciones al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="1eba3-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="1eba3-110">Si es necesario revertir a la versión anterior, solo tiene que desplazar las operaciones de vuelta a los servidores originales.</span><span class="sxs-lookup"><span data-stu-id="1eba3-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="1eba3-111">Tenga en cuenta que, en este caso, las reuniones nuevas programadas con clientes actualizados no funcionarán y los clientes también necesitarán cambiar de versión.</span><span class="sxs-lookup"><span data-stu-id="1eba3-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="1eba3-112">Pruebas de coexistencia</span><span class="sxs-lookup"><span data-stu-id="1eba3-112">Coexistence Testing</span></span>

<span data-ttu-id="1eba3-113">Una vez que haya implementado Skype empresarial Server 2019 en paralelo con la versión anterior, la implementación representa un estado de prueba de coexistencia de Skype empresarial Server 2019 y la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="1eba3-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="1eba3-114">Mientras se encuentre en este estado, es importante probar y asegurarse de que se inician los servicios, que cada sitio se puede administrar y que los clientes pueden comunicarse con los usuarios actuales y heredados.</span><span class="sxs-lookup"><span data-stu-id="1eba3-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="1eba3-115">Antes de la migración de todos los usuarios, es muy importante comprender el estado de cada implementación y asegurarse de que cada implementación es funcional y funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="1eba3-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="1eba3-116">Por lo general, la fase de pruebas de coexistencia se produce durante las pruebas piloto de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1eba3-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="1eba3-117">Los usuarios heredados se mueven a Skype empresarial Server 2019 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="1eba3-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="1eba3-118">Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Skype empresarial Server 2019, y se retirarán las aplicaciones y los grupos heredados de la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="1eba3-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
