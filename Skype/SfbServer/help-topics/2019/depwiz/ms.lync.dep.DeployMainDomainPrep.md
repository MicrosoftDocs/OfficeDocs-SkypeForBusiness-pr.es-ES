---
title: Preparar dominio actual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar un dominio de modo que aloje servidores que ejecuten Skype empresarial Server o usuarios de Skype empresarial Server, debe completar el paso 5: preparar el dominio actual, como se describe en el tema usar el programa de instalación para ejecutar la preparación del dominio. Para completar este paso, debe haber iniciado sesión como miembro del grupo de administradores del dominio en el dominio que está preparando o como miembro del grupo administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: 16b47a211ebff577844cdc29b6e28acd00952d20
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303436"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="4a529-105">Preparar dominio actual</span><span class="sxs-lookup"><span data-stu-id="4a529-105">Prepare Current Domain</span></span>

<span data-ttu-id="4a529-106">Para preparar un dominio de modo que aloje servidores que ejecuten Skype empresarial Server o usuarios de Skype empresarial Server, debe completar el **paso 5: preparar el dominio actual**, como se describe en el tema [usar el programa de instalación para ejecutar la preparación del dominio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a529-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="4a529-107">Para completar este paso, debe haber iniciado sesión como miembro del grupo de administradores del dominio en el dominio que está preparando o como miembro del grupo administradores de empresa del bosque al que pertenece el dominio.</span><span class="sxs-lookup"><span data-stu-id="4a529-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="4a529-108">Para preparar el dominio:</span><span class="sxs-lookup"><span data-stu-id="4a529-108">To prepare the domain:</span></span>

1. <span data-ttu-id="4a529-109">Desde la carpeta o los elementos multimedia de la instalación de Skype empresarial Server, ejecute setup. exe para iniciar el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4a529-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="4a529-110">Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="4a529-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="4a529-111">En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4a529-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="4a529-112">En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="4a529-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="4a529-113">En la columna **acción** , expanda **preparar el dominio**, busque un \*\* \<\> \*\* resultado de ejecución correcta al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4a529-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="4a529-114">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación en el directorio de usuarios del usuario de los servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="4a529-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="4a529-115">Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="4a529-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


