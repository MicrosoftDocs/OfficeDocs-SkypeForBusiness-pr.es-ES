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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Aprenda a configurar el sistema telefónico para las colas de llamadas en nube con Microsoft Teams.
ms.openlocfilehash: fc7cc9558036d30d388a279ac155fe6382e611a8
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925101"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="d84f5-103">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="d84f5-103">Create a Cloud call queue</span></span>

<span data-ttu-id="d84f5-104">Las colas de llamadas en nube pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="d84f5-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="d84f5-105">Un mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="d84f5-105">A greeting message.</span></span>
- <span data-ttu-id="d84f5-106">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="d84f5-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="d84f5-107">Redireccionamiento de llamadas a agentes de llamadas en listas de distribución habilitadas para correo electrónico y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d84f5-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="d84f5-108">Establecer distintos parámetros, como el tamaño máximo de la cola, el tiempo de espera y las opciones de administración de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="d84f5-109">Asociaría un número de teléfono a una cola de llamadas con una [cuenta de recursos](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-109">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="d84f5-110">Una cola de llamadas puede marcarse directamente o tener acceso a la misma mediante una selección en un operador automático.</span><span class="sxs-lookup"><span data-stu-id="d84f5-110">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="d84f5-111">La persona que llama escucha la música mientras está en espera y la llamada se conecta a los agentes de llamadas con el orden FIFO ( *primero en salir* ).</span><span class="sxs-lookup"><span data-stu-id="d84f5-111">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="d84f5-112">Todas las llamadas de la cola se envían a los agentes mediante uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="d84f5-112">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="d84f5-113">Con el enrutamiento del operador, la primera llamada de la cola suena a todos los agentes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d84f5-113">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="d84f5-114">Con el enrutamiento en serie, la primera llamada de la cola suena una por una por todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-114">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="d84f5-115">Con la operación por turnos, el enrutamiento de las llamadas entrantes está equilibrado, de modo que cada agente de llamadas obtiene el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="d84f5-115">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d84f5-116">Los agentes de llamadas que estén **desconectados**, que hayan establecido su presencia en **no molestar,** o que hayan decidido no recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-116">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="d84f5-117">Solo una notificación de llamada entrante (para la llamada al principio de la cola) a la vez va a los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-117">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="d84f5-118">Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-118">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="d84f5-119">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="d84f5-119">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="d84f5-120">Paso 1: introducción</span><span class="sxs-lookup"><span data-stu-id="d84f5-120">Step 1 — Get started</span></span>

