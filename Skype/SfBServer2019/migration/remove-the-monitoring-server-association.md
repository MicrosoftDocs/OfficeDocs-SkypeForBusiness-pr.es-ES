---
title: Quitar la asociación del servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo de Front-End asociado, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia. Para editar las propiedades del grupo de servidores Front-End, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de desactivar la dependencia y eliminar el servidor en el generador, que se le notifique que también se eliminará el objeto de almacén de base de datos asociada en el generador de topología.
ms.openlocfilehash: 854e95969d08d14d626bb374073091ae4ae39630
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892705"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="d71a2-105">Quitar la asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="d71a2-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="d71a2-106">Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo de servidores, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia de Front-End asociado.</span><span class="sxs-lookup"><span data-stu-id="d71a2-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="d71a2-107">Editar las propiedades del grupo de servidores Front-End, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia para quitar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="d71a2-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="d71a2-108">Después de desactivar la dependencia y eliminar el servidor en el generador, que se le notifique que también se eliminará el objeto de almacén de base de datos asociada en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="d71a2-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="d71a2-109">Para quitar la asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="d71a2-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="d71a2-110">En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="d71a2-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d71a2-111">Desplácese hasta el nodo de instalaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="d71a2-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="d71a2-112">En el generador de topologías, expanda **grupos de servidores Front-End de Enterprise Edition**, **Standard Edition servidor front-end**o **sitios de sucursal**, dependiendo de dónde se haya definido el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d71a2-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="d71a2-113">Si tiene un servidor de sucursal con funciones de supervivencia asociado, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda **Aplicaciones de sucursal con funciones de supervivencia**.</span><span class="sxs-lookup"><span data-stu-id="d71a2-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d71a2-114">**Aplicaciones de sucursal con funciones de supervivencia** en la interfaz de usuario se aplica a un servidor de sucursal con funciones de supervivencia y aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d71a2-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="d71a2-115">Haga clic en el grupo de servidores, servidor o dispositivo que está asociada con el servidor de supervisión y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d71a2-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="d71a2-116">En **Editar propiedades**, en **General** > **asociaciones**, desactive la casilla de verificación de **Asociar el servidor de supervisión** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d71a2-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="d71a2-117">Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d71a2-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="d71a2-118">Haga clic en el servidor de supervisión y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d71a2-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="d71a2-119">En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d71a2-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="d71a2-120">Publique la topología, compruebe el estado de replicación y ejecute la Skype para el Asistente para la implementación de Business Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d71a2-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

