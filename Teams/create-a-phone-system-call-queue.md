---
title: Crear una cola de llamada
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aprenda a configurar el sistema telefónico para las colas de llamadas en nube para que le proporcione un saludo organizacional, música en espera y redirija las llamadas a agentes de llamadas en listas de distribución y grupos de seguridad. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 63dc71d6fad4fa82e1a335b20612e60c3b56ac91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281950"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="f2f85-104">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f2f85-104">Create a Cloud call queue</span></span>

<span data-ttu-id="f2f85-105">Las colas de llamadas en nube incluyen saludos que se usan cuando un usuario llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman son escuchando música en espera.</span><span class="sxs-lookup"><span data-stu-id="f2f85-105">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="f2f85-106">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="f2f85-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="f2f85-107">Las colas de llamadas en nube pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="f2f85-107">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="f2f85-108">Un mensaje de saludo empresarial.</span><span class="sxs-lookup"><span data-stu-id="f2f85-108">An organizational greeting.</span></span>
- <span data-ttu-id="f2f85-109">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="f2f85-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="f2f85-110">Redireccionamiento de llamadas a agentes de llamadas en listas de distribución habilitadas para correo electrónico y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f2f85-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="f2f85-111">Configuración del tamaño máximo, el tiempo de espera y las opciones de administración de llamadas de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="f2f85-112">Cuando alguien llama a un número de teléfono asociado a una cola de llamadas a través de una [cuenta de recursos](manage-resource-accounts.md), escuchará primero un saludo (si se ha configurado alguno) y, a continuación, se colocará en la cola y esperará al siguiente agente de llamada disponible.</span><span class="sxs-lookup"><span data-stu-id="f2f85-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="f2f85-113">La persona que llama escuchará música mientras se encuentre en espera y las llamadas se ofrecerán a los agentes de llamadas en orden FIFO ( *en el primero en salir* ).</span><span class="sxs-lookup"><span data-stu-id="f2f85-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="f2f85-114">Todas las llamadas en espera en la cola se distribuirán con uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="f2f85-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="f2f85-115">Con el enrutamiento del operador, la primera llamada de la cola sonará a todos los agentes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2f85-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="f2f85-116">Con el enrutamiento en serie, la primera llamada de la cola llamará a todos los agentes uno a uno.</span><span class="sxs-lookup"><span data-stu-id="f2f85-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="f2f85-117">Con la operación por turnos, el enrutamiento de las llamadas entrantes está equilibrado, por lo que cada agente de llamadas recibirá el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="f2f85-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2f85-118">No se llamará a los agentes de llamadas que están **Sin conexión**, han establecido su presencia en **No molestar** o han decidido quedar fuera de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="f2f85-119">Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).</span><span class="sxs-lookup"><span data-stu-id="f2f85-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="f2f85-120">Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="f2f85-121">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="f2f85-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="f2f85-122">Paso 1: introducción</span><span class="sxs-lookup"><span data-stu-id="f2f85-122">Step 1 - Get started</span></span>

<span data-ttu-id="f2f85-123">Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="f2f85-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="f2f85-124">Se necesita una cola de llamadas para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="f2f85-124">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="f2f85-125">Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="f2f85-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="f2f85-126">Si planea asignar un número de enrutamiento directo, debe adquirir y asignar las siguientes licencias a sus cuentas \(de recursos Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico.\)</span><span class="sxs-lookup"><span data-stu-id="f2f85-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="f2f85-127">Si está asignando un número de servicio de Microsoft, debe adquirir y asignar las siguientes licencias a su cuenta \(de recursos Office 365 Enterprise E1, E3 o E5, con el complemento del sistema telefónico y un plan\)de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="f2f85-128">Solo necesita conceder licencia a las cuentas de recursos con un número de teléfono asignado.</span><span class="sxs-lookup"><span data-stu-id="f2f85-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="f2f85-129">En una cola de llamadas o un operador automático anidado, no es necesario que tenga licencia para el resto de los operadores automáticos o las colas de llamadas si no tienen números de teléfono asociados a ellos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-129">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span> 