<span data-ttu-id="d84f5-121">Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="d84f5-121">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="d84f5-122">Se necesita una cola de llamadas para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="d84f5-122">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="d84f5-123">Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="d84f5-123">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="d84f5-124">Cuando asigne un número de teléfono a una cuenta de recursos, ahora puede usar la [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md)del sistema telefónico para el coste.</span><span class="sxs-lookup"><span data-stu-id="d84f5-124">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="d84f5-125">El sistema telefónico permite números de teléfono en el nivel de la organización para su uso con los servicios de cola de llamadas y los operadores automáticos de bajo costo.</span><span class="sxs-lookup"><span data-stu-id="d84f5-125">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="d84f5-126">Los números del servicio de enrutamiento directo para colas de llamadas solo se admiten para usuarios y agentes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d84f5-126">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="d84f5-127">Para redirigir las llamadas a las personas de su organización que están conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d84f5-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="d84f5-128">Consulte [asignar licencias de Skype empresarial](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-128">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="d84f5-129">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d84f5-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d84f5-130">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d84f5-130">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="d84f5-131">Para obtener más información sobre los planes de llamadas de Office 365, consulte planes de llamadas y [sistemas telefónicos](calling-plan-landing-page.md) y [planes de llamadas para Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-131">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="d84f5-132">Solo puede asignar colas de llamadas en la nube números de teléfono de pago y gratuitos que recibió en el **centro de administración de Microsoft Teams** o transferidos desde otro proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="d84f5-132">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="d84f5-133">Para los números de servicio gratuitos se requieren créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="d84f5-133">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d84f5-134">Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.</span><span class="sxs-lookup"><span data-stu-id="d84f5-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="d84f5-135">Los siguientes clientes son compatibles con los agentes de llamadas asociados a una cola de llamadas en la nube:</span><span class="sxs-lookup"><span data-stu-id="d84f5-135">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="d84f5-136">Cliente de escritorio de Skype empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="d84f5-136">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="d84f5-137">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="d84f5-137">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="d84f5-138">Todos los modelos de teléfono IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d84f5-138">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="d84f5-139">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="d84f5-139">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="d84f5-140">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="d84f5-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="d84f5-141">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="d84f5-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="d84f5-142">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="d84f5-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="d84f5-143">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="d84f5-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="d84f5-144">Cliente de Windows de Microsoft Teams (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="d84f5-144">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="d84f5-145">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="d84f5-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="d84f5-146">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="d84f5-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="d84f5-147">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="d84f5-147">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="d84f5-148">Las colas de llamadas que tengan asignado un número de enrutamiento directo no serán compatibles con los clientes de Skype empresarial, los clientes de Lync ni los teléfonos IP de Skype empresarial como agentes.</span><span class="sxs-lookup"><span data-stu-id="d84f5-148">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="d84f5-149">Paso 2: obtener o transferir números de teléfono de pago o gratuitos</span><span class="sxs-lookup"><span data-stu-id="d84f5-149">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="d84f5-150">Antes de crear y configurar las colas de llamadas, debes obtener o transferir tus números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="d84f5-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="d84f5-151">Una vez que obtenga los números de teléfono de pago o gratuitos, aparecerán en el centro >  > de **Administración de Microsoft Teams\*\*\*\*números de teléfono**de**voz** > del**portal heredados**, y el **tipo de número** aparecerá como **Servicio:** gratuito.</span><span class="sxs-lookup"><span data-stu-id="d84f5-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="d84f5-152">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d84f5-153">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio.</span><span class="sxs-lookup"><span data-stu-id="d84f5-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="d84f5-154">En su lugar, vaya a [administrar números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d84f5-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="d84f5-155">Al configurar varios operadores automáticos, solo puede asignar un número de teléfono a la cuenta de recursos del operador automático principal, que puede dirigir a las personas que llaman a las colas de llamadas o a los operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="d84f5-155">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="d84f5-156">En esos casos, creará todos los operadores automáticos y las colas de llamadas en el sistema sin asignar opciones de marcado y, después, podrá editar la configuración más adelante.</span><span class="sxs-lookup"><span data-stu-id="d84f5-156">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="d84f5-157">Esto es necesario porque no tienes permiso para crear una opción de vinculación a una cola de llamadas o a un operador automático que aún no exista.</span><span class="sxs-lookup"><span data-stu-id="d84f5-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="d84f5-158">Paso 3: crear una nueva cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="d84f5-158">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="d84f5-159">Cada cola de llamadas debe tener una cuenta de [recursos](manage-resource-accounts.md)asociada.</span><span class="sxs-lookup"><span data-stu-id="d84f5-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="d84f5-160">Debe crear primero la cuenta de recursos y, a continuación, asociarla a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d84f5-161">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d84f5-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d84f5-162">En el **centro de administración de Microsoft Teams**,**colas de llamadas**de **voz** > y, a continuación, haga clic en **+ Agregar nuevo**:</span><span class="sxs-lookup"><span data-stu-id="d84f5-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="d84f5-163">Establecer el nombre para mostrar de la cola de llamadas y la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="d84f5-163">Set the call queue display name and resource account</span></span>

![Captura de pantalla de una nueva cola de llamadas con llamadas numeradas](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="d84f5-165">![Icono del número 1, que hace referencia a una llamada en el](media/sfbcallout1.png)
**nombre** de captura de pantalla anterior escriba un nombre descriptivo para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="d84f5-166">Este nombre es obligatorio y puede contener hasta 64 caracteres, incluidos los espacios.</span><span class="sxs-lookup"><span data-stu-id="d84f5-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="d84f5-167">Este nombre se muestra en la notificación de la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="d84f5-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="d84f5-169">**Agregar cuentas** Seleccione una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="d84f5-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="d84f5-170">La cuenta de recursos puede estar asociada o no a un número de teléfono gratuito de servicio o a un número de teléfono gratuito para la cola de llamadas, pero cada cola de llamadas requiere una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="d84f5-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="d84f5-171">Si no hay ninguna lista, debe obtener números de servicio y asignarlos a una cuenta de recursos antes de poder crear esta cola de llamadas, como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d84f5-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="d84f5-172">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="d84f5-173">Puede crear una cuenta de recursos como se describe en [administrar cuentas de recursos en Teams](manage-resource-accounts.md) si desea que la cola de llamadas tenga un número de teléfono asociado.</span><span class="sxs-lookup"><span data-stu-id="d84f5-173">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="d84f5-174">Si quiere o necesita asignar un **dominio** , lo puede asignar a la cuenta de recursos de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="d84f5-175">Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera</span><span class="sxs-lookup"><span data-stu-id="d84f5-175">Set the greeting and music played while on hold</span></span>

![captura de pantalla de las opciones de saludo y música con llamadas numeradas](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="d84f5-178">**Saludo**: este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="d84f5-178">**Greeting** is optional.</span></span> <span data-ttu-id="d84f5-179">Este es el saludo que se reproduce para las personas que llaman al número de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="d84f5-180">Puede cargar un archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="d84f5-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="d84f5-182">**Música en espera** Puede usar la música predeterminada en espera proporcionada con la cola de llamadas, o bien puede cargar un archivo de audio en formato. wav, MP3 o. WMA para usarlo como música personalizada en espera.</span><span class="sxs-lookup"><span data-stu-id="d84f5-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="d84f5-183">Selecciona las opciones de contestador automático</span><span class="sxs-lookup"><span data-stu-id="d84f5-183">Select the call answering options</span></span>

![Captura de pantalla de las opciones de contestador automático con llamadas numeradas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="d84f5-186">Puede seleccionar hasta 200 agentes de llamadas que pertenecen a cualquiera de las siguientes listas o grupos de correo:</span><span class="sxs-lookup"><span data-stu-id="d84f5-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="d84f5-187">Grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="d84f5-187">Office 365 group</span></span>
- <span data-ttu-id="d84f5-188">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="d84f5-188">Security group</span></span>
- <span data-ttu-id="d84f5-189">Lista de distribución</span><span class="sxs-lookup"><span data-stu-id="d84f5-189">Distribution list</span></span>

<span data-ttu-id="d84f5-190">Los agentes de llamadas seleccionados deben ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d84f5-190">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="d84f5-191">Usuarios en línea con una licencia de sistema telefónico y la telefonía IP empresarial habilitada</span><span class="sxs-lookup"><span data-stu-id="d84f5-191">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="d84f5-192">Usuarios en línea con un plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="d84f5-192">Online users with a  Calling Plan</span></span>
- <span data-ttu-id="d84f5-193">Usuarios locales de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d84f5-193">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="d84f5-194">Esto también se aplica si desea redirigir las llamadas a las personas de su organización que están conectadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-194">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="d84f5-195">Estas personas deben tener una licencia de **sistema telefónico** y la telefonía IP empresarial habilitada **o** tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-195">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="d84f5-196">Para obtener más información, vea [asignar licencias de Skype empresarial](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [asignar licencias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [el plan de llamadas es adecuado para usted](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) .</span><span class="sxs-lookup"><span data-stu-id="d84f5-196">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="d84f5-197">Para habilitar un agente para telefonía IP empresarial, puede usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d84f5-197">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d84f5-198">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d84f5-198">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="d84f5-199">Usuarios con una licencia de **sistema telefónico** o un plan de llamadas que se agregan a un grupo de Office 365. una lista de distribución habilitada para correo electrónico. o un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d84f5-199">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="d84f5-200">Puede demorar hasta tres horas en un agente recién agregado de una lista de distribución o un grupo de seguridad para empezar a recibir llamadas de una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-200">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="d84f5-201">Una lista de distribución o un grupo de seguridad recién creados puede demorar 48 horas en estar disponible para usarse con las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-201">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="d84f5-202">Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="d84f5-202">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="d84f5-203">Si los agentes usan la aplicación Microsoft Teams para realizar llamadas en la cola de llamadas, deben estar en modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d84f5-203">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![Captura de pantalla del panel agregar agentes de llamadas](media/skype-for-business-add-agents-to-call-queue.png)

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="d84f5-206">**Método de enrutamiento** Puede elegir entre **operador**, **serie**o **Round Robin** para el método de distribución de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-206">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="d84f5-207">De manera predeterminada, todas las colas de llamadas nuevas y existentes tienen un enrutamiento a operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d84f5-207">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="d84f5-208">Cuando se usa el enrutamiento del operador, la primera llamada en la cola llama a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d84f5-208">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="d84f5-209">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="d84f5-209">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="d84f5-210">El **enrutamiento del operador** hace que la primera llamada de la cola suene a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d84f5-210">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="d84f5-211">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="d84f5-211">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="d84f5-212">Las llamadas entrantes de **enrutamiento en serie** son agentes de llamadas de timbre uno por uno, empezando desde el principio de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-212">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="d84f5-213">Los agentes no se pueden pedir dentro de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-213">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="d84f5-214">Si un agente omite o no contesta una llamada, se realizará una llamada al siguiente agente de la lista y se probará con todos los agentes, de uno a uno, hasta que se responda la llamada o se agote el tiempo de espera en la cola.</span><span class="sxs-lookup"><span data-stu-id="d84f5-214">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="d84f5-215">El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola.</span><span class="sxs-lookup"><span data-stu-id="d84f5-215">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="d84f5-216">El enrutamiento **Round Robin** de equilibra las llamadas entrantes para que cada agente de llamadas obtenga el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="d84f5-216">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d84f5-217">Esto puede ser conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-217">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="d84f5-218">Seleccionar una opción de cancelación de la suscripción</span><span class="sxs-lookup"><span data-stu-id="d84f5-218">Select an agent opt-out option</span></span>

![Captura de pantalla de las opciones de cancelación del agente, con llamadas numeradas](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="d84f5-221">El **agente puede dejar de recibir llamadas** Habilita esta opción para permitir que los agentes de la cola de llamadas no puedan tomar llamadas de una cola en particular.</span><span class="sxs-lookup"><span data-stu-id="d84f5-221">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="d84f5-222">Al habilitar esta opción, todos los agentes de esta cola iniciarán o dejarán de recibir llamadas de esta cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-222">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="d84f5-223">Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).</span><span class="sxs-lookup"><span data-stu-id="d84f5-223">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="d84f5-224">Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d84f5-224">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="d84f5-225">Abra **Opciones** en el cliente de Skype for Business de su escritorio.</span><span class="sxs-lookup"><span data-stu-id="d84f5-225">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="d84f5-226">En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.</span><span class="sxs-lookup"><span data-stu-id="d84f5-226">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="d84f5-227">En la página Configuración de usuario, haga clic en **colas de llamadas**y, a continuación, desactive las casillas de las colas para las que desee optar.</span><span class="sxs-lookup"><span data-stu-id="d84f5-227">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d84f5-228">Los agentes que usen aplicaciones o extremos que no sean de Skype empresarial pueden acceder a la opción de cancelación de la suscripción en [https://aka.ms/cqsettings](https://aka.ms/cqsettings)el portal de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="d84f5-228">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="d84f5-229">![Icono del número 2, que hace referencia a una llamada en la](media/sfbcallout2.png)
**configuración de alerta del agente** de captura de pantalla anterior</span><span class="sxs-lookup"><span data-stu-id="d84f5-229">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="d84f5-230">Esto define la duración de un agente de notificación de una llamada antes de que los métodos de enrutamiento de serie o de turnos pasen al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="d84f5-230">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="d84f5-231">La configuración predeterminada es de 30 segundos, pero se puede establecer hasta 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="d84f5-231">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="d84f5-232">Establecer las opciones de desbordamiento de llamadas y administración de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="d84f5-232">Set the call overflow and timeout handling options</span></span>

![Captura de pantalla de las opciones de control de desbordamiento con llamadas numeradas](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="d84f5-235">**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d84f5-235">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="d84f5-236">El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="d84f5-236">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="d84f5-237">Cuando se alcanza este límite, la llamada se maneja de la forma que estableces en la configuración **cuando se alcanza el número máximo de llamadas** , a continuación.</span><span class="sxs-lookup"><span data-stu-id="d84f5-237">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="d84f5-239">**Cuando se alcanza el número máximo de llamadas** Cuando la cola de llamadas alcanza su tamaño máximo (establecido mediante las **llamadas máximas en la configuración de la cola** ), puede elegir qué sucede con las llamadas entrantes nuevas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-239">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="d84f5-240">**Desconectar** La llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="d84f5-240">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="d84f5-241">**Redirigir a** Si elige esta opción, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d84f5-241">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="d84f5-242">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-242">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="d84f5-243">Puedes configurarlo para que la persona que llama pueda enviarse al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="d84f5-243">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="d84f5-244">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="d84f5-244">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="d84f5-245">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-245">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="d84f5-246">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="d84f5-246">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout3.png)

<span data-ttu-id="d84f5-248">**Tiempo de espera de llamada: tiempo de espera máximo** También puede decidir cuánto tiempo puede estar en espera una llamada en la cola antes de que se agote el tiempo de espera y deba redirigirse o desconectarse.</span><span class="sxs-lookup"><span data-stu-id="d84f5-248">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="d84f5-249">El lugar donde se redirige se basa en el modo en que se establece la configuración **cuando la llamada supera el tiempo de espera** .</span><span class="sxs-lookup"><span data-stu-id="d84f5-249">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="d84f5-250">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="d84f5-250">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="d84f5-251">El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="d84f5-251">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="d84f5-252">Esto permite manipular el flujo de llamadas con una granularidad más fina.</span><span class="sxs-lookup"><span data-stu-id="d84f5-252">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="d84f5-253">Por ejemplo, puede especificar que las llamadas no contestadas por un agente en un plazo de 30 segundos vayan a un operador automático de búsqueda de directorios.</span><span class="sxs-lookup"><span data-stu-id="d84f5-253">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

<span data-ttu-id="d84f5-255">**Cuando la llamada supera el tiempo de salida** Cuando la llamada alcanza el límite establecido en el valor de **tiempo que puede esperar una llamada en la cola** , puede elegir lo que le sucede a esta llamada:</span><span class="sxs-lookup"><span data-stu-id="d84f5-255">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="d84f5-256">**Desconectar** La llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="d84f5-256">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="d84f5-257">**Redirigir esta llamada a** Si elige esta opción, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="d84f5-257">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="d84f5-258">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o para tener planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-258">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="d84f5-259">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="d84f5-259">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="d84f5-260">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="d84f5-260">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="d84f5-261">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="d84f5-261">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="d84f5-262">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="d84f5-262">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="d84f5-263">Cambiar la identificación de llamadas de un usuario para las llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="d84f5-263">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="d84f5-264">Puede proteger la identidad de un usuario si cambia su identificador de llamada para llamadas salientes a una cola de llamadas, operador automático o cualquier número de servicio en su lugar con el cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="d84f5-264">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="d84f5-265">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d84f5-265">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="d84f5-266">A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="d84f5-266">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="d84f5-267">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d84f5-267">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="d84f5-268">Puede obtener más información sobre cómo establecer la configuración de identificación de llamadas de su organización en el artículo [cómo se puede usar la identificación de llamadas de su organización](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d84f5-268">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="d84f5-269">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="d84f5-269">Call queue cmdlets</span></span>

<span data-ttu-id="d84f5-270">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-270">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="d84f5-271">Estos son los cmdlets que usas para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-271">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="d84f5-272">Nuevo: CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d84f5-272">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="d84f5-273">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d84f5-273">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="d84f5-274">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d84f5-274">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="d84f5-275">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d84f5-275">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="d84f5-276">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d84f5-276">More about Windows PowerShell</span></span>

- <span data-ttu-id="d84f5-277">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="d84f5-277">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d84f5-278">Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración que puede simplificar su trabajo diario, cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="d84f5-278">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d84f5-279">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d84f5-279">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d84f5-280">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d84f5-280">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="d84f5-281">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="d84f5-281">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="d84f5-282">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en el centro de administración de Microsoft Teams, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="d84f5-282">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d84f5-283">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d84f5-283">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d84f5-284">Administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d84f5-284">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="d84f5-285">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d84f5-285">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="d84f5-286">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d84f5-286">Related topics</span></span>

[<span data-ttu-id="d84f5-287">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="d84f5-287">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d84f5-288">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="d84f5-288">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="d84f5-289">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="d84f5-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="d84f5-290">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d84f5-290">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
