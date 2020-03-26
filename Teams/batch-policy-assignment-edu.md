---
title: Asignar directivas a grandes conjuntos de usuarios de la escuela
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar la asignación de directivas por lotes para asignar directivas a grandes conjuntos de usuarios de su centro educativo en masa para fines escolares (teleschool, tele-School).
f1keywords: ''
ms.openlocfilehash: 7e297b6a4b99162fb50564d4f552a06f0dc41a10
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978522"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="3b7be-103">Asignar directivas a grandes conjuntos de usuarios de la escuela</span><span class="sxs-lookup"><span data-stu-id="3b7be-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="3b7be-104">¿Necesita dar acceso a las diferentes características de Microsoft Teams a sus alumnos y educadores?</span><span class="sxs-lookup"><span data-stu-id="3b7be-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="3b7be-105">Puede identificar rápidamente los usuarios de su organización por tipo de licencia y, a continuación, asignarles la Directiva adecuada.</span><span class="sxs-lookup"><span data-stu-id="3b7be-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="3b7be-106">En este tutorial se muestra cómo usar la [asignación de directivas por lotes](assign-policies.md#assign-a-policy-to-a-batch-of-users) para asignar una directiva de reunión a los usuarios de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="3b7be-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="3b7be-107">Recuerde que en Teams, los usuarios obtienen automáticamente la directiva global (opción predeterminada para toda la organización) para un tipo de directiva de Teams, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="3b7be-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="3b7be-108">Como la población de alumnos suele ser el mayor conjunto de usuarios y a menudo reciben la configuración más restrictiva, le recomendamos que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b7be-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="3b7be-109">Edite y aplique la directiva global (valor predeterminado de la organización) para restringir las capacidades de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="3b7be-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="3b7be-110">Crear una directiva personalizada que permita capacidades básicas, como la programación privada de chats y reuniones, y la asignación de la Directiva a su personal y educadores.</span><span class="sxs-lookup"><span data-stu-id="3b7be-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="3b7be-111">Tenga en cuenta que la directiva global se aplicará a todos los usuarios de su escuela hasta que cree una directiva personalizada y la asigne a su personal y educadores.</span><span class="sxs-lookup"><span data-stu-id="3b7be-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="3b7be-112">En este tutorial, los alumnos obtendrán la Directiva de reunión global y usamos PowerShell para asignar una directiva de reuniones personalizada denominada EducatorMeetingPolicy al personal y los educadores en bloque.</span><span class="sxs-lookup"><span data-stu-id="3b7be-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="3b7be-113">Damos por hecho que ha modificado la directiva global para personalizar la configuración de la reunión de los alumnos y creado una directiva personalizada que define la experiencia de la reunión para el personal y los educadores.</span><span class="sxs-lookup"><span data-stu-id="3b7be-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Captura de pantalla de la página directivas de la reunión en el centro de administración de Teams](media/edu-batch-policy-assignment.png)

<span data-ttu-id="3b7be-115">Siga estos pasos para asignar una directiva de reunión personalizada al personal y educadores de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="3b7be-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="3b7be-116">Conectarse al módulo de Azure AD PowerShell para Graph y al módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="3b7be-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="3b7be-117">Antes de realizar los pasos de este artículo, tendrá que instalar y conectarse con el módulo Azure AD PowerShell for Graph (para identificar a los usuarios por sus licencias asignadas) y el módulo Microsoft Teams PowerShell (para asignar las directivas a esos usuarios).</span><span class="sxs-lookup"><span data-stu-id="3b7be-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="3b7be-118">Instalar y conectarse al módulo de Azure AD PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="3b7be-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="3b7be-119">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador) y, a continuación, ejecute lo siguiente para instalar el módulo Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="3b7be-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="3b7be-120">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3b7be-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="3b7be-121">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="3b7be-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="3b7be-122">Para obtener más información, vea [conectarse con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="3b7be-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3b7be-123">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b7be-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3b7be-124">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="3b7be-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="3b7be-125">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3b7be-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="3b7be-126">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="3b7be-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="3b7be-127">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3b7be-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="3b7be-128">Identificar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="3b7be-128">Identify your users</span></span>

<span data-ttu-id="3b7be-129">En primer lugar, ejecute lo siguiente para identificar a su personal y educadores por tipo de licencia.</span><span class="sxs-lookup"><span data-stu-id="3b7be-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="3b7be-130">Esto le indica qué SKU están en uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="3b7be-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="3b7be-131">A continuación, puede identificar el personal y los formadores que tienen una SKU de profesores asignados.</span><span class="sxs-lookup"><span data-stu-id="3b7be-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="3b7be-132">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="3b7be-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="3b7be-133">En este ejemplo, la salida muestra que el SkuId de la licencia del profesorado es "e97c048c-37a4-45FB-AB50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="3b7be-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="3b7be-134">Para ver una lista de SKU de educación e identificadores de SKU, consulte [educación SKU SKU](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="3b7be-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="3b7be-135">A continuación, ejecutamos lo siguiente para identificar los usuarios que tienen esta licencia y recopilar todas ellas.</span><span class="sxs-lookup"><span data-stu-id="3b7be-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="3b7be-136">Asignar una directiva en masa</span><span class="sxs-lookup"><span data-stu-id="3b7be-136">Assign a policy in bulk</span></span>

<span data-ttu-id="3b7be-137">Ahora, asignamos las directivas apropiadas a usuarios de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="3b7be-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="3b7be-138">La cantidad máxima de usuarios para los que puede asignar o actualizar directivas es 20.000 a la vez.</span><span class="sxs-lookup"><span data-stu-id="3b7be-138">The maximum number of users for which you can assign or update policies is 20,000 at a time.</span></span> <span data-ttu-id="3b7be-139">Por ejemplo, si tiene más de 20.000 de personal y educadores, tendrá que enviar varios lotes.</span><span class="sxs-lookup"><span data-stu-id="3b7be-139">For example, if you have more than 20,000 staff and educators, you'll need to submit multiple batches.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b7be-140">Actualmente recomendamos que asigne directivas en lotes de usuarios de 5.000 a la vez.</span><span class="sxs-lookup"><span data-stu-id="3b7be-140">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="3b7be-141">Durante estas horas de demanda aumentada, puede experimentar retrasos en los tiempos de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3b7be-141">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="3b7be-142">Para minimizar el impacto de estos aumentos en los tiempos de procesamiento, le sugerimos que envíe tamaños de lotes más pequeños de hasta 5.000 usuarios y que envíe cada lote solo después de que se haya completado el anterior.</span><span class="sxs-lookup"><span data-stu-id="3b7be-142">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="3b7be-143">El envío de lotes fuera del horario laboral normal también puede ayudar.</span><span class="sxs-lookup"><span data-stu-id="3b7be-143">Submitting batches outside your regular business hours can also help.</span></span>

<span data-ttu-id="3b7be-144">Ejecute lo siguiente para asignar la Directiva de reunión denominada EducatorMeetingPolicy a su personal y educadores.</span><span class="sxs-lookup"><span data-stu-id="3b7be-144">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="3b7be-145">Para asignar un tipo de directiva diferente en masa, como TeamsMessagingPolicy, tendrá que cambiar ```PolicyType``` a la Directiva que está asignando y ```PolicyName``` al nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3b7be-145">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="3b7be-146">Obtener el estado de una asignación masiva</span><span class="sxs-lookup"><span data-stu-id="3b7be-146">Get the status of a bulk assignment</span></span>

<span data-ttu-id="3b7be-147">Cada asignación en masa devuelve un identificador de operación, que puede usar para realizar un seguimiento del progreso de las asignaciones de directivas o para identificar los errores que puedan producirse.</span><span class="sxs-lookup"><span data-stu-id="3b7be-147">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="3b7be-148">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b7be-148">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="3b7be-149">Para ver el estado de asignación de cada usuario en la operación por lotes, ejecute lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3b7be-149">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="3b7be-150">Los detalles de cada usuario están en ```UserState``` la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b7be-150">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a><span data-ttu-id="3b7be-151">Asignar una directiva de forma masiva si tiene más de 20.000 usuarios</span><span class="sxs-lookup"><span data-stu-id="3b7be-151">Assign a policy in bulk if you have more than 20,000 users</span></span>

<span data-ttu-id="3b7be-152">En primer lugar, ejecute lo siguiente para ver cuánto personal y educadores tiene:</span><span class="sxs-lookup"><span data-stu-id="3b7be-152">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="3b7be-153">En lugar de proporcionar la lista completa de identificadores de usuario, ejecute lo siguiente para especificar el primer 20.000, después, el siguiente 20.000, etc.</span><span class="sxs-lookup"><span data-stu-id="3b7be-153">Instead of providing the whole list of user IDs, run the following to specify the first 20,000, and then the next 20,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="3b7be-154">Puede cambiar el intervalo de identificadores de usuario hasta que llegue a la lista completa de usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b7be-154">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="3b7be-155">Por ejemplo, escriba ```$faculty[0..19999``` para el primer lote, use ```$faculty[20000..39999``` para el segundo lote, especifique ```$faculty[40000..59999``` el tercer lote, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3b7be-155">For example, enter ```$faculty[0..19999``` for the first batch, use ```$faculty[20000..39999``` for the second batch, enter ```$faculty[40000..59999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="3b7be-156">Obtener las directivas asignadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="3b7be-156">Get the policies assigned to a user</span></span>

<span data-ttu-id="3b7be-157">Ejecute lo siguiente para ver todas las directivas que se han asignado a un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="3b7be-157">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="3b7be-158">En el ejemplo siguiente se muestra cómo obtener las directivas que se asignan a hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b7be-158">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="3b7be-159">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="3b7be-159">FAQ</span></span>

<span data-ttu-id="3b7be-160">**Quiero asegurarme de que todos los usuarios que son estudiantes, personal y educadores obtengan automáticamente las directivas asignadas. ¿Cómo puedo hacerlo?**</span><span class="sxs-lookup"><span data-stu-id="3b7be-160">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="3b7be-161">El equipo de producto de Teams está trabajando para asignar directivas a grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3b7be-161">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="3b7be-162">En ese momento, podrá crear grupos para los estudiantes y los profesores, y después las directivas correspondientes a esos grupos.</span><span class="sxs-lookup"><span data-stu-id="3b7be-162">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="3b7be-163">Tenga en cuenta que las asignaciones explícitas de usuarios (como las directivas que haya asignado con este tutorial) invalidarán las directivas heredadas de un grupo.</span><span class="sxs-lookup"><span data-stu-id="3b7be-163">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="3b7be-164">Cuando esta característica sea compatible, proporcionaremos más instrucciones sobre cómo usar la asignación de directivas para agrupar y actualizar los usuarios para asegurarse de que obtengan las directivas de grupo heredadas.</span><span class="sxs-lookup"><span data-stu-id="3b7be-164">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="3b7be-165">**No estoy familiarizado con PowerShell para Teams. ¿Dónde puedo obtener más información?**</span><span class="sxs-lookup"><span data-stu-id="3b7be-165">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="3b7be-166">Consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3b7be-166">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b7be-167">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b7be-167">Related topics</span></span>

- [<span data-ttu-id="3b7be-168">Asignar directivas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="3b7be-168">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="3b7be-169">Nuevo: CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="3b7be-169">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="3b7be-170">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="3b7be-170">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="3b7be-171">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="3b7be-171">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
