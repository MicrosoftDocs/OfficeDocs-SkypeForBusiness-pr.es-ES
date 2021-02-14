---
title: Expansor de configuración de almacén SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de una SQL Server base de datos, debe cambiar la SQL Server de base de datos. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805520"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="4a923-105">Expansor de configuración de almacén SQL</span><span class="sxs-lookup"><span data-stu-id="4a923-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="4a923-106">Para editar las propiedades de una SQL Server base de datos, debe cambiar la SQL Server de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a923-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="4a923-107">No puede usar el cuadro **de diálogo** Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="4a923-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="4a923-108">Además, no puede  usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="4a923-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="4a923-109">Edición de las propiedades de una base de datos SQL Server datos</span><span class="sxs-lookup"><span data-stu-id="4a923-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="4a923-110">Para cambiar la instancia de SQL Server que usa cualquier base de datos que no sea el almacén de administración central, complete el siguiente procedimiento en el Generador de topologías:</span><span class="sxs-lookup"><span data-stu-id="4a923-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="4a923-111">Para modificar una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a923-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="4a923-112">Seleccione la base de datos adecuada en el **SQL almacena el** nodo y, a continuación, haga clic en Editar **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4a923-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="4a923-113">En el cuadro de diálogo **Editar propiedades**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4a923-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="4a923-114">Para usar la instancia SQL Server predeterminada, seleccione **Instancia predeterminada** y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="4a923-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="4a923-115">Para usar una instancia de base de datos con nombre, seleccione **Instancia con nombre**, indique un nombre en el cuadro de texto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a923-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="4a923-116">Solo debe escribir el nombre de instancia (por ejemplo, ArchivingInstance) y no toda la ruta SQL Server acceso.</span><span class="sxs-lookup"><span data-stu-id="4a923-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="4a923-117">Cuando trabaje en  el cuadro de diálogo Editar propiedades, el Generador de topologías no comprobará que la instancia de base de datos que ha especificado es una instancia válida.</span><span class="sxs-lookup"><span data-stu-id="4a923-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="4a923-118">Por ejemplo, si escribe AccidentalmenteArchivingInstanec como nombre de instancia y, a continuación, hace clic en **Aceptar,** el Generador de topologías aceptará esa instancia no válida.</span><span class="sxs-lookup"><span data-stu-id="4a923-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="4a923-119">Para poder publicar esta topología, debe corregir este error: si no se encuentra una instancia de SQL Server, el Generador de topologías no creará esa instancia por usted.</span><span class="sxs-lookup"><span data-stu-id="4a923-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

