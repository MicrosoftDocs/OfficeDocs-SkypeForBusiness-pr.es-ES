---
title: Preparar bosque actual
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar el bosque de servicios de dominio de Active Directory, correctamente debe extender el esquema, como se describe en el tema preparación del esquema de ejecución y asegúrese de que el esquema se ha replicado.
ms.openlocfilehash: 80218036b6eaee5abb0156ca6a13678f9b9f2238
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-current-forest"></a><span data-ttu-id="4bead-103">Preparar bosque actual</span><span class="sxs-lookup"><span data-stu-id="4bead-103">Prepare Current Forest</span></span>
 
<span data-ttu-id="4bead-104">Para preparar el bosque de servicios de dominio de Active Directory, correctamente debe extender el esquema, como se describe en el tema [Preparación del esquema de ejecución](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)y asegúrese de que el esquema se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="4bead-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>
  
<span data-ttu-id="4bead-p101">Una vez completados los requisitos previos, puede empezar el **Paso 3: Preparar el bosque actual**. Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro del grupo Admins. del dominio en la raíz del bosque, o bien como miembro del grupo Administradores de organización del bosque que se prepara.</span><span class="sxs-lookup"><span data-stu-id="4bead-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>
  
1. <span data-ttu-id="4bead-107">En el Asistente para la implementación, en el **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4bead-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>
    
2. <span data-ttu-id="4bead-108">En la página **Preparar el bosque**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4bead-108">From the **Prepare Forest** page, click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4bead-109">Preparación del bosque permite elegir dónde desea colocar los grupos universales para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4bead-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="4bead-110">Elija una ubicación que respete los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4bead-110">Choose a location that is consistent with the requirements of your organization.</span></span> 
  
3. <span data-ttu-id="4bead-p103">En la página **Ejecución de comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**. Asegúrese de que no haya errores. Examine las advertencias para saber si son las previstas y son habituales en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="4bead-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>
    
4. <span data-ttu-id="4bead-114">En la columna en el registro de **acción** , expanda **Preparar el bosque**, busque un ** \<éxito\> ** resultado de ejecución al final de cada tarea para comprobar que finalizó correctamente la preparación del bosque, cierre el registro y, a continuación, haga clic en **Finalizar **.</span><span class="sxs-lookup"><span data-stu-id="4bead-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>
    
5. <span data-ttu-id="4bead-115">Espere a completar la replicación de los servicios de dominio de Active Directory o fuerce la replicación en todos los controladores de dominio enumerados en el complemento **servicios y sitios de Active Directory** para el controlador de dominio raíz de bosque, antes de ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="4bead-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="4bead-116">Forzar la replicación entre los controladores de dominio en todos los sitios de Active Directory para hacer que la replicación dentro de los sitios que se produzcan en minutos.</span><span class="sxs-lookup"><span data-stu-id="4bead-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="4bead-117">Si necesita revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrarlas en el equipo donde se ejecuta el Asistente de implementación, en el directorio de usuarios de usuario de servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="4bead-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="4bead-118">Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="4bead-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

