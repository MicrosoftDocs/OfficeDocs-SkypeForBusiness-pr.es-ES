---
title: Expansor de configuración de almacén de SQL
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de base de datos de SQL Server. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas tales como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de Administración Central.
ms.openlocfilehash: 3079f29a82f26dac42badcb8efb2945710b1f97d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373926"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="54fa6-105">Expansor de configuración de almacén de SQL</span><span class="sxs-lookup"><span data-stu-id="54fa6-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="54fa6-106">Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54fa6-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="54fa6-107">No puede usar el cuadro de diálogo **Editar propiedades** para realizar tareas tales como mover la base de datos del servidor de archivado de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="54fa6-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="54fa6-108">Además, no puede usar el cuadro de diálogo **Editar propiedades** para cambiar la instancia de SQL Server que hospeda el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="54fa6-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="54fa6-109">Editar las propiedades de una base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="54fa6-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="54fa6-110">Para cambiar la instancia de SQL Server que se usa en cualquier base de datos que no sea el almacén de Administración Central, complete el procedimiento siguiente en el generador de topología:</span><span class="sxs-lookup"><span data-stu-id="54fa6-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="54fa6-111">Para modificar una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="54fa6-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="54fa6-112">Seleccione la base de datos adecuada en el nodo **SQL almacena** y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="54fa6-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="54fa6-113">En el cuadro de diálogo **Editar propiedades** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="54fa6-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="54fa6-114">Para usar la instancia de SQL Server predeterminada, seleccione **Instancia predeterminada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54fa6-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="54fa6-115">Para usar una instancia con nombre de la base de datos, seleccione **Instancia con nombre**, escriba el nombre de instancia en el cuadro de texto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54fa6-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="54fa6-116">Debe escribir el nombre de instancia (por ejemplo, ArchivingInstance) y no la ruta completa de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54fa6-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="54fa6-117">Cuando se trabaja en el cuadro de diálogo **Editar propiedades** , Topology Builder no comprobará que la instancia de base de datos que ha escrito es una instancia válida.</span><span class="sxs-lookup"><span data-stu-id="54fa6-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="54fa6-118">Por ejemplo, si se sin darse cuenta typeArchivingInstanec como el nombre de instancia y, a continuación, haga clic en **Aceptar**, Topology Builder aceptará esa instancia no válida.</span><span class="sxs-lookup"><span data-stu-id="54fa6-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="54fa6-119">Antes de poder publicar esta topología, debe corregir este error: si no se encuentra una instancia de SQL Server, Topology Builder no crear esa instancia para usted.</span><span class="sxs-lookup"><span data-stu-id="54fa6-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

