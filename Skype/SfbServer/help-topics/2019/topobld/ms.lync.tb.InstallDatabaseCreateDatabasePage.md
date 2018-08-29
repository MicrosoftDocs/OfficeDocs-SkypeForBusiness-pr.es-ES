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
ROBOTS: NOINDEX, NOFOLLOW
description: Seleccione las bases de datos que desea crear para su implementación. De forma predeterminada, la base de datos en el servidor de SQL definido en el sitio definido, se creará y se automáticamente implementar y configurar los archivos de base de datos basándose en el servidor de SQL que se va a colocar las bases de datos en.
ms.openlocfilehash: c5dde8ccd1e6202155b43b00a127f985ffb4961f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263411"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="bddfc-104">Instalar y crear bases de datos</span><span class="sxs-lookup"><span data-stu-id="bddfc-104">Install and Create Databases</span></span>

<span data-ttu-id="bddfc-105">Seleccione las bases de datos que desea crear para su implementación.</span><span class="sxs-lookup"><span data-stu-id="bddfc-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="bddfc-106">De forma predeterminada, la base de datos en el servidor de SQL definido en el sitio definido, se creará y se automáticamente implementar y configurar los archivos de base de datos basándose en el servidor de SQL que se va a colocar las bases de datos en.</span><span class="sxs-lookup"><span data-stu-id="bddfc-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="bddfc-107">**Seleccione las bases de datos que desea crear**: Active la casilla de verificación de las bases de datos que vaya a implementar y configurar.</span><span class="sxs-lookup"><span data-stu-id="bddfc-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="bddfc-108">Active la casilla de verificación de cualquiera o todas las bases de datos que se van a implementar.</span><span class="sxs-lookup"><span data-stu-id="bddfc-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="bddfc-109">El servidor SQL Server debe ya se han configurado para la instancia (si hay alguno) y deben estar abiertos los puertos de firewall para dar cabida a la instancia que va a implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bddfc-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="bddfc-110">Para obtener información detallada, vea [Configurar SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="bddfc-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="bddfc-111">**Opciones avanzadas**: haga clic en el servidor SQL Server y haga clic en el botón **Avanzadas** para elegir las opciones de la base de datos de ubicaciones de archivos en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bddfc-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="bddfc-112">Para obtener información detallada sobre la ubicación del archivo de base de datos avanzada, vea [Base de datos de instalación de uso de Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="bddfc-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="bddfc-113">**Atrás**: al hacer clic en este botón devuelve a la pantalla anterior (es posible que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="bddfc-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="bddfc-114">**Siguiente**: al hacer clic en este botón confirma la selección en el cuadro de diálogo actual y se abre el cuadro de diálogo siguiente para configurar la información adicional</span><span class="sxs-lookup"><span data-stu-id="bddfc-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="bddfc-115">**Cancelar**: al hacer clic en este botón se salga de la configuración y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bddfc-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="bddfc-116">Algunos, pero no todas las pantallas de configuración le preguntará si desea salir y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bddfc-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="bddfc-117">Si selecciona **Sí** cerrará la configuración actual y cerrar la configuración actual y volver al generador de topología.</span><span class="sxs-lookup"><span data-stu-id="bddfc-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="bddfc-118">Si selecciona **No** se devolverá para el cuadro de diálogo de configuración actual y podrá continuar la configuración.</span><span class="sxs-lookup"><span data-stu-id="bddfc-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="bddfc-119">**Ayuda**: al hacer clic en el botón **Ayuda** muestra esta información de ayuda asociada con el cuadro de diálogo de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="bddfc-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


