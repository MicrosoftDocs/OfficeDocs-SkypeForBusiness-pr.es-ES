---
title: Crear base de datos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Topology Builder proporciona una forma de instalar bases de datos en un SQL Server web. Al instalar bases de datos mediante el Generador de topologías, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server o el clúster SQL Server especificado. Es el único tipo de instalación de bases de datos disponible mediante Topology Builder. Si necesita instalar una base de datos específica en un equipo específico o si debe instalar una base de datos instalada Windows PowerShell, debe usar una interfaz de línea de comandos y el cmdlet Install-CsDatabase en su lugar.
ms.openlocfilehash: 1092840305d1a455aa094776ae757cf074f7e89a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822290"
---
# <a name="create-database"></a><span data-ttu-id="5479d-106">Crear base de datos</span><span class="sxs-lookup"><span data-stu-id="5479d-106">Create Database</span></span>
 
<span data-ttu-id="5479d-107">Topology Builder proporciona una forma de instalar bases de datos en un SQL Server web.</span><span class="sxs-lookup"><span data-stu-id="5479d-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="5479d-108">Al instalar bases de datos mediante el Generador de topologías, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server o el clúster SQL Server especificado.</span><span class="sxs-lookup"><span data-stu-id="5479d-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="5479d-109">Es el único tipo de instalación de bases de datos disponible mediante Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="5479d-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="5479d-110">Si necesita instalar una base de datos específica en un equipo específico o si debe instalar una base de datos instalada Windows PowerShell, debe usar una interfaz de línea de comandos y el cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5479d-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="5479d-111">Creación de una base de datos</span><span class="sxs-lookup"><span data-stu-id="5479d-111">Creating a Database</span></span>

1. <span data-ttu-id="5479d-112">Haga clic en el nodo de Skype Empresarial Server y, a continuación, haga clic **en Instalar base de datos.**</span><span class="sxs-lookup"><span data-stu-id="5479d-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="5479d-113">En el cuadro **de** diálogo  Instalar bases de datos, en la página Crear base de datos, seleccione el nombre de dominio completo (FQDN) del almacén de SQL Server donde se crearán las nuevas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5479d-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="5479d-p103">Haga clic en **Avanzadas**. En el cuadro de diálogo de **selección de la ubicación del archivo de base de datos**, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5479d-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="5479d-p104">**Automatically determine database file location**. Si selecciona esta opción, Topology Builder usa un algoritmo integrado para elegir la ubicación de almacenamiento para los registros de las bases de datos y los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="5479d-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="5479d-118">**Use SQL Server instance defaults**.</span><span class="sxs-lookup"><span data-stu-id="5479d-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="5479d-119">Si selecciona esta opción, no se usa el algoritmo integrado para elegir las ubicaciones de almacenamiento para los registros de las bases de datos y los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="5479d-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="5479d-120">Por el contrario, los archivos de datos y registros se almacenan en las ubicaciones especificadas por las rutas de acceso predeterminadas de SQL Server (estas rutas debe configurarlas previamente un administrador de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="5479d-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="5479d-121">Los archivos de datos se almacenarán en la ubicación de archivos de datos de SQL Server predeterminada, mientras que los archivos de registro se almacenarán en la ubicación de archivos de registro de SQL Server predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5479d-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="5479d-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5479d-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="5479d-123">En la página **Crear base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5479d-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="5479d-124">En la página que indica que **ha finalizado la creación de la base de datos**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5479d-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

