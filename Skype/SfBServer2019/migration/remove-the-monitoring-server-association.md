---
title: Quitar la asociación del servidor de supervisión
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
description: Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia del grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en topology Builder.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753422"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="8bf5a-105">Quitar la asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="8bf5a-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="8bf5a-106">Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="8bf5a-107">Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="8bf5a-108">Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="8bf5a-109">Para quitar la asociación del Servidor de supervisión:</span><span class="sxs-lookup"><span data-stu-id="8bf5a-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="8bf5a-110">En el servidor front-end de Skype Empresarial Server 2019, abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="8bf5a-111">Navegue hasta el nodo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="8bf5a-112">En topology Builder, expanda grupos de servidores **front-end Enterprise Edition,** servidores **front-end Standard Edition** o sitios de sucursal, en función de dónde esté definido el servidor de supervisión. </span><span class="sxs-lookup"><span data-stu-id="8bf5a-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="8bf5a-113">Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **Sitios de** sucursal, expanda el nombre del sitio de sucursal y, a continuación, expanda Aplicaciones de sucursal con funciones **de supervivencia.**</span><span class="sxs-lookup"><span data-stu-id="8bf5a-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8bf5a-114">**Las aplicaciones de sucursal con funciones** de supervivencia de la interfaz de usuario se aplican tanto al servidor de sucursal con funciones de supervivencia como a la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="8bf5a-115">Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado con el servidor de supervisión y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="8bf5a-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="8bf5a-116">En **Editar propiedades**, en Asociaciones **generales,** desactive la casilla Asociar servidor de supervisión y, a continuación, haga clic en  >   **Aceptar.** </span><span class="sxs-lookup"><span data-stu-id="8bf5a-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="8bf5a-117">Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="8bf5a-118">Haga clic con el botón secundario en el servidor de supervisión y, a continuación, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="8bf5a-119">En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="8bf5a-120">Publique la topología, compruebe el estado de replicación y ejecute el Asistente para la implementación de Skype Empresarial Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8bf5a-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

