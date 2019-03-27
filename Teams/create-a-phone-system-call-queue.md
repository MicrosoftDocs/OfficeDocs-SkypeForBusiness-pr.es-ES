---
title: Crear una cola de llamadas para el Sistema telefónico
ms.author: jambirk
author: jambirk
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar el sistema telefónico para las colas de llamadas de sistema telefónico dar un saludo, música en espera, organizativas y redirigir las llamadas para llamar a los agentes en las listas de distribución y grupos de seguridad. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 924885ff62bb0e7e2ba0f25cc348dc62eb29ec32
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898169"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="c5c38-104">Crear una cola de llamadas para el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="c5c38-104">Create a Phone System call queue</span></span>

<span data-ttu-id="c5c38-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span><span class="sxs-lookup"><span data-stu-id="c5c38-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="c5c38-107">Las colas de llamadas del Sistema telefónico pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="c5c38-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="c5c38-108">Un mensaje de saludo empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5c38-108">An organizational greeting.</span></span>
- <span data-ttu-id="c5c38-109">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="c5c38-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="c5c38-110">El redireccionamiento de llamadas para llamar a los agentes en las listas de distribución habilitados para correo y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c5c38-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="c5c38-111">Realizar la configuración de tamaño máximo de la cola de llamadas, tiempo de espera y las opciones de administración de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="c5c38-112">Cuando alguien llama a un número de teléfono que está asociado con una cola de llamadas a través de una [cuenta de recurso](manage-resource-accounts.md), escuchará un saludo inicial (si se configura cualquiera) y, a continuación, se coloca en la cola y espere a que el siguiente agente de llamada disponibles.</span><span class="sxs-lookup"><span data-stu-id="c5c38-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="c5c38-113">La persona que llama escuchará música mientras están en espera en espera y las llamadas se ofrecerán a los agentes de llamada en orden *Primero en ENTRAR, primero en salir* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="c5c38-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="c5c38-114">Todas las llamadas en espera en la cola se distribuirá mediante un modo de enrutamiento operador o el modo de enrutamiento en serie:</span><span class="sxs-lookup"><span data-stu-id="c5c38-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="c5c38-115">Con el operador de enrutamiento, la primera llamada en la cola sonarán a todos los agentes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5c38-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="c5c38-116">Con el enrutamiento en serie, la primera llamada de la cola llamará a todos los agentes uno a uno.</span><span class="sxs-lookup"><span data-stu-id="c5c38-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5c38-117">No se llamará a los agentes de llamadas que están **Sin conexión**, han establecido su presencia en **No molestar** o han decidido quedar fuera de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="c5c38-118">Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).</span><span class="sxs-lookup"><span data-stu-id="c5c38-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="c5c38-119">Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="c5c38-120">En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="c5c38-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="c5c38-121">Paso 1: Introducción</span><span class="sxs-lookup"><span data-stu-id="c5c38-121">Step 1 - Get started</span></span>

