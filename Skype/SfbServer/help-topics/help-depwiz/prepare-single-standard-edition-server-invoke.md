---
title: Preparar un servidor único de Standard Edition (invocar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: En la página comandos en ejecución, las tareas de instalación de SQL Server Express y la configuración para actuar como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server llamada RTC. También se crean reglas de Firewall para permitir el acceso entrante y saliente a los servidores y clientes para que se comuniquen con la base de datos y la instancia. Una vez completada la tarea, puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina bootstrap local Machine. Después de seleccionar el archivo de registro, haga clic en Ver registro. Revise el archivo de registro en busca de errores y advertencias. Cuando esté listo para continuar, haga clic en finalizar. Ahora debe definir su topología con Topology Builder si todavía no lo ha hecho.
ms.openlocfilehash: 16cc6ada75ae90da4da2cb269aed26adbf472a33
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823444"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="25035-111">Preparar un servidor único de Standard Edition (invocar)</span><span class="sxs-lookup"><span data-stu-id="25035-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="25035-112">En la página **comandos en ejecución** , las tareas de instalación de SQL Server Express y la configuración para actuar como almacén de administración central se pueden ver en el panel de tareas.</span><span class="sxs-lookup"><span data-stu-id="25035-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="25035-113">De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server llamada RTC.</span><span class="sxs-lookup"><span data-stu-id="25035-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="25035-114">También se crean reglas de Firewall para permitir el acceso entrante y saliente a los servidores y clientes para que se comuniquen con la base de datos y la instancia.</span><span class="sxs-lookup"><span data-stu-id="25035-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="25035-115">Una vez completada la tarea, puede seleccionar el archivo de registro en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="25035-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="25035-116">El archivo de registro se denomina **bootstrap local Machine**.</span><span class="sxs-lookup"><span data-stu-id="25035-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="25035-117">Después de seleccionar el archivo de registro, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="25035-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="25035-118">Revise el archivo de registro en busca de errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="25035-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="25035-119">Cuando esté listo para continuar, haga clic en **Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="25035-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="25035-120">Ahora debe definir su topología con Topology Builder si todavía no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="25035-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="25035-121">La instalación de SQL Server Express puede tardar algún tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="25035-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="25035-122">Durante la instalación, no se muestra ningún progreso en la pantalla o en el panel de tareas.</span><span class="sxs-lookup"><span data-stu-id="25035-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="25035-123">Para supervisar la instalación, debe usar el administrador de tareas de Windows y buscar los procesos de MSIExec y los archivos de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25035-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="25035-124">De esta manera, puede ver el estado de la instalación y asegurarse de que la instalación se está realizando.</span><span class="sxs-lookup"><span data-stu-id="25035-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="25035-125">En función de los factores ajenos al ámbito de este tema de ayuda, puede demorar hasta 15 minutos o más para que se complete la instalación de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25035-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

