---
title: Preparar un servidor único de Standard Edition (invocar)
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
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: En la página Ejecutar comandos, las tareas de instalación de SQL Server Express y configuración para que actúen como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia SQL Server base de datos basada en rtc. También se crean reglas de firewall para que los servidores y clientes tengan acceso de entrada y salida con el fin de comunicarse con la base de datos y la instancia. Cuando la tarea está finalizada, se puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina Equipo local de arranque. Después de seleccionar el archivo de registro, haga clic en Ver registro. Compruebe si el archivo de registro contiene errores y advertencias. Cuando desee continuar, haga clic en Finalizar. Ahora debe definir la topología con el Generador de topologías si aún no lo ha hecho.
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829750"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="1e353-111">Preparar un servidor único de Standard Edition (invocar)</span><span class="sxs-lookup"><span data-stu-id="1e353-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="1e353-112">En la **página Ejecutar** comandos, las tareas de instalación de SQL Server Express y configuración para que actúen como almacén de administración central se pueden ver en el panel de tareas.</span><span class="sxs-lookup"><span data-stu-id="1e353-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="1e353-113">De forma predeterminada, se crea una instancia SQL Server base de datos basada en rtc.</span><span class="sxs-lookup"><span data-stu-id="1e353-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="1e353-114">También se crean reglas de firewall para que los servidores y clientes tengan acceso de entrada y salida con el fin de comunicarse con la base de datos y la instancia.</span><span class="sxs-lookup"><span data-stu-id="1e353-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="1e353-115">Cuando la tarea está finalizada, se puede seleccionar el archivo de registro en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e353-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="1e353-116">El archivo de registro se denomina **Equipo local de arranque**.</span><span class="sxs-lookup"><span data-stu-id="1e353-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="1e353-117">Después de seleccionar el archivo de registro, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="1e353-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="1e353-118">Compruebe si el archivo de registro contiene errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="1e353-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="1e353-119">Cuando desee continuar, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1e353-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="1e353-120">Ahora debe definir la topología con el Generador de topologías si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="1e353-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e353-121">La instalación de SQL Server Express puede tardar algún tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="1e353-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="1e353-122">Durante el proceso de instalación no aparece ninguna información sobre el progreso en la pantalla ni el panel de tareas.</span><span class="sxs-lookup"><span data-stu-id="1e353-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="1e353-123">Para supervisar la instalación, debes usar el Administrador de tareas de Windows y buscar los procesos MSIExec y los archivos de instalación para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1e353-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="1e353-124">De esta forma, puede comprobar el estado de la instalación y saber si el proceso continúa o no.</span><span class="sxs-lookup"><span data-stu-id="1e353-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="1e353-125">Según los factores que no se den en este tema de ayuda, la instalación de la instancia de SQL Server puede tardar hasta 15 minutos o más en completarse.</span><span class="sxs-lookup"><span data-stu-id="1e353-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