> [!NOTE] 
> <span data-ttu-id="f2f85-130">Los números del servicio de enrutamiento directo del operador automático y las colas de llamadas solo se admiten para los usuarios y agentes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2f85-130">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="f2f85-131">Microsoft está trabajando en un modelo de licencias sin costo para aplicaciones como los operadores automáticos de la nube y las colas de llamadas, por ahora necesita usar el modelo de licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="f2f85-131">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="f2f85-132">Para redirigir las llamadas a las personas de su organización que están conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2f85-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="f2f85-133">Consulte [asignar licencias de Skype empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="f2f85-134">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2f85-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f2f85-135">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f2f85-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="f2f85-136">Para obtener más información sobre los planes de llamadas de Office 365, consulte planes de llamadas y [sistemas telefónicos](calling-plan-landing-page.md) y [planes de llamadas para Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="f2f85-137">Solo puede asignar números de teléfono de pago y gratuitos que recibió en el **centro de administración de Microsoft Teams** o transferidos de otro proveedor de servicios a colas de llamadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="f2f85-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="f2f85-138">Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="f2f85-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2f85-139">Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="f2f85-140">Al distribuir las llamadas entrantes desde una cola de llamadas en la nube, estos clientes son compatibles con los agentes de llamadas:</span><span class="sxs-lookup"><span data-stu-id="f2f85-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="f2f85-141">Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f2f85-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="f2f85-142">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f2f85-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="f2f85-143">Todos los modelos de teléfono IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2f85-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="f2f85-144">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="f2f85-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="f2f85-145">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="f2f85-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="f2f85-146">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="f2f85-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="f2f85-147">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="f2f85-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="f2f85-148">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="f2f85-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="f2f85-149">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f2f85-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="f2f85-150">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="f2f85-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="f2f85-151">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="f2f85-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="f2f85-152">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="f2f85-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="f2f85-153">Paso 2: obtener o transferir números de servicio de pago o gratuitos</span><span class="sxs-lookup"><span data-stu-id="f2f85-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="f2f85-154">Antes de crear o configurar una cola, tendrá que obtener sus números de servicio de pago o gratuitos, o transferir unos existentes.</span><span class="sxs-lookup"><span data-stu-id="f2f85-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f2f85-155">Una vez que obtenga los números de teléfono de pago o gratuitos, aparecerán en los\*\*\*\* > **números de teléfono**del **Centro** > de administración de Microsoft Teams, y el **tipo de número** que aparece en la lista aparecerá como **servicio-** gratuito.</span><span class="sxs-lookup"><span data-stu-id="f2f85-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f2f85-156">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-156">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2f85-157">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio.</span><span class="sxs-lookup"><span data-stu-id="f2f85-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="f2f85-158">En su lugar, vaya a [administrar números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="f2f85-159">Si también está configurando operadores automáticos, es posible que solo tenga que asignar un número de teléfono a la cuenta de recursos del operador automático principal y, a continuación, hacer que las personas que llaman se dirijan a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="f2f85-160">Si ese es el caso, será necesario crear la cola de llamadas para poder crear una opción en el operador automático que seleccione la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="f2f85-161">Paso 3: crear una nueva cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="f2f85-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="f2f85-162">Cada cola de llamadas debe tener una cuenta de [recursos](manage-resource-accounts.md)asociada.</span><span class="sxs-lookup"><span data-stu-id="f2f85-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="f2f85-163">Debe crear primero la cuenta de recursos y, a continuación, asociarla a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f2f85-164">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2f85-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f2f85-165">En el **centro de administración de Microsoft Teams**,**colas de llamadas**de **voz** >  y, a continuación, haga clic en **+ Agregar nuevo**:</span><span class="sxs-lookup"><span data-stu-id="f2f85-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="f2f85-166">Establecer el nombre para mostrar de la cola de llamadas y la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="f2f85-166">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="f2f85-168">![](media/sfbcallout1.png)
**Nombre** del número 1 Escriba un nombre descriptivo para mostrar para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-168">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="f2f85-169">Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="f2f85-170">Este nombre se mostrará en la notificación de la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="f2f85-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="f2f85-172">**Agregar cuentas** Seleccione una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="f2f85-173">La cuenta de recursos puede estar asociada o no a un número de teléfono gratuito de servicio o a un número de teléfono gratuito para la cola de llamadas, pero cada cola de llamadas requiere una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="f2f85-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="f2f85-174">Si no hay ninguna lista, debe obtener números de servicio y asignarlos a una cuenta de recursos antes de poder crear esta cola de llamadas, como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f2f85-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="f2f85-175">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f2f85-175">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> <span data-ttu-id="f2f85-176">Tendrá que crear una cuenta de recursos como se describe en [administrar cuentas de recursos en Teams](manage-resource-accounts.md) si desea que la cola de llamadas tenga un número de teléfono asociado.</span><span class="sxs-lookup"><span data-stu-id="f2f85-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="f2f85-177">Si quiere o necesita asignar un **dominio** , lo puede asignar a la cuenta de recursos de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="f2f85-178">Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera</span><span class="sxs-lookup"><span data-stu-id="f2f85-178">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="f2f85-181">**Saludo**: este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="f2f85-181">**Greeting** is optional.</span></span> <span data-ttu-id="f2f85-182">Este es el saludo que se reproduce para las personas que llaman al número de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="f2f85-183">Puede cargar un archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="f2f85-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="f2f85-185">**Música en espera** Puede usar la música predeterminada en espera proporcionada con la cola de llamadas, o bien puede cargar un archivo de audio en formato. wav, MP3 o. WMA para usarlo como música personalizada en espera.</span><span class="sxs-lookup"><span data-stu-id="f2f85-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="f2f85-186">Selecciona las opciones de contestador automático</span><span class="sxs-lookup"><span data-stu-id="f2f85-186">Select the call answering options</span></span>

![Muestra las opciones del método de distribución de la llamadas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="f2f85-189">Puede seleccionar hasta 200 agentes de llamadas pertenecientes a grupos o listas de distribución de correo especificados.</span><span class="sxs-lookup"><span data-stu-id="f2f85-189">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="f2f85-190">Los agentes de llamadas deben ser:</span><span class="sxs-lookup"><span data-stu-id="f2f85-190">Call agents must be either:</span></span>

- <span data-ttu-id="f2f85-191">Un usuario en línea con una licencia de **Sistema telefónico** y habilitado para Enterprise Voice o con un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="f2f85-191">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f2f85-192">Para redirigir las llamadas a las personas de su organización que están conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para la telefonía IP empresarial o tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-192">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="f2f85-193">Consulte [asignar licencias de Skype empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-193">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="f2f85-194">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2f85-194">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f2f85-195">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f2f85-195">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="f2f85-196">Usuarios en línea con una licencia de **Sistema telefónico** y un Plan de llamadas que se agregan a un grupo de Office 365, una lista de distribución habilitada para correo o un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f2f85-196">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="f2f85-197">Puede demorar hasta 3 horas en agregar un nuevo agente para una lista de distribución o un grupo de seguridad para empezar a recibir llamadas de una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-197">It might take up to 3 hours for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="f2f85-198">Una lista de distribución o un grupo de seguridad recién creados puede demorar 48 horas en estar disponible para usarse con las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="f2f85-199">Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="f2f85-199">Newly created Office 365 Groups are available almost immediately.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="f2f85-202">**Método de enrutamiento** Puede elegir entre **operador**, **serie**o **Round Robin** para el método de distribución de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-202">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="f2f85-203">De manera predeterminada, todas las colas de llamadas nuevas y existentes tienen un enrutamiento a operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f2f85-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="f2f85-204">Cuando se usa el enrutamiento de operador, la primera llamada en la cola sonará a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2f85-204">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="f2f85-205">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2f85-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="f2f85-206">El **enrutamiento del operador** hace que la primera llamada de la cola suene a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2f85-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="f2f85-207">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2f85-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="f2f85-208">El **enrutamiento serie** llamará a los agentes de llamadas entrantes uno por uno, empezando desde el principio de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-208">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="f2f85-209">Los agentes no se pueden pedir dentro de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-209">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="f2f85-210">Si un agente omite o no contesta una llamada, se realizará una llamada al siguiente agente de la lista y se probará con todos los agentes, de uno a uno, hasta que se responda la llamada o se agote el tiempo de espera en la cola.</span><span class="sxs-lookup"><span data-stu-id="f2f85-210">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="f2f85-211">El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola.</span><span class="sxs-lookup"><span data-stu-id="f2f85-211">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="f2f85-212">El enrutamiento **Round Robin** de equilibra las llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="f2f85-212">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="f2f85-213">Esto puede ser muy conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-213">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="f2f85-214">Seleccionar una opción de no participación de agente</span><span class="sxs-lookup"><span data-stu-id="f2f85-214">Select an agent opt out option</span></span>

![Muestra la casilla de verificación de no participación de agente](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="f2f85-217">**Opción de no participación de agente** Puede elegir esta opción para permitir a los agentes de la cola de llamadas no participar en la recepción de llamadas procedentes de una cola determinada mediante la selección de **Opción de no participación de agente**.</span><span class="sxs-lookup"><span data-stu-id="f2f85-217">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="f2f85-218">Al habilitar esta opción, todos los agentes de esta cola iniciarán o dejarán de recibir llamadas de esta cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-218">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="f2f85-219">Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).</span><span class="sxs-lookup"><span data-stu-id="f2f85-219">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="f2f85-220">Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2f85-220">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="f2f85-221">Abra **Opciones** en el cliente de Skype for Business de su escritorio.</span><span class="sxs-lookup"><span data-stu-id="f2f85-221">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="f2f85-222">En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.</span><span class="sxs-lookup"><span data-stu-id="f2f85-222">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="f2f85-223">En la página de configuración del usuario, haga clic en **Colas de llamadas**y, a continuación, desactive las casillas de verificación de las colas en las que no desee participar.</span><span class="sxs-lookup"><span data-stu-id="f2f85-223">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2f85-224">Los agentes que usen aplicaciones o extremos distintos del escritorio de Skype empresarial pueden acceder a la opción de cancelación del portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings)de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="f2f85-224">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="f2f85-225">![Configuración de](media/sfbcallout2.png)
**alertas del agente** número 2</span><span class="sxs-lookup"><span data-stu-id="f2f85-225">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="f2f85-226">Esto define la duración de un agente de notificación de una llamada antes de que los métodos de enrutamiento de serie o de turnos pasen al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="f2f85-226">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="f2f85-227">La configuración predeterminada es de 30 segundos, pero se puede establecer hasta 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-227">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="f2f85-228">Establecer las opciones de desbordamiento de llamadas y administración de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="f2f85-228">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="f2f85-231">**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2f85-231">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="f2f85-232">El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="f2f85-232">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="f2f85-233">Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="f2f85-233">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="f2f85-235">**Cuando se alcanza el número máximo de llamadas** Cuando la cola de llamadas alcanza su tamaño máximo (establecido mediante las **llamadas máximas en la configuración de la cola** ), puede elegir qué sucede con las llamadas entrantes nuevas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-235">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="f2f85-236">**Desconectar**: la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="f2f85-236">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="f2f85-237">**Redirigir a** Si elige esta opción, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f2f85-237">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="f2f85-238">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="f2f85-239">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f2f85-239">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="f2f85-240">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="f2f85-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="f2f85-241">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-241">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="f2f85-242">**Aplicación de voz** Seleccione el nombre de una cola de llamadas o del operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="f2f85-242">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="f2f85-244">**Tiempo de espera de llamada: tiempo de espera máximo** También puede decidir cuánto tiempo puede estar en espera una llamada en la cola antes de que se agote el tiempo de espera y deba redirigirse o desconectarse.</span><span class="sxs-lookup"><span data-stu-id="f2f85-244">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="f2f85-245">Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**.</span><span class="sxs-lookup"><span data-stu-id="f2f85-245">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="f2f85-246">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-246">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="f2f85-247">El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="f2f85-247">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="f2f85-248">Esto permite manipular el flujo de llamadas con una granularidad más fina.</span><span class="sxs-lookup"><span data-stu-id="f2f85-248">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="f2f85-249">Por ejemplo, puede especificar que las llamadas no contestadas por un agente en un plazo de 30 segundos vayan a un operador automático de búsqueda de directorios.</span><span class="sxs-lookup"><span data-stu-id="f2f85-249">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="f2f85-251">**Cuando la llamada supera el tiempo de salida** Cuando la llamada alcanza el límite establecido en el valor de **tiempo que puede esperar una llamada en la cola** , puede elegir lo que le sucede a esta llamada:</span><span class="sxs-lookup"><span data-stu-id="f2f85-251">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="f2f85-252">**Desconectar**: la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="f2f85-252">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="f2f85-253">**Redirigir esta llamada a** Si elige esta opción, tendrá las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f2f85-253">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="f2f85-254">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o para tener planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-254">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="f2f85-255">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f2f85-255">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="f2f85-256">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="f2f85-256">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="f2f85-257">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-257">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="f2f85-258">**Aplicación de voz** Seleccione el nombre de una cola de llamadas o del operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="f2f85-258">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="f2f85-259">Cambiar la identificación de llamadas de un usuario para las llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="f2f85-259">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="f2f85-260">Puede proteger la identidad de un usuario si cambia la identificación de llamadas para las llamadas salientes a una cola de llamadas, a un operador automático o a cualquier número de servicio mediante la creación de una directiva con el cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="f2f85-260">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="f2f85-261">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f2f85-261">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="f2f85-262">A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="f2f85-262">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="f2f85-263">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f2f85-263">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="f2f85-264">Puede obtener más información sobre cómo realizar cambios en la configuración de identificación de llamadas de su organización en el artículo [cómo se puede usar la identificación de llamadas en su organización](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="f2f85-264">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="f2f85-265">¿Desea obtener más información?</span><span class="sxs-lookup"><span data-stu-id="f2f85-265">Want to know more?</span></span>

<span data-ttu-id="f2f85-266">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-266">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="f2f85-267">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="f2f85-267">Call queue cmdlets</span></span>

<span data-ttu-id="f2f85-268">Estos son los cmdlets que necesita para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-268">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="f2f85-269">Nuevo: CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f2f85-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="f2f85-270">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f2f85-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="f2f85-271">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f2f85-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="f2f85-272">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f2f85-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="f2f85-273">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2f85-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="f2f85-274">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="f2f85-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f2f85-275">Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración que puede simplificar su trabajo diario, cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="f2f85-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f2f85-276">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="f2f85-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="f2f85-277">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f2f85-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="f2f85-278">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="f2f85-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="f2f85-279">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar solo el centro de administración de Microsoft Teams, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="f2f85-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f2f85-280">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f2f85-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="f2f85-281">Administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2f85-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="f2f85-282">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2f85-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="f2f85-283">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f2f85-283">Related topics</span></span>

[<span data-ttu-id="f2f85-284">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="f2f85-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f2f85-285">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="f2f85-285">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="f2f85-286">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="f2f85-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="f2f85-287">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f2f85-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
