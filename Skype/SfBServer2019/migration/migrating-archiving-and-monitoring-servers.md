---
title: Migrar los servidores de archivado y supervisión
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
description: Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar el archivado y la supervisión al grupo piloto de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752672"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="1180c-104">Migrar los servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="1180c-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="1180c-105">Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1180c-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="1180c-106">Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar el archivado y la supervisión al grupo piloto de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="1180c-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="1180c-107">Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1180c-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="1180c-108">Los datos de archivado y supervisión no se mueven a la implementación de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1180c-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="1180c-109">Los datos que realices en la copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en el entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="1180c-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="1180c-110">La versión heredada del servidor de archivado y el servidor de supervisión solo se pueden asociar a un grupo de servidores front-end heredado.</span><span class="sxs-lookup"><span data-stu-id="1180c-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="1180c-111">En Skype empresarial Server 2019, el archivado y la supervisión ya no tienen roles de servidor, sino que se integran en el grupo de servidores front-end de la 2019 de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1180c-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="1180c-112">Durante el tiempo que coexisten las implementaciones heredadas y de Skype empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios hospedados en grupos de servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="1180c-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="1180c-113">Archivado y supervisión en Skype empresarial Server 2019 recopilar datos para los usuarios hospedados en grupos de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="1180c-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1180c-114">Durante la fase de migración, cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Skype empresarial Server 2019, la versión heredada del servidor de archivado continúa recopilando datos para los usuarios alojados en grupos de servidores heredados y el archivado en Skype empresarial Server 2019 recopila datos para los usuarios alojados en grupos de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1180c-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="1180c-115">Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Skype empresarial Server 2019, consulte al proveedor Cuándo y cómo debe integrar la solución de terceros con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1180c-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

