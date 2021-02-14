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
description: 'Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server 2015 o Skype Empresarial Server, debe completar el paso 5: Preparar el dominio actual, como se describe en el tema Using Setup to Run Domain Preparation. Para completar el paso, debe iniciar sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de organización del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804970"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="478fe-105">Preparar dominio actual</span><span class="sxs-lookup"><span data-stu-id="478fe-105">Prepare Current Domain</span></span>

<span data-ttu-id="478fe-106">Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server 2015 o Skype Empresarial Server, debe completar el paso **5:** Preparar el dominio actual, tal como se describe en el tema Using [Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="478fe-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="478fe-107">Para completar el paso, debe iniciar sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de organización del bosque al que pertenece el dominio.</span><span class="sxs-lookup"><span data-stu-id="478fe-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="478fe-108">Para preparar el dominio:</span><span class="sxs-lookup"><span data-stu-id="478fe-108">To prepare the domain:</span></span>

1. <span data-ttu-id="478fe-109">Desde la carpeta o los medios de instalación de Skype Empresarial Server 2015, ejecute Setup.exe para iniciar el Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="478fe-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="478fe-110">Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="478fe-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="478fe-111">En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="478fe-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="478fe-112">En la página **Ejecutando comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="478fe-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="478fe-113">En la **columna** Acción, expanda Preparación del dominio **,** busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="478fe-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="478fe-114">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación en el directorio de usuarios del usuario de Servicios de dominio de Active Directory que realizó el paso.</span><span class="sxs-lookup"><span data-stu-id="478fe-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="478fe-115">Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="478fe-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


