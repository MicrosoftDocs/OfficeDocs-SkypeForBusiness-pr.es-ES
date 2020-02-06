---
title: Preparar bosque actual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar el bosque de los servicios de dominio de Active Directory, debe extender correctamente el esquema, como se describe en el tema ejecución de la preparación del esquema y asegurarse de que el esquema se ha replicado.
ms.openlocfilehash: d13660eb703a793c1fc59ed422bd0b317986a86b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823534"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="5d0fe-103">Preparar bosque actual</span><span class="sxs-lookup"><span data-stu-id="5d0fe-103">Prepare Current Forest</span></span>

<span data-ttu-id="5d0fe-104">Para preparar el bosque de los servicios de dominio de Active Directory, debe extender correctamente el esquema, como se describe en el tema ejecución de la [preparación del esquema](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)y asegurarse de que el esquema se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="5d0fe-p101">Una vez completados los requisitos previos, puede empezar el **Paso 3: Preparar el bosque actual**. Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro del grupo Admins. del dominio en la raíz del bosque, o bien como miembro del grupo Administradores de organización del bosque que se prepara.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="5d0fe-107">En el Asistente para la implementación, en el **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="5d0fe-108">En la página **Preparar el bosque**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d0fe-109">La preparación del bosque le permite elegir dónde ubicar los grupos universales para Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="5d0fe-110">Elija una ubicación que respete los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="5d0fe-p103">En la página **Ejecución de comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**. Asegúrese de que no haya errores. Examine las advertencias para saber si son las previstas y son habituales en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="5d0fe-114">En la columna **acción** del registro, expanda **preparación del bosque**, busque un \*\* \<resultado\> \*\* de ejecución correcta al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="5d0fe-115">Espere a que se complete la replicación de servicios de dominio de Active Directory, o fuerce la replicación en todos los controladores de dominio que aparecen en el complemento **sitios y servicios de Active** Directory para el controlador de dominio raíz del bosque, antes de ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="5d0fe-116">Fuerce la replicación entre los controladores de dominio de todos los sitios de Active Directory para que la replicación dentro de los sitios se produzca en minutos.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="5d0fe-117">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo en el que se ejecutó el Asistente para la implementación, en el directorio usuarios del usuario de los servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="5d0fe-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="5d0fe-118">Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="5d0fe-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


