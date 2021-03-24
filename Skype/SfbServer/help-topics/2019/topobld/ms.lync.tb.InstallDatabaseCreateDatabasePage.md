---
title: Instalar y crear bases de datos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y se implementarán y configurarán automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.
ms.openlocfilehash: 160b42e510fc54b3f03375a0c86bc9f6bdf83f5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100056"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="a5444-104">Instalar y crear bases de datos</span><span class="sxs-lookup"><span data-stu-id="a5444-104">Install and Create Databases</span></span>

<span data-ttu-id="a5444-105">Seleccione las bases de datos que desee crear para la implementación.</span><span class="sxs-lookup"><span data-stu-id="a5444-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="a5444-106">De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y se implementarán y configurarán automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a5444-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="a5444-p103">**Seleccione las bases de datos que desee crear**: seleccione la casilla de verificación de todas las bases de datos que tiene la intención de implementar y configurar. Seleccione la casilla de verificación de todas las bases de datos que desee implementar.</span><span class="sxs-lookup"><span data-stu-id="a5444-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="a5444-109">El SQL Server debe haber sido configurado para la instancia (si existe) y los puertos de firewall deben abrirse para dar cabida a la instancia en la que se implementan las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a5444-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="a5444-110">Para obtener más información, vea [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span><span class="sxs-lookup"><span data-stu-id="a5444-110">For details, see [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span></span>

 <span data-ttu-id="a5444-111">**Avanzado:** haga clic en el SQL Server y haga clic en el **botón** Opciones avanzadas para elegir opciones para las ubicaciones de archivos de base de datos en su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5444-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="a5444-112">Para más información sobre la ubicación avanzada del archivo de la base de datos, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span><span class="sxs-lookup"><span data-stu-id="a5444-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span></span>

 <span data-ttu-id="a5444-113">**Atrás**: al hacer clic en este botón el usuario vuelve a la pantalla anterior (puede que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="a5444-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="a5444-114">**Siguiente**: al hacer clic en este botón se confirma la selección del cuadro de diálogo actual y se abre el siguiente cuadro de diálogo que permite configurar la información adicional</span><span class="sxs-lookup"><span data-stu-id="a5444-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="a5444-115">**Cancelar**: al hacer clic en este botón se sale de la configuración y se descartan los cambios.</span><span class="sxs-lookup"><span data-stu-id="a5444-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="a5444-116">Algunas pantallas de configuración, aunque no todas, le pedirán si desea salir y descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a5444-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="a5444-117">Si selecciona **Sí,** se cerrará la configuración actual, se cerrará la configuración actual y se devolverá al Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a5444-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="a5444-118">Si selecciona **No** el usuario volverá al cuadro de diálogo de configuración actual desde el que podrá continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="a5444-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="a5444-119">**Ayuda**: al hacer clic en el botón **Ayuda** aparece esta información de ayuda relacionada con el cuadro de diálogo de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="a5444-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>