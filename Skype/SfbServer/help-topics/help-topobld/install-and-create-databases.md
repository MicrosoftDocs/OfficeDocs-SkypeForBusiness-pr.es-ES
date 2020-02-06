---
title: Instalar y crear bases de datos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Seleccione las bases de datos que desea crear para su implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido del sitio definido e implementará y configurará automáticamente los archivos de base de datos basándose en el SQL Server en el que está colocando las bases de datos.
ms.openlocfilehash: 72eebc4523eb538762adcfd3c2ee7138853a80ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819832"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="cebd5-104">Instalar y crear bases de datos</span><span class="sxs-lookup"><span data-stu-id="cebd5-104">Install and Create Databases</span></span>

<span data-ttu-id="cebd5-105">Seleccione las bases de datos que desea crear para su implementación.</span><span class="sxs-lookup"><span data-stu-id="cebd5-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="cebd5-106">De forma predeterminada, la base de datos se creará en el SQL Server definido del sitio definido e implementará y configurará automáticamente los archivos de base de datos basándose en el SQL Server en el que está colocando las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cebd5-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="cebd5-107">**Seleccione las bases de datos que desea crear**: Marque la casilla de verificación de las bases de datos que desea implementar y configurar.</span><span class="sxs-lookup"><span data-stu-id="cebd5-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="cebd5-108">Seleccione la casilla de cualquiera o todas las bases de datos que va a implementar.</span><span class="sxs-lookup"><span data-stu-id="cebd5-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="cebd5-109">SQL Server ya debe estar configurado para la instancia (si existe) y los puertos de Firewall deben estar abiertos para poder albergar la instancia en la que está implementando las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cebd5-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="cebd5-110">Para obtener más información, consulte [configurar SQL Server para Lync server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="cebd5-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="cebd5-111">**Avanzado**: haga clic en el servidor SQL y haga clic en el botón **avanzadas** para elegir las opciones de ubicación de los archivos de base de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cebd5-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="cebd5-112">Para obtener información sobre la ubicación avanzada de archivos de base de datos, vea [instalación de bases de datos con el shell de administración de Lync Server](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="cebd5-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="cebd5-113">**Atrás**: al hacer clic en este botón, se vuelve a la pantalla anterior (es posible que no siempre esté disponible, en función de cómo llegues a este cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="cebd5-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="cebd5-114">**Después**: al hacer clic en este botón confirma la selección en el cuadro de diálogo actual y le lleva al siguiente cuadro de diálogo para configurar información adicional</span><span class="sxs-lookup"><span data-stu-id="cebd5-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="cebd5-115">**Cancelar**: al hacer clic en este botón, se saldrá de la configuración y se descartarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="cebd5-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="cebd5-116">Algunas pantallas de configuración le preguntarán si desea salir y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cebd5-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="cebd5-117">Si selecciona **sí** , se cerrará la configuración actual y se cerrará la configuración actual y se volverá al generador de topología.</span><span class="sxs-lookup"><span data-stu-id="cebd5-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="cebd5-118">Si selecciona **no** , volverá al cuadro de diálogo configuración actual y le permitirá continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="cebd5-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="cebd5-119">**Ayuda**: al hacer clic en el botón **ayuda** se muestra esta información de ayuda asociada al cuadro de diálogo configuración actual.</span><span class="sxs-lookup"><span data-stu-id="cebd5-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


