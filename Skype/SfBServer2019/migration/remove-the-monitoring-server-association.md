---
title: Quitar la asociación del servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo front-end, el servidor front-end, el equipo de la sucursal y el servidor de la sucursal supervivientes relacionados. Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301100"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="3a71d-105">Quitar la asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="3a71d-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="3a71d-106">Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo front-end, el servidor front-end, el dispositivo de la sucursal que puede ser superviviente y el servidor de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="3a71d-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="3a71d-107">Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="3a71d-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="3a71d-108">Después de borrar la dependencia y eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.</span><span class="sxs-lookup"><span data-stu-id="3a71d-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="3a71d-109">Para quitar la Asociación de servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="3a71d-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="3a71d-110">En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="3a71d-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="3a71d-111">Vaya al nodo instalaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="3a71d-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="3a71d-112">En el generador de topología, expanda las **agrupaciones front end de Enterprise Edition**, **los servidores de aplicaciones para el usuario Standard Edition**o los **sitios de sucursales**, según dónde se defina el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="3a71d-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="3a71d-113">Si tiene asociado un servidor de sucursal, expanda **sitios de sucursales**, expanda el nombre del sitio de la sucursal y, a continuación, expanda **aplicaciones de sucursales**reutilizables.</span><span class="sxs-lookup"><span data-stu-id="3a71d-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a71d-114">Los **dispositivos** de la interfaz de usuario que son supervivientes se aplican a los servidores de sucursal con supervivencia y con la aplicación de rama superviviente.</span><span class="sxs-lookup"><span data-stu-id="3a71d-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="3a71d-115">Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de supervisión y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3a71d-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="3a71d-116">En **Editar propiedades**, en \*\*\*\* > **asociaciones**generales, desactive la casilla **asociar servidor de supervisión** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3a71d-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="3a71d-117">Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado al servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="3a71d-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="3a71d-118">Haga clic con el botón secundario en el servidor de supervisión y luego haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3a71d-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="3a71d-119">En **eliminar almacenes**dependientes, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3a71d-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="3a71d-120">Publique la topología, compruebe el estado de la replicación y ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3a71d-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

