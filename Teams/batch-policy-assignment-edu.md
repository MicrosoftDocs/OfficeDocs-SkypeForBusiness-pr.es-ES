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
ms.openlocfilehash: e95c6b035298ce583a0ad34a030f2086b7c12ff3
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583356"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="5cf76-103">Asignar directivas a grandes conjuntos de usuarios de la escuela</span><span class="sxs-lookup"><span data-stu-id="5cf76-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="5cf76-104">¿Necesita dar acceso a las diferentes características de Microsoft Teams a sus alumnos y educadores?</span><span class="sxs-lookup"><span data-stu-id="5cf76-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="5cf76-105">Puede identificar rápidamente los usuarios de su organización por tipo de licencia y, a continuación, asignarles la Directiva adecuada.</span><span class="sxs-lookup"><span data-stu-id="5cf76-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="5cf76-106">En este tutorial se muestra cómo usar la [asignación de directivas por lotes](assign-policies.md#assign-a-policy-to-a-batch-of-users) para asignar una directiva de reunión a los usuarios de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="5cf76-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="5cf76-107">Recuerde que en Teams, los usuarios obtienen automáticamente la directiva global (opción predeterminada para toda la organización) para un tipo de directiva de Teams, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="5cf76-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="5cf76-108">Como la población de alumnos suele ser el mayor conjunto de usuarios y a menudo reciben la configuración más restrictiva, le recomendamos que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5cf76-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="5cf76-109">Edite y aplique la directiva global (valor predeterminado de la organización) para restringir las capacidades de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="5cf76-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="5cf76-110">Crear una directiva personalizada que permita capacidades básicas, como la programación privada de chats y reuniones, y la asignación de la Directiva a su personal y educadores.</span><span class="sxs-lookup"><span data-stu-id="5cf76-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="5cf76-111">Tenga en cuenta que la directiva global se aplicará a todos los usuarios de su escuela hasta que cree una directiva personalizada y la asigne a su personal y educadores.</span><span class="sxs-lookup"><span data-stu-id="5cf76-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="5cf76-112">En este tutorial, los alumnos obtendrán la Directiva de reunión global y usamos PowerShell para asignar una directiva de reuniones personalizada denominada EducatorMeetingPolicy al personal y los educadores en bloque.</span><span class="sxs-lookup"><span data-stu-id="5cf76-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="5cf76-113">Damos por hecho que ha modificado la directiva global para personalizar la configuración de la reunión de los alumnos y creado una directiva personalizada que define la experiencia de la reunión para el personal y los educadores.</span><span class="sxs-lookup"><span data-stu-id="5cf76-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Captura de pantalla de la página directivas de la reunión en el centro de administración de Teams](media/edu-batch-policy-assignment.png)

<span data-ttu-id="5cf76-115">Siga estos pasos para asignar una directiva de reunión personalizada al personal y educadores de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="5cf76-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="5cf76-116">Conectarse al módulo de Azure AD PowerShell para Graph y al módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="5cf76-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="5cf76-117">Antes de realizar los pasos de este artículo, tendrá que instalar y conectarse al módulo Azure AD PowerShell for Graph (para identificar a los usuarios por sus licencias asignadas) y la versión preliminar del módulo Microsoft Teams PowerShell (para asignar las directivas a esos usuarios).</span><span class="sxs-lookup"><span data-stu-id="5cf76-117">Before you perform the steps in this article, you’ll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the pre-release version of the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="5cf76-118">Instalar y conectarse al módulo de Azure AD PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="5cf76-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="5cf76-119">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador) y, a continuación, ejecute lo siguiente para instalar el módulo Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="5cf76-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module AzureAD
```

<span data-ttu-id="5cf76-120">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5cf76-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="5cf76-121">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="5cf76-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="5cf76-122">Para obtener más información, vea [conectarse con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5cf76-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="5cf76-123">Instalar y conectarse a la versión preliminar del módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="5cf76-123">Install and connect to the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="5cf76-124">Los cmdlets que necesitará se encuentran en la versión preliminar del módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="5cf76-124">The cmdlets you'll need are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="5cf76-125">Siga los pasos que se indican en [instalar y conectarse al módulo Microsoft Teams PowerShell](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) para desinstalar primero la versión disponible general del módulo de PowerShell de Teams (si está instalado) y, a continuación, instale la última versión preliminar del módulo de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cf76-125">Follow the steps in [Install and connect to the Microsoft Teams PowerShell module](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="5cf76-126">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="5cf76-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="5cf76-127">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5cf76-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="5cf76-128">Identificar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="5cf76-128">Identify your users</span></span>

<span data-ttu-id="5cf76-129">En primer lugar, ejecute lo siguiente para identificar a su personal y educadores por tipo de licencia.</span><span class="sxs-lookup"><span data-stu-id="5cf76-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="5cf76-130">Esto le indica qué SKU están en uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="5cf76-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="5cf76-131">A continuación, puede identificar el personal y los formadores que tienen una SKU de profesores asignados.</span><span class="sxs-lookup"><span data-stu-id="5cf76-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

<span data-ttu-id="5cf76-132">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="5cf76-132">Which returns:</span></span>

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="5cf76-133">En este ejemplo, la salida muestra que el SkuId de la licencia del profesorado es "e97c048c-37a4-45FB-AB50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="5cf76-133">In this example, the output shows that the Faculty license SkuId is “e97c048c-37a4-45fb-ab50-922fbf07a370”.</span></span>

> [!NOTE]
> <span data-ttu-id="5cf76-134">Para ver una lista de SKU de educación e identificadores de SKU, consulte [educación SKU SKU](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="5cf76-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="5cf76-135">A continuación, ejecutamos lo siguiente para identificar los usuarios que tienen esta licencia y recopilar todas ellas.</span><span class="sxs-lookup"><span data-stu-id="5cf76-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains “e97c048c-37a4-45fb-ab50-922fbf07a370”)
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="5cf76-136">Asignar una directiva en masa</span><span class="sxs-lookup"><span data-stu-id="5cf76-136">Assign a policy in bulk</span></span>

<span data-ttu-id="5cf76-137">Ahora, asignamos las directivas apropiadas a usuarios de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="5cf76-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="5cf76-138">La cantidad máxima de usuarios para los que puede asignar o actualizar directivas es 20.000 a la vez.</span><span class="sxs-lookup"><span data-stu-id="5cf76-138">The maximum number of users for which you can assign or update policies is 20,000 at a time.</span></span> <span data-ttu-id="5cf76-139">Por ejemplo, si tiene más de 20.000 de personal y educadores, tendrá que enviar varios lotes.</span><span class="sxs-lookup"><span data-stu-id="5cf76-139">For example, if you have more than 20,000 staff and educators, you’ll need to submit multiple batches.</span></span>

<span data-ttu-id="5cf76-140">Ejecute lo siguiente para asignar la Directiva de reunión denominada EducatorMeetingPolicy a su personal y educadores.</span><span class="sxs-lookup"><span data-stu-id="5cf76-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="5cf76-141">Para asignar un tipo de directiva diferente en masa, como TeamsMessagingPolicy, tendrá que cambiar ```PolicyType``` a la Directiva que está asignando y ```PolicyName``` al nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="5cf76-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you’ll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="5cf76-142">Obtener el estado de una asignación masiva</span><span class="sxs-lookup"><span data-stu-id="5cf76-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="5cf76-143">Cada asignación en masa devuelve un identificador de operación, que puede usar para realizar un seguimiento del progreso de las asignaciones de directivas o para identificar los errores que puedan producirse.</span><span class="sxs-lookup"><span data-stu-id="5cf76-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="5cf76-144">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5cf76-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="5cf76-145">Para ver el estado de asignación de cada usuario en la operación por lotes, ejecute lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5cf76-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="5cf76-146">Los detalles de cada usuario están en ```UserState``` la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5cf76-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a><span data-ttu-id="5cf76-147">Asignar una directiva de forma masiva si tiene más de 20.000 usuarios</span><span class="sxs-lookup"><span data-stu-id="5cf76-147">Assign a policy in bulk if you have more than 20,000 users</span></span>

<span data-ttu-id="5cf76-148">En primer lugar, ejecute lo siguiente para ver cuánto personal y educadores tiene:</span><span class="sxs-lookup"><span data-stu-id="5cf76-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="5cf76-149">En lugar de proporcionar la lista completa de identificadores de usuario, ejecute lo siguiente para especificar el primer 20.000, después, el siguiente 20.000, etc.</span><span class="sxs-lookup"><span data-stu-id="5cf76-149">Instead of providing the whole list of user IDs, run the following to specify the first 20,000, and then the next 20,000, and so on.</span></span>

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

<span data-ttu-id="5cf76-150">Puede cambiar el intervalo de identificadores de usuario hasta que llegue a la lista completa de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5cf76-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="5cf76-151">Por ejemplo, escriba ```$faculty[0..19999``` para el primer lote, use ```$faculty[20000..39999``` para el segundo lote, especifique ```$faculty[40000..59999``` el tercer lote, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5cf76-151">For example, enter ```$faculty[0..19999``` for the first batch, use ```$faculty[20000..39999``` for the second batch, enter ```$faculty[40000..59999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="5cf76-152">Obtener las directivas asignadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="5cf76-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="5cf76-153">Ejecute lo siguiente para ver todas las directivas que se han asignado a un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="5cf76-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="5cf76-154">En el ejemplo siguiente se muestra cómo obtener las directivas que se asignan a hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5cf76-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="5cf76-155">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="5cf76-155">FAQ</span></span>

<span data-ttu-id="5cf76-156">**Quiero asegurarme de que todos los usuarios que sean estudiantes, personal y educadores obtengan licencias automáticamente asignadas. ¿Cómo puedo hacerlo?**</span><span class="sxs-lookup"><span data-stu-id="5cf76-156">**I want to make sure that all users that are students, staff, and educators automatically get licenses assigned. How can I do that?**</span></span>

<span data-ttu-id="5cf76-157">El equipo de producto de Teams está trabajando para asignar directivas a grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5cf76-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="5cf76-158">En ese momento, podrá crear grupos para los estudiantes y los profesores, y después las directivas correspondientes a esos grupos.</span><span class="sxs-lookup"><span data-stu-id="5cf76-158">At that time, you’ll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="5cf76-159">Tenga en cuenta que las asignaciones explícitas de usuarios (como las directivas que haya asignado con este tutorial) invalidarán las directivas heredadas de un grupo.</span><span class="sxs-lookup"><span data-stu-id="5cf76-159">Note that explicit user assignments (such as the policies that you’ve assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="5cf76-160">Cuando esta característica sea compatible, proporcionaremos más instrucciones sobre cómo usar la asignación de directivas para agrupar y actualizar los usuarios para asegurarse de que obtengan las directivas de grupo heredadas.</span><span class="sxs-lookup"><span data-stu-id="5cf76-160">When this feature is supported, we’ll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="5cf76-161">**No estoy familiarizado con PowerShell para Teams. ¿Dónde puedo obtener más información?**</span><span class="sxs-lookup"><span data-stu-id="5cf76-161">**I’m not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="5cf76-162">Consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5cf76-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5cf76-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5cf76-163">Related topics</span></span>

- [<span data-ttu-id="5cf76-164">Asignar directivas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="5cf76-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="5cf76-165">Nuevo: CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="5cf76-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="5cf76-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="5cf76-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="5cf76-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="5cf76-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)