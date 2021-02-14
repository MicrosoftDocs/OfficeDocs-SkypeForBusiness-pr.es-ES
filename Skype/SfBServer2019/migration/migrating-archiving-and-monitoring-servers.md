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
description: Si implementó el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype Empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar archivado y supervisión a su grupo piloto de Skype Empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752672"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="81752-104">Migrar los servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="81752-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="81752-105">Si implementó el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype Empresarial Server 2019 después de migrar los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="81752-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="81752-106">Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar archivado y supervisión a su grupo piloto de Skype Empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="81752-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="81752-107">Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="81752-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="81752-108">Los datos de archivado y los datos de supervisión no se mueven a la implementación de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="81752-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="81752-109">Los datos de los que se hace una copia de seguridad antes de retirar el entorno heredado serán su historial de actividad en el entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="81752-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="81752-110">La versión heredada del servidor de archivado y del servidor de supervisión solo se puede asociar a un grupo de servidores front-end heredado.</span><span class="sxs-lookup"><span data-stu-id="81752-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="81752-111">En Skype Empresarial Server 2019, el archivado y la supervisión ya no son roles de servidor, sino servicios integrados en el grupo de servidores front-end de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="81752-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="81752-112">Durante el tiempo en que coexisten las implementaciones heredadas y de Skype Empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios que están en grupos heredados.</span><span class="sxs-lookup"><span data-stu-id="81752-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="81752-113">El archivado y la supervisión en Skype Empresarial Server 2019 recopilan datos para los usuarios que están en grupos de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="81752-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81752-114">Durante la fase de migración cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Skype Empresarial Server 2019, la versión heredada del servidor de archivado sigue recopilando datos para los usuarios que se encuentran en grupos heredados y el archivado en Skype Empresarial Server 2019 recopila datos para los usuarios que están en grupos de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="81752-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="81752-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="81752-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

