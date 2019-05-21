---
title: Expansor de configuración de almacén SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de la base de datos de SQL Server. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303021"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="0650e-105">Expansor de configuración de almacén SQL</span><span class="sxs-lookup"><span data-stu-id="0650e-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="0650e-106">Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0650e-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="0650e-107">No puede usar el cuadro de diálogo **Editar propiedades** para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="0650e-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="0650e-108">Además, no puede usar el cuadro de diálogo **Editar propiedades** para cambiar la instancia de SQL Server que hospeda el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="0650e-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="0650e-109">Editar las propiedades de una base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0650e-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="0650e-110">Para cambiar la instancia de SQL Server que se usa en cualquier base de datos que no sea el almacén de administración central, complete el procedimiento siguiente en el generador de topología:</span><span class="sxs-lookup"><span data-stu-id="0650e-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="0650e-111">Para modificar una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0650e-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="0650e-112">Seleccione la base de datos adecuada en el nodo **almacenes de SQL** y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0650e-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="0650e-113">En el cuadro de diálogo **Editar propiedades** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0650e-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="0650e-114">Para usar la instancia de SQL Server predeterminada, seleccione **instancia predeterminada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0650e-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="0650e-115">Para usar una instancia de base de datos con nombre, seleccione **instancia con nombre**, escriba el nombre de la instancia en el cuadro de texto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0650e-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="0650e-116">Solo debe escribir el nombre de la instancia (por ejemplo, ArchivingInstance) y no toda la ruta de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0650e-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="0650e-117">Cuando esté trabajando en el cuadro de diálogo **Editar propiedades** , el generador de topología no comprobará que la instancia de base de datos especificada sea válida.</span><span class="sxs-lookup"><span data-stu-id="0650e-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="0650e-118">Por ejemplo, si inadvertidamente typeArchivingInstanec como el nombre de la instancia y luego hace clic en **Aceptar**, el generador de topología aceptará esa instancia no válida.</span><span class="sxs-lookup"><span data-stu-id="0650e-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="0650e-119">Antes de poder publicar esta topología, debe corregir este error: Si no se puede encontrar una instancia de SQL Server, Topology Builder no creará esa instancia para usted.</span><span class="sxs-lookup"><span data-stu-id="0650e-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

