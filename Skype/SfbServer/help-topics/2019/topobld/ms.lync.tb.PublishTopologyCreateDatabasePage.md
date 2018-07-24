---
title: Crear base de datos
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Generador de topología proporciona una forma de instalar las bases de datos en un almacén de SQL Server. Al instalar las bases de datos mediante el uso de Topology Builder, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarios en el equipo de SQL Server especificado o el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si es necesario instalar una base de datos específica en un equipo específico, o si se debe instalar una base de datos combinada, debe usar el cmdlet Install-CsDatabase e interfaz de línea de comandos de Windows PowerShell en su lugar.
ms.openlocfilehash: 087bed64e0e1d53cd610433c5695899107a9aa71
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21066115"
---
# <a name="create-database"></a><span data-ttu-id="3c8af-106">Crear base de datos</span><span class="sxs-lookup"><span data-stu-id="3c8af-106">Create Database</span></span>
 
<span data-ttu-id="3c8af-107">Generador de topología proporciona una forma de instalar las bases de datos en un almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c8af-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="3c8af-108">Al instalar las bases de datos mediante el uso de Topology Builder, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarios en el equipo de SQL Server especificado o el clúster de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c8af-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="3c8af-109">Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="3c8af-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="3c8af-110">Si es necesario instalar una base de datos específica en un equipo específico, o si se debe instalar una base de datos combinada, debe usar el cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) e interfaz de línea de comandos de Windows PowerShell en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3c8af-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="3c8af-111">Creación de una base de datos</span><span class="sxs-lookup"><span data-stu-id="3c8af-111">Creating a Database</span></span>

1. <span data-ttu-id="3c8af-112">Haga clic en el Skype para el nodo de servidor empresarial y, a continuación, haga clic en **Instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="3c8af-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="3c8af-113">En el cuadro de diálogo **Instalar bases de datos** , en la página **Crear base de datos** , seleccione el nombre de dominio completo (FQDN) del almacén de SQL Server donde están las nuevas bases de datos que se creará.</span><span class="sxs-lookup"><span data-stu-id="3c8af-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="3c8af-p103">Haga clic en **Opciones avanzadas**. En el cuadro de diálogo **Seleccionar la ubicación de los archivos de base de datos**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3c8af-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
  - <span data-ttu-id="3c8af-p104">**Ubicar automáticamente los archivos de base de datos**. Si selecciona esta opción, el Generador de topologías usa un algoritmo integrado para elegir la ubicación de almacenamiento de los registros de bases de datos y los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="3c8af-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
  - <span data-ttu-id="3c8af-118">**Valores predeterminados de instancia de utilizar SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3c8af-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="3c8af-119">Si selecciona esta opción, no se usa el algoritmo integrado para elegir las ubicaciones de almacenamiento para los registros de la base de datos y archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="3c8af-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="3c8af-120">En su lugar, los archivos de registro y datos se almacenan en las ubicaciones especificadas por la ruta de acceso de valores predeterminados de SQL Server (estas rutas de acceso deben estar configurados en avanzada por un administrador de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="3c8af-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="3c8af-121">Los archivos de datos se almacenará en la ubicación predeterminada del archivo de datos de SQL Server, mientras que los archivos de registro se almacenará en la ubicación predeterminada del archivo de registro de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c8af-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="3c8af-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c8af-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="3c8af-123">En la página **Crear base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c8af-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="3c8af-124">En la página **Creación de base de datos completada**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3c8af-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

