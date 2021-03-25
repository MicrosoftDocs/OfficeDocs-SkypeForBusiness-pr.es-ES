---
title: Página de opción Instalar base de datos
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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Puede configurar opciones avanzadas para la ubicación de los archivos de base de datos y registro en su SQL Server. Las opciones disponibles son:'
ms.openlocfilehash: 392db6eb9b882ff66a9f15e1f5c4f0918cb140a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116078"
---
# <a name="install-database-options-page"></a><span data-ttu-id="7c9cd-104">Página de opción Instalar base de datos</span><span class="sxs-lookup"><span data-stu-id="7c9cd-104">Install Database Options Page</span></span>

<span data-ttu-id="7c9cd-105">Puede configurar opciones avanzadas para la ubicación de los archivos de base de datos y registro en su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="7c9cd-106">Las opciones disponibles son:</span><span class="sxs-lookup"><span data-stu-id="7c9cd-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c9cd-107">Seleccione la opción que mejor se adapte a sus requisitos y directivas relacionados con la ubicación de datos y archivos de registro en los SQL Server equipos.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="7c9cd-108">**Determinar automáticamente la** ubicación del archivo de base de datos: la opción predeterminada usa un algoritmo que determina el espacio disponible en el SQL Server y distribuye los archivos de registro y base de datos para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="7c9cd-109">**Usar SQL Server de instancia:** seleccione esta opción para colocar archivos de base de datos y archivos de registro en función de la configuración de la instancia en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="7c9cd-110">El administrador de la base de datos es quien administra y configura normalmente las opciones.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="7c9cd-111">**Us these path on target SQL Server:** Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c9cd-112">Las rutas de acceso que se introducen pueden modificarse según los algoritmos de optimización del rendimiento durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="7c9cd-113">Para obtener más información, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span><span class="sxs-lookup"><span data-stu-id="7c9cd-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="7c9cd-114">**Aceptar**: haga clic en el botón Aceptar para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="7c9cd-115">**Cancelar**: haga clic en Cancelar para descartar los cambios y volver a la pantalla de instalación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="7c9cd-116">**Ayuda**: haga clic en el botón Ayuda para obtener acceso a esta página de Ayuda.</span><span class="sxs-lookup"><span data-stu-id="7c9cd-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c9cd-117">Ver también</span><span class="sxs-lookup"><span data-stu-id="7c9cd-117">See also</span></span>

[<span data-ttu-id="7c9cd-118">Colocación del archivo de registro y los datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c9cd-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)