<span data-ttu-id="c5c38-122">Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="c5c38-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="c5c38-123">Su organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema telefónico** o una licencia Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="c5c38-123">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="c5c38-124">El número de licencias de usuario de **Sistema telefónico** que se asignan afecta al número de números de servicio que están disponibles para usarse en las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-124">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="c5c38-125">El número de colas de llamada que puede tener depende de que el número de licencias de **Sistema telefónico** y **Conferencias de Audio** que se asignan en la organización.</span><span class="sxs-lookup"><span data-stu-id="c5c38-125">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="c5c38-126">Para obtener más información acerca de las licencias, vea [Skype para licencias de complemento de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) o [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="c5c38-126">To learn more about licensing, see [Skype for Business add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) or [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5c38-127">Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5c38-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c5c38-128">Vea [Asignar Skype para licencias de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-128">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c5c38-129">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5c38-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c5c38-130">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c5c38-130">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="c5c38-131">Para obtener más información acerca de planes de llamada de Office 365, vea [sistema telefónico y llamar a los planes](calling-plan-landing-page.md) y [Llamar a los planes de Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-131">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5c38-132">Los usuarios alojados en implementaciones locales con Lync Server 2010 no se admiten como una cola de llamada de los agentes.</span><span class="sxs-lookup"><span data-stu-id="c5c38-132">Users hosted on-premises using Lync Server 2010 aren't supported as a call queue Agents.</span></span>
  
- <span data-ttu-id="c5c38-133">Sólo se pueden asignar números de pago y los números de teléfono gratuito de servicio que se obtuvo en el **Centro de administración de equipos de Microsoft** o se transfiere desde otro proveedor de servicios a las colas de llamadas de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="c5c38-133">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="c5c38-134">Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="c5c38-134">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5c38-135">Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.</span><span class="sxs-lookup"><span data-stu-id="c5c38-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="c5c38-136">Cuando se va a distribuir las llamadas entrantes de una cola de llamada de sistema telefónico, estos clientes son compatibles para agentes de llamada:</span><span class="sxs-lookup"><span data-stu-id="c5c38-136">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="c5c38-137">Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c5c38-137">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c5c38-138">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c5c38-138">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c5c38-139">Todos los modelos de teléfono IP compatible con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c5c38-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c5c38-140">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c5c38-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="c5c38-141">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c5c38-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="c5c38-142">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c5c38-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="c5c38-143">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c5c38-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c5c38-144">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c5c38-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c5c38-145">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c5c38-145">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c5c38-146">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="c5c38-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="c5c38-147">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="c5c38-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="c5c38-148">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="c5c38-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="c5c38-149">Paso 2: obtener o transferir números de servicio de pago o gratuitos</span><span class="sxs-lookup"><span data-stu-id="c5c38-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="c5c38-150">Antes de crear o configurar una cola, tendrá que obtener sus números de servicio de pago o gratuitos, o transferir unos existentes.</span><span class="sxs-lookup"><span data-stu-id="c5c38-150">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c5c38-151">Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="c5c38-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c5c38-152">Para obtener sus números de servicio, vea [los números de teléfono del servicio de obtención](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) o si desea transferir un número de servicio existente, vea [los números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-152">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5c38-153">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio.</span><span class="sxs-lookup"><span data-stu-id="c5c38-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c5c38-154">Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c5c38-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="c5c38-155">Si también está configurando operadores automáticos, es posible que sólo debe asignar a un número de teléfono a la cuenta del recurso del operador automático principal, y, a continuación, hacer que los autores de llamadas directas a la cola de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-155">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="c5c38-156">Si ese es el caso, la cola de llamadas se debe crearse antes de poder crear una opción en el operador automático de que selecciona la cola de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-156">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="c5c38-157">Paso 3: crear una nueva cola de llamada</span><span class="sxs-lookup"><span data-stu-id="c5c38-157">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="c5c38-158">Cada cola de llamada es necesario tener asociado a una [cuenta del recurso](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c5c38-159">Debe crear la cuenta del recurso en primer lugar, a continuación, se puede asociar a la cola de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c5c38-160">Desde el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5c38-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c5c38-161">En el **Centro de administración de equipos de Microsoft**, **voz** >  **colas de llamadas**, a continuación, haga clic en **+ Agregar nuevo**:</span><span class="sxs-lookup"><span data-stu-id="c5c38-161">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="c5c38-162">Establecer la llamada de cola para mostrar recursos y nombre de cuenta</span><span class="sxs-lookup"><span data-stu-id="c5c38-162">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="c5c38-164">![Número 1](media/sfbcallout1.png)
**nombre** escriba un nombre para mostrar descriptivo para la cola de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-164">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="c5c38-165">Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.</span><span class="sxs-lookup"><span data-stu-id="c5c38-165">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="c5c38-166">Este nombre se mostrará en la notificación de la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="c5c38-166">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="c5c38-168">**Agregar cuentas** Seleccione una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="c5c38-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="c5c38-169">La cuenta del recurso puede o no puede estar asociada con un teléfono de pago de servicio o el número de teléfono gratuito de la cola de llamadas, pero cada cola llamada requiere una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="c5c38-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="c5c38-170">Si no existe ninguno en la lista, debe obtener los números de servicio y asignarlos a una cuenta de recursos con el para poder crear esta cola de llamadas, tal y como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c5c38-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="c5c38-171">Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="c5c38-171">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> <span data-ttu-id="c5c38-172">Debe crear una cuenta de recurso tal como se describe en [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) , si desea que la cola de llamada tiene un número de teléfono asociado.</span><span class="sxs-lookup"><span data-stu-id="c5c38-172">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="c5c38-173">Si desea o necesita asignar un **dominio** sería hacerlo mediante la asignación a la cuenta del recurso de la cola de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="c5c38-174">Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera</span><span class="sxs-lookup"><span data-stu-id="c5c38-174">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="c5c38-177">**Saludo**: este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="c5c38-177">**Greeting** is optional.</span></span> <span data-ttu-id="c5c38-178">Este es el saludo que se reproduce para las personas que llamar el número de llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="c5c38-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="c5c38-179">Puede cargar un archivo de audio (formatos .wav,. mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="c5c38-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="c5c38-181">**Música en espera** Puede usar el valor predeterminado de música en espera que se proporcionan con la cola de llamadas, o puede cargar un archivo de audio en los formatos WAV, mp3 o .wma que se utilizará como su personalizado de música en espera.</span><span class="sxs-lookup"><span data-stu-id="c5c38-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="c5c38-182">Seleccione el contestador automático opciones</span><span class="sxs-lookup"><span data-stu-id="c5c38-182">Select the call answering options</span></span>

![Muestra las opciones del método de distribución de la llamadas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="c5c38-185">Puede seleccionar a un máximo de 200 agentes de llamada que pertenecen a grupos o listas de correo especificadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-185">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="c5c38-186">Los agentes de llamada deben ser:</span><span class="sxs-lookup"><span data-stu-id="c5c38-186">Call agents must be either:</span></span>

- <span data-ttu-id="c5c38-187">Un usuario en línea con una licencia de **Sistema telefónico** y habilitado para Enterprise Voice o con un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-187">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5c38-188">Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o disponer de un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-188">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c5c38-189">Vea [Asignar Skype para licencias de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-189">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="c5c38-190">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5c38-190">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c5c38-191">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c5c38-191">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c5c38-192">Usuarios en línea con una licencia de **Sistema telefónico** y un Plan de llamadas que se agregan a un grupo de Office 365, una lista de distribución habilitada para correo o un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c5c38-192">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="c5c38-193">El nuevo agente agregado a una lista de distribución o a un grupo de seguridad podría tardar hasta 30 minutos en recibir llamadas de una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-193">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="c5c38-194">Un grupo de seguridad o lista de distribución recién creado puede tardar hasta 48 horas para que estén disponibles para usarse con colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-194">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="c5c38-195">Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="c5c38-195">Newly created Office 365 Groups are available almost immediately.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5c38-196">Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c5c38-196">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="c5c38-199">**Método de enrutamiento** Puede elegir ya sea **operador**, **en serie**o **Round Robin** para el método de distribución de la cola de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-199">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="c5c38-200">De manera predeterminada, todas las colas de llamadas nuevas y existentes tienen un enrutamiento a operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5c38-200">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="c5c38-201">Cuando se usa el operador de enrutamiento, la primera llamada en la cola sonarán todos los agentes de la llamada al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5c38-201">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="c5c38-202">El primer agente de llamada para atender la llamada, obtiene la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-202">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c5c38-203">**Enrutamiento de operador** hace que la primera llamada en la cola para llamar a todos los agentes de la llamada al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5c38-203">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="c5c38-204">El primer agente de llamada para atender la llamada, obtiene la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-204">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="c5c38-205">**Enrutamiento en serie** , hace que las llamadas entrantes llamar a los agentes de llamada uno a uno, comenzando por el principio de la lista de agentes de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-205">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="c5c38-206">Si un agente omite o no contesta una llamada, se realizará una llamada al siguiente agente de la lista y se probará con todos los agentes, de uno a uno, hasta que se responda la llamada o se agote el tiempo de espera en la cola.</span><span class="sxs-lookup"><span data-stu-id="c5c38-206">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c5c38-207">El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola.</span><span class="sxs-lookup"><span data-stu-id="c5c38-207">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="c5c38-208">**Operación por turnos** equilibra el enrutamiento de las llamadas entrantes de manera que cada agente de llamada obtendrá el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="c5c38-208">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="c5c38-209">Esto puede resultar muy deseable en un entorno de venta entrante para garantizar la igualdad de oportunidades entre todos los agentes de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-209">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="c5c38-210">Seleccionar una opción de no participación de agente</span><span class="sxs-lookup"><span data-stu-id="c5c38-210">Select an agent opt out option</span></span>

![Muestra la casilla de verificación de no participación de agente](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="c5c38-213">**Opción de no participación de agente** Puede elegir esta opción para permitir a los agentes de la cola de llamadas no participar en la recepción de llamadas procedentes de una cola determinada mediante la selección de **Opción de no participación de agente**.</span><span class="sxs-lookup"><span data-stu-id="c5c38-213">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="c5c38-214">Si habilita esta opción permite que va todos los agentes en esta cola para iniciar o detener la recepción de llamadas desde esta cola de llamada en.</span><span class="sxs-lookup"><span data-stu-id="c5c38-214">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="c5c38-215">Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).</span><span class="sxs-lookup"><span data-stu-id="c5c38-215">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="c5c38-216">Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5c38-216">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="c5c38-217">Abra **Opciones** en el cliente de Skype for Business de su escritorio.</span><span class="sxs-lookup"><span data-stu-id="c5c38-217">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="c5c38-218">En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.</span><span class="sxs-lookup"><span data-stu-id="c5c38-218">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="c5c38-219">En la página de configuración del usuario, haga clic en **Colas de llamadas**y, a continuación, desactive las casillas de verificación de las colas en las que no desee participar.</span><span class="sxs-lookup"><span data-stu-id="c5c38-219">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5c38-220">Los agentes con clientes Mac, Mobile o Lync 2013 o los usuarios de Voz híbrida alojados localmente que utilicen Skype for Business 2015 pueden ir a [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para tener acceso a la opción de no participación.</span><span class="sxs-lookup"><span data-stu-id="c5c38-220">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

<span data-ttu-id="c5c38-221">![Número 2](media/sfbcallout2.png)
**configuración de alerta del agente**</span><span class="sxs-lookup"><span data-stu-id="c5c38-221">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="c5c38-222">Esto define la duración de un agente se notifique de una llamada antes de la serie o métodos de enrutamiento Round Robin mover al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="c5c38-222">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="c5c38-223">El valor predeterminado es 30 segundos, pero se puede establecer para hasta 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="c5c38-223">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="c5c38-224">Establecer el desbordamiento de la llamada y el tiempo de espera de las opciones de control</span><span class="sxs-lookup"><span data-stu-id="c5c38-224">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="c5c38-227">**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5c38-227">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="c5c38-228">El valor predeterminado es 50, pero puede oscilar entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="c5c38-228">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c5c38-229">Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="c5c38-229">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="c5c38-231">**Cuando se alcanza el número máximo de llamadas** Cuando la cola llamada alcanza su tamaño máximo (establecido con el valor **máximo de llamadas en la cola** ), puede elegir lo que ocurre con las nuevas llamadas recibidas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-231">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="c5c38-232">**Desconectar**: la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="c5c38-232">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c5c38-233">**Redirigir a** Cuando se selecciona esta opción, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c5c38-233">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="c5c38-234">**Persona de la empresa** Un usuario con una licencia de **Sistema telefónico** en línea y estar habilitados para Enterprise Voice o disponer de un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-234">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c5c38-235">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="c5c38-235">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c5c38-236">Para ello, seleccione una **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="c5c38-236">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c5c38-237">Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz de Sistema telefónico](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-237">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="c5c38-238">Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c5c38-238">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>
  - <span data-ttu-id="c5c38-239">**Aplicación de voz** Seleccione el nombre de uno de ellos en una cola de llamada u operadores automáticos que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="c5c38-239">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="c5c38-241">**Llamar a tiempo de espera: tiempo de espera máximo** También puede decidir cuánto tiempo una llamada puede ser en espera en la cola antes de que se agota el tiempo y se debe redirigir o desconectado.</span><span class="sxs-lookup"><span data-stu-id="c5c38-241">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="c5c38-242">Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**.</span><span class="sxs-lookup"><span data-stu-id="c5c38-242">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="c5c38-243">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="c5c38-243">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="c5c38-244">El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="c5c38-244">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="c5c38-245">Esto permite manipular el flujo de llamadas con una granularidad más fina.</span><span class="sxs-lookup"><span data-stu-id="c5c38-245">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="c5c38-246">Por ejemplo, podría especificar que todas las llamadas que un agente no responde dentro de 30 segundos vaya a un operador automático de búsqueda en el directorio.</span><span class="sxs-lookup"><span data-stu-id="c5c38-246">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="c5c38-248">**Cuando se agota el tiempo de espera de llamada** Cuando la llamada alcanza el límite establecido en la configuración de **cuánto tiempo puede esperar una llamada en la cola** , puede elegir lo que ocurre con esta llamada:</span><span class="sxs-lookup"><span data-stu-id="c5c38-248">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="c5c38-249">**Desconectar**: la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="c5c38-249">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c5c38-250">**Redirigir esta llamada a** Cuando se selecciona esta opción, tendrá estas opciones:</span><span class="sxs-lookup"><span data-stu-id="c5c38-250">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="c5c38-251">**Persona de la empresa** Un usuario con una licencia de **Sistema telefónico** en línea y estar habilitados para Enterprise Voice o tienen planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5c38-251">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="c5c38-252">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="c5c38-252">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c5c38-253">Para ello, seleccione una **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="c5c38-253">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c5c38-254">Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz de Sistema telefónico](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c5c38-254">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="c5c38-255">Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c5c38-255">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

  - <span data-ttu-id="c5c38-256">**Aplicación de voz** Seleccione el nombre de uno de ellos en una cola de llamada u operadores automáticos que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="c5c38-256">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="c5c38-257">Cambiar el identificador de autor de la llamada de un usuario para que sea el número de teléfono de la cola de llamada</span><span class="sxs-lookup"><span data-stu-id="c5c38-257">Changing a user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="c5c38-258">Puede proteger la identidad de un usuario cambiando su identificador de llamada para las llamadas salientes a una cola de llamadas en lugar de crear una directiva con el cmdlet **New-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="c5c38-258">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="c5c38-259">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c5c38-259">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="c5c38-260">A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="c5c38-260">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="c5c38-261">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c5c38-261">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="c5c38-262">Puede obtener más información acerca de cómo realizar cambios en la configuración de identificador de autor de la llamada de la organización en el artículo [cómo se puede usar el identificador de autor de la llamada de la organización](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c5c38-262">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="c5c38-263">¿Desea obtener más información?</span><span class="sxs-lookup"><span data-stu-id="c5c38-263">Want to know more?</span></span>

<span data-ttu-id="c5c38-264">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-264">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="c5c38-265">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="c5c38-265">Call queue cmdlets</span></span>

<span data-ttu-id="c5c38-266">Estos son los cmdlets que necesita para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5c38-266">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="c5c38-267">New-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c5c38-267">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [<span data-ttu-id="c5c38-268">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c5c38-268">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [<span data-ttu-id="c5c38-269">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c5c38-269">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [<span data-ttu-id="c5c38-270">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c5c38-270">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="c5c38-271">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5c38-271">More about Windows PowerShell</span></span>

- <span data-ttu-id="c5c38-272">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="c5c38-272">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c5c38-273">Con Windows PowerShell, puede administrar Office 365 y Teams Microsoft mediante un único punto de administración que puede simplificar su trabajo diario, cuando haya varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="c5c38-273">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c5c38-274">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="c5c38-274">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c5c38-275">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c5c38-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="c5c38-276">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="c5c38-276">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="c5c38-277">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre sólo desde el centro de administración de Microsoft Teams como cuando desea realizar cambios en la configuración de muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="c5c38-277">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c5c38-278">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="c5c38-278">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c5c38-279">Administración de Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5c38-279">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="c5c38-280">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5c38-280">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="c5c38-281">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c5c38-281">Related topics</span></span>

[<span data-ttu-id="c5c38-282">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="c5c38-282">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c5c38-283">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="c5c38-283">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="c5c38-284">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="c5c38-284">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c5c38-285">Nueva CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c5c38-285">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
