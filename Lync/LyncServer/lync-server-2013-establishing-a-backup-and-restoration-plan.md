---
title: 'Lync Server 2013: establecer un plan de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbe142d697fc3d95772fb2d4ca758b8550054a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="08e2f-102">Establecimiento de un plan de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08e2f-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08e2f-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="08e2f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="08e2f-104">Para crear un plan de copia de seguridad y restauración deberá seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="08e2f-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="08e2f-105">Desarrollar el plan.</span><span class="sxs-lookup"><span data-stu-id="08e2f-105">Developing the plan.</span></span>

  - <span data-ttu-id="08e2f-106">Implementar el plan.</span><span class="sxs-lookup"><span data-stu-id="08e2f-106">Implementing the plan.</span></span>

  - <span data-ttu-id="08e2f-107">Mantenimiento del plan.</span><span class="sxs-lookup"><span data-stu-id="08e2f-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="08e2f-108">Desarrollar un plan de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="08e2f-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="08e2f-109">Después de desarrollar su estrategia de copia de seguridad y restauración para Lync Server, Úsela para documentar un plan de copia de seguridad y restauración detallado.</span><span class="sxs-lookup"><span data-stu-id="08e2f-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="08e2f-110">Su plan debe explicar en detalle las prioridades y requisitos para hacer copias de seguridad de datos y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="08e2f-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="08e2f-111">Puede usar la información contenida en [establecer una estrategia de copia de seguridad y restauración para Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) y las hojas de [cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar la documentación de su estrategia.</span><span class="sxs-lookup"><span data-stu-id="08e2f-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="08e2f-112">Su plan deberá incluir también criterios para decidir cuándo y cómo restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="08e2f-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="08e2f-113">A medida que desarrolla el plan, debe tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08e2f-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="08e2f-114">Cómo se recuperarán los servidores en nuevo hardware.</span><span class="sxs-lookup"><span data-stu-id="08e2f-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="08e2f-115">Cómo se recuperarán los servicios que requieran acciones por parte de varios departamentos o áreas de negocio.</span><span class="sxs-lookup"><span data-stu-id="08e2f-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="08e2f-116">Cómo adquirir servidores de repuesto rápidamente.</span><span class="sxs-lookup"><span data-stu-id="08e2f-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="08e2f-117">El tiempo que se tarda en completar la recuperación utilizando su estrategia.</span><span class="sxs-lookup"><span data-stu-id="08e2f-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="08e2f-118">Considere los requisitos de la organización para el objetivo de tiempo de recuperación (RTO).</span><span class="sxs-lookup"><span data-stu-id="08e2f-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="08e2f-119">Modifique los procedimientos de copia de seguridad y restauración en este tema, agregando y eliminando procedimientos según corresponda, para reflejar los servidores y los componentes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="08e2f-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="08e2f-120">También puede Agregar los detalles apropiados, como la programación de copia de seguridad, a los procedimientos apropiados para asegurarse de que la información no se ha desactivado.</span><span class="sxs-lookup"><span data-stu-id="08e2f-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08e2f-121">Se recomienda crear scripts para tantos pasos como sea posible, para ayudar a garantizar la calidad y la reproducibilidad de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="08e2f-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="08e2f-122">En su plan, especifique quién es responsable de revisar el plan, quién es responsable de probar y validar los nuevos procedimientos o herramientas, y quién debe aprobar los cambios en el plan y los procedimientos relacionados.</span><span class="sxs-lookup"><span data-stu-id="08e2f-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="08e2f-123">Para asegurarse de que el plan de copia de seguridad y restauración cumple completamente todos los objetivos y las prioridades establecidos, obtenga la aprobación de los responsables de la toma de decisiones empresariales y los responsables de las decisiones técnicas de su organización antes de implementar el plan.</span><span class="sxs-lookup"><span data-stu-id="08e2f-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="08e2f-124">Implementar el plan de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="08e2f-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="08e2f-125">Para implementar un plan de copia de seguridad y restauración es necesario seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="08e2f-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="08e2f-126">Probar y validar el plan.</span><span class="sxs-lookup"><span data-stu-id="08e2f-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="08e2f-127">Comunicar el plan.</span><span class="sxs-lookup"><span data-stu-id="08e2f-127">Communicating the plan.</span></span>

  - <span data-ttu-id="08e2f-128">Validar las operaciones de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="08e2f-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="08e2f-129">Probar y validar el plan</span><span class="sxs-lookup"><span data-stu-id="08e2f-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="08e2f-130">Los procedimientos descritos aquí se han probado y validado en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="08e2f-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="08e2f-131">Para asegurarse de que estos u otros procedimientos funcionan en su entorno, debe probar y validar cada procedimiento que pretenda implementar.</span><span class="sxs-lookup"><span data-stu-id="08e2f-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="08e2f-132">Complete las pruebas y la validación antes de enviar el plan para la aprobación final.</span><span class="sxs-lookup"><span data-stu-id="08e2f-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="08e2f-133">Comunicar el plan</span><span class="sxs-lookup"><span data-stu-id="08e2f-133">Communicating the Plan</span></span>

<span data-ttu-id="08e2f-134">Su plan de copia de seguridad y restauración debe describir claramente quién implementa los procedimientos e incluir instrucciones paso por paso para llevar a cabo dichos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="08e2f-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="08e2f-135">Debe asegurarse de que todos los responsables de cualquier aspecto de la copia de seguridad y restauración comprenden el plan, cómo se va a implementar y cuál es su rol.</span><span class="sxs-lookup"><span data-stu-id="08e2f-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="08e2f-136">Tenga en cuenta todos los requisitos de implementación para los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="08e2f-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="08e2f-137">Copia de seguridad del grupo y del servidor.</span><span class="sxs-lookup"><span data-stu-id="08e2f-137">Pool and server backup.</span></span>

  - <span data-ttu-id="08e2f-138">Restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="08e2f-138">Restoration of service.</span></span>

<span data-ttu-id="08e2f-139">**Copias de seguridad de servidores y grupos de servidores**</span><span class="sxs-lookup"><span data-stu-id="08e2f-139">**Pool and server backup**</span></span>

<span data-ttu-id="08e2f-p106">El plan de copia de seguridad y restauración debe incluir toda la información necesaria para completar los procedimientos de copia de seguridad de forma continuada. Deberá comunicar a los miembros del equipo responsable una serie de informaciones básicas, entre ellas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="08e2f-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="08e2f-142">Equipo o persona (especificado como una persona o rol) responsable de realizar la copia de seguridad de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="08e2f-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="08e2f-143">Programaciones específicas para hacer copias de seguridad de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="08e2f-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="08e2f-144">Ubicaciones de copia de seguridad para cada tipo de datos (configuración, base de datos y recursos compartidos de archivos).</span><span class="sxs-lookup"><span data-stu-id="08e2f-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="08e2f-145">Procedimientos de copia de seguridad que se van a usar, incluidas las herramientas necesarias para completar cada procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08e2f-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="08e2f-146">Información necesaria para completar las copias de seguridad, tal como se describe en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="08e2f-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="08e2f-147">Métodos de validación que se usan para ayudar a garantizar que se realicen copias de seguridad de los datos y la configuración correctamente y que estén disponibles para la restauración, lo que puede incluir auditorías periódicas y restauraciones de prueba.</span><span class="sxs-lookup"><span data-stu-id="08e2f-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="08e2f-148">**Restauración de servicio**</span><span class="sxs-lookup"><span data-stu-id="08e2f-148">**Restoration of service**</span></span>

<span data-ttu-id="08e2f-149">El plan de copia de seguridad y restauración debe incluir toda la información necesaria para restaurar el servicio, en caso de que uno o varios servidores experimenten una pérdida que permita que el servicio no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="08e2f-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="08e2f-150">Deberá comunicar a los miembros del equipo responsable una serie de informaciones básicas, entre ellas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="08e2f-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="08e2f-151">Equipo o persona (especificados como persona individual o rol) responsable de determinar cuándo se necesita restaurar el servicio, así como los procedimientos que se utilizarán para restaurarlo y el equipo o persona responsable de implementar los procedimientos para cada escenario de restauración.</span><span class="sxs-lookup"><span data-stu-id="08e2f-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="08e2f-152">Criterios para determinar qué procedimientos de restauración son los más apropiados para una situación concreta.</span><span class="sxs-lookup"><span data-stu-id="08e2f-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="08e2f-153">Tiempo estimado para la restauración del servicio y el objetivo de tiempo de recuperación (RTO) en cada escenario de restauración.</span><span class="sxs-lookup"><span data-stu-id="08e2f-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="08e2f-154">Procedimientos de restauración que se utilizarán, incluyendo las herramientas necesarias para completar cada procedimiento</span><span class="sxs-lookup"><span data-stu-id="08e2f-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="08e2f-155">Información necesaria para restaurar los datos y la configuración.</span><span class="sxs-lookup"><span data-stu-id="08e2f-155">Information required to restore data and settings.</span></span> <span data-ttu-id="08e2f-156">Las hojas de cálculo se proporcionan en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="08e2f-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="08e2f-157">Validar operaciones de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="08e2f-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="08e2f-158">Tras completar las tareas iniciales de copia de seguridad en su entorno de producción y a intervalos especificados (conforme a su plan de copia de seguridad y restauración), deberá verificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08e2f-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="08e2f-159">Las copias de seguridad se están haciendo según lo requerido.</span><span class="sxs-lookup"><span data-stu-id="08e2f-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="08e2f-160">Se puede tener acceso a los datos y la configuración de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="08e2f-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="08e2f-161">Los procedimientos de restauración pueden realizarse dentro de las horas de objetivo de tiempo de recuperación (RTO) especificadas en el plan de copia de seguridad y restauración, y los resultados cumplen todos los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="08e2f-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="08e2f-162">Las copias de seguridad de las hojas se han completado, verificado y almacenado en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="08e2f-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="08e2f-163">Estas hojas de cálculo se proporcionan en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="08e2f-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="08e2f-164">Los procedimientos de restauración se han probado y se ha verificado que funciona según lo esperado y conforme al plan de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="08e2f-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="08e2f-165">Mantener el plan de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="08e2f-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="08e2f-166">Una topología de Lync Server es un entorno dinámico que cambia con la organización.</span><span class="sxs-lookup"><span data-stu-id="08e2f-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="08e2f-167">Reevalúe el plan de copia de seguridad y restauración a medida que su organización cambie y revise periódicamente para asegurarse de que sigue cumpliendo las necesidades de su empresa.</span><span class="sxs-lookup"><span data-stu-id="08e2f-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

