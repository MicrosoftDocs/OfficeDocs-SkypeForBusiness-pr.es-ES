---
title: Crear base de datos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: El generador de topología proporciona una forma de instalar bases de datos en un almacén de SQL Server. Al instalar bases de datos con el generador de topología, la aplicación Lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server especificado o en el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos ordenada, debe usar la interfaz de línea de comandos de Windows PowerShell y el cmdlet install-CsDatabase en su lugar.
ms.openlocfilehash: 02d754870cb2d2db16424474a68b8ea0245191f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684853"
---
# <a name="create-database"></a><span data-ttu-id="3c07d-106">Crear base de datos</span><span class="sxs-lookup"><span data-stu-id="3c07d-106">Create Database</span></span>
 
<span data-ttu-id="3c07d-107">El generador de topología proporciona una forma de instalar bases de datos en un almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c07d-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="3c07d-108">Al instalar bases de datos con el generador de topología, la aplicación Lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server especificado o en el clúster de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c07d-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="3c07d-109">Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="3c07d-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="3c07d-110">Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos ordenada, debe usar la interfaz de línea de comandos de Windows PowerShell y el cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3c07d-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="3c07d-111">Creación de una base de datos</span><span class="sxs-lookup"><span data-stu-id="3c07d-111">Creating a Database</span></span>

1. <span data-ttu-id="3c07d-112">Haga clic en el nodo de Skype empresarial Server 2015 y, a continuación, haga clic en **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="3c07d-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="3c07d-113">En el cuadro de diálogo **instalar bases** de datos, en la página **crear base de datos** , seleccione el nombre de dominio completo (FQDN) del almacén SQL Server en el que se van a crear las nuevas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="3c07d-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="3c07d-p103">Haga clic en **Opciones avanzadas**. En el cuadro de diálogo **Seleccionar la ubicación de los archivos de base de datos**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3c07d-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="3c07d-p104">**Ubicar automáticamente los archivos de base de datos**. Si selecciona esta opción, el Generador de topologías usa un algoritmo integrado para elegir la ubicación de almacenamiento de los registros de bases de datos y los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="3c07d-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="3c07d-118">**Use los valores predeterminados de instancia de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3c07d-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="3c07d-119">Si selecciona esta opción, el algoritmo integrado no se usa para elegir las ubicaciones de almacenamiento de los archivos de datos y los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c07d-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="3c07d-120">En su lugar, los archivos de registro y de datos se almacenan en las ubicaciones especificadas por la ruta de acceso de valores predeterminados de SQL Server (estas rutas deben estar configuradas por un administrador de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="3c07d-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="3c07d-121">Los archivos de datos se almacenarán en la ubicación predeterminada de los archivos de datos de SQL Server, mientras que los archivos de registro se almacenarán en la ubicación predeterminada del archivo de registro de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c07d-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="3c07d-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c07d-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="3c07d-123">En la página **Crear base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c07d-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="3c07d-124">En la página **Creación de base de datos completada**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3c07d-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

