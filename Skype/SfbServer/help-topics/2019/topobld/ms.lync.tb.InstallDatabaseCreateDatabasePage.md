---
title: Instalar y crear bases de datos
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Seleccione las bases de datos que desea crear para su implementación. De forma predeterminada, la base de datos en el servidor de SQL definido en el sitio definido, se creará y se automáticamente implementar y configurar los archivos de base de datos basándose en el servidor de SQL que se va a colocar las bases de datos en.
ms.openlocfilehash: 70bd185b4e559215df7d3623dc5591648e718ed9
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979361"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="b72ec-104">Instalar y crear bases de datos</span><span class="sxs-lookup"><span data-stu-id="b72ec-104">Install and Create Databases</span></span>
 
<span data-ttu-id="b72ec-105">Seleccione las bases de datos que desea crear para su implementación.</span><span class="sxs-lookup"><span data-stu-id="b72ec-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="b72ec-106">De forma predeterminada, la base de datos en el servidor de SQL definido en el sitio definido, se creará y se automáticamente implementar y configurar los archivos de base de datos basándose en el servidor de SQL que se va a colocar las bases de datos en.</span><span class="sxs-lookup"><span data-stu-id="b72ec-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="b72ec-107">**Seleccione las bases de datos que desea crear**: Active la casilla de verificación de las bases de datos que vaya a implementar y configurar.</span><span class="sxs-lookup"><span data-stu-id="b72ec-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="b72ec-108">Active la casilla de verificación de cualquiera o todas las bases de datos que se van a implementar.</span><span class="sxs-lookup"><span data-stu-id="b72ec-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b72ec-109">El servidor SQL Server debe ya se han configurado para la instancia (si hay alguno) y deben estar abiertos los puertos de firewall para dar cabida a la instancia que va a implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b72ec-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="b72ec-110">Para obtener información detallada, vea [Configurar SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="b72ec-110">For details, see [Configure SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="b72ec-111">**Opciones avanzadas**: haga clic en el servidor SQL Server y haga clic en el botón **Avanzadas** para elegir las opciones de la base de datos de ubicaciones de archivos en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b72ec-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="b72ec-112">Para obtener información detallada sobre la ubicación del archivo de base de datos avanzada, vea [Base de datos de instalación de uso de Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="b72ec-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="b72ec-113">**Atrás**: al hacer clic en este botón devuelve a la pantalla anterior (es posible que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="b72ec-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="b72ec-114">**Siguiente**: al hacer clic en este botón confirma la selección en el cuadro de diálogo actual y se abre el cuadro de diálogo siguiente para configurar la información adicional</span><span class="sxs-lookup"><span data-stu-id="b72ec-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="b72ec-115">**Cancelar**: al hacer clic en este botón se salga de la configuración y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b72ec-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="b72ec-116">Algunos, pero no todas las pantallas de configuración le preguntará si desea salir y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b72ec-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="b72ec-117">Si selecciona **Sí** cerrará la configuración actual y cerrar la configuración actual y volver al generador de topología.</span><span class="sxs-lookup"><span data-stu-id="b72ec-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="b72ec-118">Si selecciona **No** se devolverá para el cuadro de diálogo de configuración actual y podrá continuar la configuración.</span><span class="sxs-lookup"><span data-stu-id="b72ec-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="b72ec-119">**Ayuda**: al hacer clic en el botón **Ayuda** muestra esta información de ayuda asociada con el cuadro de diálogo de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="b72ec-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

