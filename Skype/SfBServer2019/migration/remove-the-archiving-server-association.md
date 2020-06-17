---
title: Quitar la asociación del servidor de archivado
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
description: Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia. Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752142"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="55ef4-105">Quitar la asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="55ef4-105">Remove the Archiving server association</span></span>

<span data-ttu-id="55ef4-106">Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="55ef4-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="55ef4-107">Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="55ef4-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="55ef4-108">Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="55ef4-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="55ef4-109">Para quitar la asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="55ef4-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="55ef4-110">En el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="55ef4-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="55ef4-111">Navegue hasta el nodo instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="55ef4-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="55ef4-112">En el generador de topologías, expanda grupos de servidores **front-end Enterprise Edition**, **servidores front-end Standard Edition**o **sitios de sucursal**, según dónde se haya definido el servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="55ef4-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="55ef4-113">Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda aplicaciones de sucursal con funciones de **supervivencia**.</span><span class="sxs-lookup"><span data-stu-id="55ef4-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="55ef4-114">Las **aplicaciones de sucursal** con funciones de supervivencia de la interfaz de usuario se aplican a un servidor de sucursal con funciones de supervivencia y una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="55ef4-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="55ef4-115">Haga clic con el botón secundario en el grupo de servidores, servidor o dispositivo asociado con el servidor de archivado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="55ef4-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="55ef4-116">En **Editar propiedades**, bajo **General**  >  **asociaciones**generales, desactive la casilla **asociar servidor de archivado** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55ef4-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="55ef4-117">Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de archivado que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="55ef4-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="55ef4-118">Haga clic con el botón secundario en el servidor de archivado y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="55ef4-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="55ef4-119">En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55ef4-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="55ef4-120">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="55ef4-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

