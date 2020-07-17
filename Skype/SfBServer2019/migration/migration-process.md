---
title: Proceso de migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752642"
---
# <a name="migration-process"></a><span data-ttu-id="ed017-104">Proceso de migración</span><span class="sxs-lookup"><span data-stu-id="ed017-104">Migration process</span></span>

<span data-ttu-id="ed017-105">El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ed017-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="ed017-106">Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="ed017-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="ed017-107">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="ed017-107">Side-By-Side Migration</span></span>

<span data-ttu-id="ed017-108">En casi todas las migraciones se debe usar la vía de la migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ed017-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="ed017-109">En una migración en paralelo, se implementa un nuevo servidor con Skype empresarial Server 2019 junto con un servidor correspondiente que ejecuta una versión anterior y, a continuación, se transfieren las operaciones al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="ed017-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="ed017-110">Si es necesario revertir a la versión anterior, solo tiene que desplazar las operaciones de vuelta a los servidores originales.</span><span class="sxs-lookup"><span data-stu-id="ed017-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="ed017-111">No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="ed017-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="ed017-112">Prueba de coexistencia</span><span class="sxs-lookup"><span data-stu-id="ed017-112">Coexistence Testing</span></span>

<span data-ttu-id="ed017-113">Una vez que haya implementado Skype empresarial Server 2019 en paralelo con la versión anterior, la implementación representa un estado de prueba de coexistencia de Skype empresarial Server 2019 y la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="ed017-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="ed017-114">Durante este estado, es importante comprobar y confirmar que los servicios se han iniciado, que todos los sitios se pueden administrar y que los clientes se pueden comunicar con los usuarios tanto actuales como heredados.</span><span class="sxs-lookup"><span data-stu-id="ed017-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="ed017-115">Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe.</span><span class="sxs-lookup"><span data-stu-id="ed017-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="ed017-116">Normalmente, la fase de pruebas de coexistencia existe en las pruebas piloto de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ed017-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="ed017-117">Los usuarios heredados se mueven a Skype empresarial Server 2019 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed017-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="ed017-118">Después de realizar las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Skype empresarial Server 2019 y se retiran las aplicaciones y los grupos de servidores heredados de la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="ed017-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
