---
title: Instalar y crear bases de datos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido e implementará y configurará automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.
ms.openlocfilehash: 36912e468b0618925b3fbeb20db829d8d19249fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806940"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="2a9f1-104">Instalar y crear bases de datos</span><span class="sxs-lookup"><span data-stu-id="2a9f1-104">Install and Create Databases</span></span>

<span data-ttu-id="2a9f1-105">Seleccione las bases de datos que desee crear para la implementación.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="2a9f1-106">De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido e implementará y configurará automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="2a9f1-p103">**Seleccione las bases de datos que desee crear**: seleccione la casilla de verificación de todas las bases de datos que tiene la intención de implementar y configurar. Seleccione la casilla de verificación de todas las bases de datos que desee implementar.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="2a9f1-109">El SQL Server ya debe estar configurado para la instancia (si lo hay) y los puertos de firewall deben estar abiertos para dar cabida a la instancia en la que está implementando las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="2a9f1-110">Para más información, consulte [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a9f1-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="2a9f1-111">**Avanzado:** haga clic en el  SQL Server y haga clic en el botón Avanzadas para elegir las opciones de las ubicaciones de archivos de base de datos en su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="2a9f1-112">Para más información sobre la ubicación avanzada del archivo de la base de datos, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a9f1-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="2a9f1-113">**Atrás**: al hacer clic en este botón el usuario vuelve a la pantalla anterior (puede que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="2a9f1-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="2a9f1-114">**Siguiente**: al hacer clic en este botón se confirma la selección del cuadro de diálogo actual y se abre el siguiente cuadro de diálogo que permite configurar la información adicional</span><span class="sxs-lookup"><span data-stu-id="2a9f1-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="2a9f1-115">**Cancelar**: al hacer clic en este botón se sale de la configuración y se descartan los cambios.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="2a9f1-116">Algunas pantallas de configuración, aunque no todas, le pedirán si desea salir y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="2a9f1-117">Si selecciona **Sí,** se cerrará la configuración actual, se cerrará la configuración actual y se volverá al Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="2a9f1-118">Si selecciona **No** el usuario volverá al cuadro de diálogo de configuración actual desde el que podrá continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="2a9f1-119">**Ayuda**: al hacer clic en el botón **Ayuda** aparece esta información de ayuda relacionada con el cuadro de diálogo de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="2a9f1-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


