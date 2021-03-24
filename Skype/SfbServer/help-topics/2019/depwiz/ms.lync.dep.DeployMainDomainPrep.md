---
title: Preparar dominio actual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar un dominio para hospedar servidores que ejecutan usuarios de Skype Empresarial Server o Skype Empresarial Server, debe completar el paso 5: Preparar el dominio actual, tal como se describe en el tema Using Setup to Run Domain Preparation. Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097346"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="94ba6-105">Preparar dominio actual</span><span class="sxs-lookup"><span data-stu-id="94ba6-105">Prepare Current Domain</span></span>

<span data-ttu-id="94ba6-106">Para preparar un dominio para hospedar servidores que ejecutan usuarios de Skype Empresarial Server o Skype Empresarial Server, debe completar el paso **5: Preparar** dominio actual , tal como se describe en el tema [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span><span class="sxs-lookup"><span data-stu-id="94ba6-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="94ba6-107">Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de empresa del bosque al que pertenece el dominio.</span><span class="sxs-lookup"><span data-stu-id="94ba6-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="94ba6-108">Para preparar el dominio:</span><span class="sxs-lookup"><span data-stu-id="94ba6-108">To prepare the domain:</span></span>

1. <span data-ttu-id="94ba6-109">Desde la carpeta o medios de instalación de Skype Empresarial Server, ejecute Setup.exe para iniciar el Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="94ba6-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="94ba6-110">Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="94ba6-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="94ba6-111">En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="94ba6-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="94ba6-112">En la página **Ejecutando comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="94ba6-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="94ba6-113">En la **columna** Acción, expanda **Preparación** del dominio , busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="94ba6-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="94ba6-114">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación en el directorio Usuarios del usuario de Servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="94ba6-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="94ba6-115">Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="94ba6-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>