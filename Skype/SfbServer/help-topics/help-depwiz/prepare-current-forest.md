---
title: Preparar bosque actual
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
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar el bosque de Servicios de dominio de Active Directory, debe extender correctamente el esquema, tal como se describe en el tema Running Schema Preparation, y asegurarse de que el esquema se haya replicado.
ms.openlocfilehash: 94d41a993b2fe976ef7ede885d277c00417ff7dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103466"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="4fa24-103">Preparar bosque actual</span><span class="sxs-lookup"><span data-stu-id="4fa24-103">Prepare Current Forest</span></span>

<span data-ttu-id="4fa24-104">Para preparar el bosque de Servicios de dominio de Active Directory, debe extender correctamente el esquema, tal como se describe en el tema [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), y asegurarse de que el esquema se haya replicado.</span><span class="sxs-lookup"><span data-stu-id="4fa24-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="4fa24-105">Después de completar estos requisitos previos, puede comenzar **el paso 3: Preparar el bosque actual**.</span><span class="sxs-lookup"><span data-stu-id="4fa24-105">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**.</span></span> <span data-ttu-id="4fa24-106">Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro de administradores de dominio en la raíz del bosque o como miembro de los administradores de empresa para el bosque que está preparando.</span><span class="sxs-lookup"><span data-stu-id="4fa24-106">To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="4fa24-107">En el Asistente para implementación **del paso 3: Preparar el bosque actual,** haga clic **en Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4fa24-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="4fa24-108">En la página **Preparar bosque,** haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4fa24-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fa24-109">La preparación del bosque permite elegir dónde colocar los grupos universales para Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4fa24-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="4fa24-110">Elija una ubicación que respete los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4fa24-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="4fa24-111">En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="4fa24-111">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span> <span data-ttu-id="4fa24-112">Asegúrese de que no hay errores.</span><span class="sxs-lookup"><span data-stu-id="4fa24-112">Make sure that there are no errors.</span></span> <span data-ttu-id="4fa24-113">Revise las advertencias para determinar si se esperan y son típicas para la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="4fa24-113">Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="4fa24-114">En  la columna Acción del registro, expanda Forest **Prep**, busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4fa24-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="4fa24-115">Espere a que se complete la replicación de Servicios de dominio de Active Directory o forzar la replicación a todos los controladores de dominio enumerados en el complemento Sitios y servicios de **Active Directory** para el controlador de dominio raíz del bosque, antes de ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="4fa24-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="4fa24-116">Fuerce la replicación entre los controladores de dominio en todos los sitios de Active Directory para que la replicación en los sitios se produzca en cuestión de minutos.</span><span class="sxs-lookup"><span data-stu-id="4fa24-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="4fa24-117">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación, en el directorio Usuarios del usuario de Servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="4fa24-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="4fa24-118">Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="4fa24-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>