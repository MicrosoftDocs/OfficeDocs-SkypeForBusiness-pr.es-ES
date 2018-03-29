---
title: Crear base de datos
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: El generador de topología proporciona una forma para instalar las bases de datos en un almacén de SQL Server. Al instalar las bases de datos mediante el generador de topología, la aplicación lee la información de la topología y, a continuación, instala las bases de datos necesarios en el equipo de SQL Server especificado o el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos colocada, debe utilizar el cmdlet Install-CsDatabase e interfaz de línea de comandos de Windows PowerShell en su lugar.
ms.openlocfilehash: 9bee333e0b56a6eeb8f4363e6657be2fabfa1ace
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-database"></a><span data-ttu-id="59dde-106">Crear base de datos</span><span class="sxs-lookup"><span data-stu-id="59dde-106">Create Database</span></span>
 
<span data-ttu-id="59dde-107">El generador de topología proporciona una forma para instalar las bases de datos en un almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59dde-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="59dde-108">Al instalar las bases de datos mediante el generador de topología, la aplicación lee la información de la topología y, a continuación, instala las bases de datos necesarios en el equipo de SQL Server especificado o el clúster de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59dde-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="59dde-109">Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="59dde-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="59dde-110">Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos colocada, debe utilizar el cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) e interfaz de línea de comandos de Windows PowerShell en su lugar.</span><span class="sxs-lookup"><span data-stu-id="59dde-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="59dde-111">Creación de una base de datos</span><span class="sxs-lookup"><span data-stu-id="59dde-111">Creating a Database</span></span>

1. <span data-ttu-id="59dde-112">Haga clic en el Skype para Business Server 2015 nodo y, a continuación, haga clic en **Instalar la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="59dde-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="59dde-113">En el cuadro de diálogo **Instalar bases de datos** , en la página **Crear base de datos** , seleccione el nombre de dominio completo (FQDN) del almacén de SQL Server donde deben crearse las nuevas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="59dde-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="59dde-p103">Haga clic en **Opciones avanzadas**. En el cuadro de diálogo **Seleccionar la ubicación de los archivos de base de datos**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="59dde-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
  - <span data-ttu-id="59dde-p104">**Ubicar automáticamente los archivos de base de datos**. Si selecciona esta opción, el Generador de topologías usa un algoritmo integrado para elegir la ubicación de almacenamiento de los registros de bases de datos y los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="59dde-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
  - <span data-ttu-id="59dde-118">**Valores predeterminados de instancia de SQL Server de uso**.</span><span class="sxs-lookup"><span data-stu-id="59dde-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="59dde-119">Si selecciona esta opción, no se utiliza el algoritmo integrado para elegir las ubicaciones de almacenamiento para los archivos de datos y registros de base de datos.</span><span class="sxs-lookup"><span data-stu-id="59dde-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="59dde-120">En su lugar, los archivos de registro y datos se almacenan en las ubicaciones especificadas por la ruta de acceso de valores predeterminados de SQL Server (estas rutas deben configurarse en avanzada por un administrador de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="59dde-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="59dde-121">Archivos de datos se almacenarán en la ubicación predeterminada del archivo de datos de SQL Server, mientras que los archivos de registro se almacenará en la ubicación predeterminada del archivo de registro de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59dde-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="59dde-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="59dde-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="59dde-123">En la página **Crear base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="59dde-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="59dde-124">En la página **Creación de base de datos completada**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="59dde-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

