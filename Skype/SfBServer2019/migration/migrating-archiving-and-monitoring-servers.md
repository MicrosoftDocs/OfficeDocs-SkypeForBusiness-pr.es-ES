---
title: Migrar los servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de aplicaciones para el usuario. Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo de pruebas de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298200"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="89d70-104">Migrar los servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="89d70-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="89d70-105">Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="89d70-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="89d70-106">Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo de pruebas de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="89d70-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="89d70-107">Si desea mantener la funcionalidad de archivado y supervisión durante el proceso de migración, tenga en cuenta las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="89d70-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="89d70-108">Los datos de archivado y supervisión no se mueven a la implementación de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="89d70-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="89d70-109">Los datos que respaldas antes de dar de baja el entorno heredado serán tu historial de actividad en el entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="89d70-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="89d70-110">La versión heredada del servidor de archivado y del servidor de supervisión solo se puede asociar con un grupo de servidores front-end heredado.</span><span class="sxs-lookup"><span data-stu-id="89d70-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="89d70-111">En Skype empresarial Server 2019, el archivado y la supervisión ya no tienen roles de servidor, pero los servicios se integran en el grupo front-end de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="89d70-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="89d70-112">En el momento en que coexistan las implementaciones heredada de Skype empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en grupos heredados.</span><span class="sxs-lookup"><span data-stu-id="89d70-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="89d70-113">Archivado y supervisión en Skype empresarial Server 2019 recopilar datos para los usuarios alojados en los grupos de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="89d70-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89d70-114">Durante la fase de migración, cuando aún usa el servidor perimetral heredado con el nuevo grupo piloto de Skype empresarial Server 2019, la versión heredada del servidor de archivado continúa recopilando datos para los usuarios alojados en grupos heredados y archivado en Skype empresarial. El servidor 2019 reúne datos para usuarios alojados en grupos de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="89d70-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="89d70-115">Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Skype empresarial Server 2019, póngase en relación con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="89d70-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

