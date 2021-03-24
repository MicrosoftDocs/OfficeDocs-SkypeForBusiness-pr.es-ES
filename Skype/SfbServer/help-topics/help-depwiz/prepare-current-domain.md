---
title: Preparar dominio actual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server 2015 o Skype Empresarial Server, debe completar el paso 5: Preparar el dominio actual, tal como se describe en el tema Using Setup to Run Domain Preparation. Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: c9c33e466b7b0fcc7c2711603c284e5f419960a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096876"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="3312c-105">Preparar dominio actual</span><span class="sxs-lookup"><span data-stu-id="3312c-105">Prepare Current Domain</span></span>

<span data-ttu-id="3312c-106">Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server 2015 o Skype Empresarial Server, debe completar el paso **5: Preparar** dominio actual , tal como se describe en el tema [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span><span class="sxs-lookup"><span data-stu-id="3312c-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="3312c-107">Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de empresa del bosque al que pertenece el dominio.</span><span class="sxs-lookup"><span data-stu-id="3312c-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="3312c-108">Para preparar el dominio:</span><span class="sxs-lookup"><span data-stu-id="3312c-108">To prepare the domain:</span></span>

1. <span data-ttu-id="3312c-109">Desde la carpeta o medios de instalación de Skype Empresarial Server 2015, ejecute Setup.exe para iniciar el Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3312c-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="3312c-110">Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="3312c-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="3312c-111">En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3312c-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="3312c-112">En la página **Ejecutando comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="3312c-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="3312c-113">En la **columna** Acción, expanda **Preparación** del dominio , busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3312c-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="3312c-114">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación en el directorio Usuarios del usuario de Servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="3312c-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="3312c-115">Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="3312c-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>