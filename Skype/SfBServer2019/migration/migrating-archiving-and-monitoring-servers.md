---
title: Migración de servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si ha implementado el servidor de archivado y el servidor de supervisión en el entorno heredado, puede implementar estos servidores en su Skype para entorno empresarial Server 2019 después de migrar los grupos de servidores Front-End. Sin embargo, si la funcionalidad de supervisión y archivado son críticos para la organización, debe agregar el archivado y supervisión a su Skype para el grupo piloto Business Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896095"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="2c4b7-104">Migración de servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="2c4b7-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="2c4b7-105">Si ha implementado el servidor de archivado y el servidor de supervisión en el entorno heredado, puede implementar estos servidores en su Skype para entorno empresarial Server 2019 después de migrar los grupos de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="2c4b7-106">Sin embargo, si la funcionalidad de supervisión y archivado son críticos para la organización, debe agregar el archivado y supervisión a su Skype para el grupo piloto Business Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="2c4b7-107">Si desea la funcionalidad de archivado y supervisión durante el proceso de migración, tenga en cuenta las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="2c4b7-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="2c4b7-108">Datos de archivado y supervisión de datos no se mueven a la Skype para la implementación empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="2c4b7-109">Los datos que la copia de seguridad antes de retirar el entorno heredado será el historial de actividad en el entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="2c4b7-110">La versión heredada de servidor de archivado y el servidor de supervisión se puede asociar solo con un grupo de servidores Front-End heredado.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="2c4b7-111">En Skype para Business Server 2019, archivado y supervisión ya no son roles de servidor, pero los servicios integrados en el Skype para el grupo de servidores Front-End de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="2c4b7-112">Durante el tiempo que su heredado y Skype para las implementaciones empresariales Server 2019 coexistir, la versión antigua de servidor de archivado y el servidor de supervisión recopilar datos para los usuarios alojados en grupos de servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="2c4b7-113">Archivado y supervisión de Skype para Business Server 2019 recopilan datos para los usuarios alojados en Skype para grupos de negocio Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2c4b7-114">Durante la fase de migración cuando se siguen usando su servidor perimetral heredado con el nuevo Skype para Business Server 2019 continúa con el grupo piloto, la versión antigua de servidor de archivado para recopilar datos para los usuarios alojado en grupos de servidores heredados y Archiving en Skype para la empresa Servidor 2019 recopila datos de los usuarios alojados en Skype para grupos de negocio Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="2c4b7-115">Si usa un tercero de archivado y supervisión solución junto con archivado y supervisión de Skype para 2019 de servidor empresarial, póngase en contacto con su proveedor acerca de cómo y cuándo es necesario integrar la solución de terceros con Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2c4b7-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

