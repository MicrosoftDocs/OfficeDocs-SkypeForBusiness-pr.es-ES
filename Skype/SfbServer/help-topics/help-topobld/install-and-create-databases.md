---
title: Instalar y crear bases de datos
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Seleccione las bases de datos que desea crear para su implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y será automáticamente implementar y configurar los archivos de base de datos basados en el SQL Server que se va a colocar las bases de datos en.
ms.openlocfilehash: cf838e66dc5e9592ba71dd9d44fa5fc333c6dbc7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-create-databases"></a><span data-ttu-id="c69de-104">Instalar y crear bases de datos</span><span class="sxs-lookup"><span data-stu-id="c69de-104">Install and Create Databases</span></span>
 
<span data-ttu-id="c69de-105">Seleccione las bases de datos que desea crear para su implementación.</span><span class="sxs-lookup"><span data-stu-id="c69de-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="c69de-106">De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y será automáticamente implementar y configurar los archivos de base de datos basados en el SQL Server que se va a colocar las bases de datos en.</span><span class="sxs-lookup"><span data-stu-id="c69de-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="c69de-107">**Seleccione las bases de datos que desea crear**: seleccione la casilla de verificación de las bases de datos que vaya a implementar y configurar.</span><span class="sxs-lookup"><span data-stu-id="c69de-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="c69de-108">Active la casilla de verificación de cualquiera o todas las bases de datos que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="c69de-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c69de-109">El SQL Server debe estar configurado previamente para la instancia (si existe) y puertos de firewall que deben abrirse para dar cabida a la instancia que se va a implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c69de-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="c69de-110">Para obtener información detallada, vea [Configurar SQL Server para la versión preliminar de 2013 de Lync Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="c69de-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="c69de-111">**Opciones avanzadas**: haga clic en el de SQL Server y haga clic en el botón **Opciones avanzadas** para elegir las opciones de la base de datos de ubicaciones de archivo de su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c69de-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="c69de-112">Para obtener detalles sobre la ubicación del archivo de base de datos avanzada, consulte la [Base de datos de instalación utilizando Lync Server Shell de administración de](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="c69de-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="c69de-113">**Atrás**: al pulsar este botón vuelve a la pantalla anterior (no siempre esté disponible, basándose en cómo llegó a este cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="c69de-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="c69de-114">**Siguiente**: este botón confirma la selección en el cuadro de diálogo actual y le lleva al siguiente cuadro de diálogo para configurar información adicional</span><span class="sxs-lookup"><span data-stu-id="c69de-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="c69de-115">**Cancelar**: este botón se salga de la configuración y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c69de-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="c69de-116">Algunos, pero no todas las pantallas de configuración le pedirá si desea salir y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c69de-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="c69de-117">Si se selecciona **Sí** cerrará la configuración actual y cerrar la configuración actual y volver al generador de topología.</span><span class="sxs-lookup"><span data-stu-id="c69de-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="c69de-118">Si selecciona **No** se devolverá en el cuadro de diálogo de configuración actual y podrá continuar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c69de-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="c69de-119">**Ayuda**: haga clic en el botón **Ayuda** muestra esta información de ayuda asociada con el cuadro de diálogo de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="c69de-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

