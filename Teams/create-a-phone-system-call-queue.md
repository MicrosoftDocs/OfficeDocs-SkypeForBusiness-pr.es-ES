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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Aprenda a configurar el sistema telefónico para las colas de llamadas en nube con Microsoft Teams.
ms.openlocfilehash: 0447bf7aa8d935b214dc9db7c9a730d27fbb0b23
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824798"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="20a5a-103">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="20a5a-103">Create a Cloud call queue</span></span>

<span data-ttu-id="20a5a-104">Las colas de llamadas en nube pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="20a5a-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="20a5a-105">Un mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="20a5a-105">A greeting message.</span></span>
- <span data-ttu-id="20a5a-106">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="20a5a-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="20a5a-107">Redireccionamiento de llamadas a agentes de llamadas en listas de distribución habilitadas para correo electrónico y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="20a5a-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="20a5a-108">Establecer distintos parámetros, como el tamaño máximo de la cola, el tiempo de espera y las opciones de administración de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="20a5a-109">Buzón de voz compartido para que las personas que llaman dejen un mensaje para una organización.</span><span class="sxs-lookup"><span data-stu-id="20a5a-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="20a5a-110">No asocia directamente un número de teléfono a una cola de llamadas, sino que el número de teléfono está asociado a una [cuenta de recursos](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="20a5a-111">Una cola de llamadas puede marcarse directamente o tener acceso a la misma mediante una selección en un operador automático.</span><span class="sxs-lookup"><span data-stu-id="20a5a-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="20a5a-112">La persona que llama escucha la música mientras está en espera y la llamada se conecta a los agentes de llamadas con el orden FIFO ( *primero en salir* ).</span><span class="sxs-lookup"><span data-stu-id="20a5a-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="20a5a-113">Todas las llamadas de la cola se envían a los agentes mediante uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="20a5a-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="20a5a-114">Con el enrutamiento del operador, la primera llamada de la cola suena a todos los agentes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="20a5a-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="20a5a-115">Con el enrutamiento en serie, la primera llamada de la cola suena una por una por todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="20a5a-116">Con la operación por turnos, el enrutamiento de las llamadas entrantes está equilibrado, de modo que cada agente de llamadas obtiene el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="20a5a-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20a5a-117">Los agentes de llamadas que estén **desconectados**, que hayan establecido su presencia en **no molestar,** o que hayan decidido no recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="20a5a-118">Solo una notificación de llamada entrante (para la llamada al principio de la cola) a la vez va a los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="20a5a-119">Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="20a5a-120">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="20a5a-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="20a5a-121">Paso 1: introducción</span><span class="sxs-lookup"><span data-stu-id="20a5a-121">Step 1 — Get started</span></span>

<span data-ttu-id="20a5a-122">Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="20a5a-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="20a5a-123">Se necesita una cola de llamadas para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="20a5a-124">Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="20a5a-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="20a5a-125">Cuando asigne un número de teléfono a una cuenta de recursos, ahora puede usar la [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md)del sistema telefónico para el coste.</span><span class="sxs-lookup"><span data-stu-id="20a5a-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="20a5a-126">El sistema telefónico permite números de teléfono en el nivel de la organización para su uso con los servicios de cola de llamadas y los operadores automáticos de bajo costo.</span><span class="sxs-lookup"><span data-stu-id="20a5a-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="20a5a-127">Los números del servicio de enrutamiento directo para colas de llamadas solo se admiten para usuarios y agentes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20a5a-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="20a5a-128">Para redirigir las llamadas a las personas de su organización que están conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="20a5a-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="20a5a-129">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="20a5a-130">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20a5a-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="20a5a-131">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="20a5a-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="20a5a-132">Para obtener más información sobre los planes de llamadas de Office 365, consulte planes de llamadas y [sistemas telefónicos](calling-plan-landing-page.md) y [planes de llamadas para Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="20a5a-133">Solo puede asignar colas de llamadas en la nube números de teléfono de pago y gratuitos que recibió en el **centro de administración de Microsoft Teams** o transferidos desde otro proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="20a5a-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="20a5a-134">Para los números de servicio gratuitos se requieren créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="20a5a-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20a5a-135">Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="20a5a-136">Los siguientes clientes son compatibles con los agentes de llamadas asociados a una cola de llamadas en la nube:</span><span class="sxs-lookup"><span data-stu-id="20a5a-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="20a5a-137">Cliente de escritorio de Skype empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="20a5a-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="20a5a-138">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="20a5a-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="20a5a-139">Todos los modelos de teléfono IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20a5a-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="20a5a-140">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="20a5a-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="20a5a-141">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="20a5a-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="20a5a-142">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="20a5a-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="20a5a-143">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="20a5a-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="20a5a-144">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="20a5a-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="20a5a-145">Cliente de Windows de Microsoft Teams (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="20a5a-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="20a5a-146">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="20a5a-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="20a5a-147">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="20a5a-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="20a5a-148">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="20a5a-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="20a5a-149">Las colas de llamadas que tengan asignado un número de enrutamiento directo no serán compatibles con los clientes de Skype empresarial, los clientes de Lync ni los teléfonos IP de Skype empresarial como agentes.</span><span class="sxs-lookup"><span data-stu-id="20a5a-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="20a5a-150">Paso 2: obtener o transferir números de teléfono de pago o gratuitos</span><span class="sxs-lookup"><span data-stu-id="20a5a-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="20a5a-151">Antes de crear y configurar las colas de llamadas, debes obtener o transferir tus números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="20a5a-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="20a5a-152">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="20a5a-153">Después de recibir los números**de teléfono de**pago o gratuitos, aparecerán en > **los números de teléfono**del centro > de **Administración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="20a5a-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="20a5a-154">Los números gratuitos se mostrarán con un **tipo** de servicio de número **(gratuito)**.</span><span class="sxs-lookup"><span data-stu-id="20a5a-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="20a5a-155">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio.</span><span class="sxs-lookup"><span data-stu-id="20a5a-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="20a5a-156">En su lugar, vaya a [administrar números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="20a5a-157">Cuando configure varios operadores automáticos, normalmente asignaría un número de teléfono a la cuenta de recursos del operador automático principal.</span><span class="sxs-lookup"><span data-stu-id="20a5a-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="20a5a-158">Las cuentas de recursos asociadas a los operadores automáticos anidados o a las colas de llamadas a menudo no necesitan números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="20a5a-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="20a5a-159">Ese operador automático puede dirigir a las personas que llaman a las colas de llamadas o a los operadores automáticos anidados incluso si no tienen un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="20a5a-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="20a5a-160">En esos casos, puede crear todos los operadores automáticos y colas de llamadas en el sistema sin asignar opciones de marcado y, después, editar la configuración más adelante.</span><span class="sxs-lookup"><span data-stu-id="20a5a-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="20a5a-161">Debe existir una cola de llamadas o un operador automático para establecerla como una opción de menú.</span><span class="sxs-lookup"><span data-stu-id="20a5a-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="20a5a-162">Paso 3: crear una cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="20a5a-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="20a5a-163">Cada cola de llamadas debe tener una cuenta de [recursos](manage-resource-accounts.md)asociada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="20a5a-164">Debe crear primero la cuenta de recursos y, a continuación, asociarla a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="20a5a-165">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20a5a-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="20a5a-166">En el **centro de administración de Microsoft Teams**,**colas de llamadas**de **voz** > y, a continuación, haga clic en **+ Agregar nuevo**:</span><span class="sxs-lookup"><span data-stu-id="20a5a-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="20a5a-167">Establecer el nombre para mostrar y la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="20a5a-167">Set the display name and resource account</span></span>

![Captura de pantalla de una nueva cola de llamadas con llamadas numeradas](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="20a5a-169">![El icono del número 1 hace referencia a una llamada en el](media/teamscallout1.png)
**nombre** de la captura de pantalla anterior escriba un nombre descriptivo para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-169">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="20a5a-170">Este nombre es obligatorio y puede contener hasta 64 caracteres, incluidos los espacios.</span><span class="sxs-lookup"><span data-stu-id="20a5a-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="20a5a-171">Este nombre se muestra en la notificación de la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="20a5a-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="20a5a-172">![Icono del número 2, que hace referencia a una llamada en la](media/teamscallout2.png)
captura de pantalla anterior**Agregar cuentas** Seleccione una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-172">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="20a5a-173">Todas las colas de llamadas deben tener una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-173">All call queues are required to have a resource account.</span></span> <span data-ttu-id="20a5a-174">No es necesario que las cuentas de recursos tengan un número de teléfono gratuito o gratuito.</span><span class="sxs-lookup"><span data-stu-id="20a5a-174">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="20a5a-175">Si no hay ninguna lista, obtenga números de servicio y asígnelos a una cuenta de recursos antes de crear la cola de llamadas, como se describe anteriormente.</span><span class="sxs-lookup"><span data-stu-id="20a5a-175">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="20a5a-176">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-176">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="20a5a-177">Consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) para obtener información específica sobre cómo asignar un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="20a5a-177">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="20a5a-178">Si quiere o necesita asignar un **dominio** , lo asignaría a la cuenta de recursos para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-178">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="20a5a-179">Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera</span><span class="sxs-lookup"><span data-stu-id="20a5a-179">Set the greeting and music played while on hold</span></span>

![captura de pantalla de las opciones de saludo y música con llamadas numeradas](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="20a5a-181">![El icono del número 1, hace referencia a una llamada en la](media/teamscallout1.png)
captura de pantalla anterior,**saludo** el saludo opcional que se reproduce para las personas que llaman al número de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-181">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="20a5a-182">Puede cargar un archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="20a5a-182">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="20a5a-183">![Icono del número 2, que hace referencia a una llamada en la](media/teamscallout2.png)
captura de pantalla anterior**música en espera** puede usar la música predeterminada en espera con la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-183">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="20a5a-184">También puede cargar un archivo de audio en formato. wav, MP3 o. WMA para usarlo como música personalizada en espera.</span><span class="sxs-lookup"><span data-stu-id="20a5a-184">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="20a5a-185">Selecciona las opciones de contestador automático</span><span class="sxs-lookup"><span data-stu-id="20a5a-185">Select the call answering options</span></span>

![Captura de pantalla de las opciones de contestador automático](media/5d249515-d532-4af2-90da-011404028b89.png) 

<span data-ttu-id="20a5a-187">![El icono del número 1, hace referencia a una llamada en la](media/teamscallout1.png)
captura de pantalla anterior de los**agentes y grupos** para agregar agentes individuales directamente, sin agregarlos a un grupo, haga clic en **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="20a5a-187">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="20a5a-188">Coloca agentes individuales en el orden en que quieras que reciban la llamada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-188">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="20a5a-189">Puedes añadir hasta 20 agentes individuales (para añadir más de 20, ponerlos en un grupo).</span><span class="sxs-lookup"><span data-stu-id="20a5a-189">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="20a5a-190">Las llamadas se enrutan primero a los agentes individuales y luego a los agentes en grupos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-190">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="20a5a-191">Puede seleccionar hasta 200 agentes de llamadas que pertenecen a cualquiera de las siguientes listas o grupos de correo:</span><span class="sxs-lookup"><span data-stu-id="20a5a-191">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="20a5a-192">Grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="20a5a-192">Office 365 group</span></span>
- <span data-ttu-id="20a5a-193">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="20a5a-193">Security group</span></span>
- <span data-ttu-id="20a5a-194">Lista de distribución</span><span class="sxs-lookup"><span data-stu-id="20a5a-194">Distribution list</span></span>

<span data-ttu-id="20a5a-195">Los agentes de llamadas seleccionados deben ser:</span><span class="sxs-lookup"><span data-stu-id="20a5a-195">Call agents selected must be:</span></span> 

- <span data-ttu-id="20a5a-196">Usuarios en línea con una licencia de sistema telefónico y la telefonía IP empresarial habilitada</span><span class="sxs-lookup"><span data-stu-id="20a5a-196">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="20a5a-197">Usuarios en línea con un plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="20a5a-197">Online users with a Calling Plan</span></span>
- <span data-ttu-id="20a5a-198">Usuarios locales de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="20a5a-198">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="20a5a-199">Esto también se aplica si desea redirigir las llamadas a las personas de su organización que están conectadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-199">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="20a5a-200">Estas personas deben tener una licencia de **sistema telefónico** y la telefonía IP empresarial habilitada **o** tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-200">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="20a5a-201">Para obtener más información, vea [asignar licencias de Skype empresarial](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [asignar licencias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [el plan de llamadas es adecuado para usted](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) .</span><span class="sxs-lookup"><span data-stu-id="20a5a-201">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="20a5a-202">Para habilitar un agente para telefonía IP empresarial, puede usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20a5a-202">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="20a5a-203">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="20a5a-203">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="20a5a-204">Usuarios con una licencia de **sistema telefónico** o un plan de llamadas que se agregan a un grupo de Office 365. una lista de distribución habilitada para correo electrónico. o un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="20a5a-204">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="20a5a-205">Al agregar un agente en una lista de distribución o un grupo de seguridad como agente de la cola de llamadas, puede demorar hasta tres horas en llegar a la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-205">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="20a5a-206">Una lista de distribución o un grupo de seguridad recién creados puede demorar 48 horas en estar disponible para usarse con las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-206">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="20a5a-207">Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="20a5a-207">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="20a5a-208">Si los agentes usan la aplicación Microsoft Teams para las llamadas de la cola de llamadas, deben estar en modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="20a5a-208">If your agents are using the Microsoft Teams App for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="20a5a-209">![Icono del número 2, que hace referencia a una llamada en el](media/teamscallout2.png)
**método de enrutamiento** de captura de pantalla anterior, puede elegir entre **operador**, **serie**o **Round Robin** como método de distribución.</span><span class="sxs-lookup"><span data-stu-id="20a5a-209">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="20a5a-210">Todas las colas de llamadas nuevas y existentes tienen el enrutamiento de operador seleccionado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-210">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="20a5a-211">Cuando se usa el enrutamiento del operador, la primera llamada en la cola llama a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="20a5a-211">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="20a5a-212">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-212">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="20a5a-213">El **enrutamiento del operador** hace que la primera llamada de la cola suene a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="20a5a-213">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="20a5a-214">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-214">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="20a5a-215">El **enrutamiento serie** llama a todos los agentes de llamadas de uno en uno, desde el principio de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-215">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="20a5a-216">Los agentes no se pueden pedir dentro de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-216">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="20a5a-217">Si un agente descarta o no atiende una llamada, la llamada sonará al próximo agente y probará con todos los agentes hasta que se seleccione o agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="20a5a-217">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
  > [!NOTE]
  > <span data-ttu-id="20a5a-218">Con el enrutamiento en serie, en el caso de agentes que estén **desconectados** o que hayan establecido su presencia en **no molestar**, la llamada se redirigirá a esos usuarios y no podrá conectarse al siguiente agente de la lista de agentes.</span><span class="sxs-lookup"><span data-stu-id="20a5a-218">With Serial routing, for agents who are **Offline** or have set their presence to **Do not Disturb**, the call will be routed to those users and fail to connect unavailable user, the routing to the next agent in the agent list.</span></span> <span data-ttu-id="20a5a-219">Esto no sucede si el agente ha **optado** por no recibir llamadas de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-219">This is not the case if the agent has **opted out** of getting calls from the call queue.</span></span> <span data-ttu-id="20a5a-220">Para reducir el intervalo de tiempo que se puede disminuir la llamada se dirige al siguiente agente de la línea.</span><span class="sxs-lookup"><span data-stu-id="20a5a-220">To reduce the time interval the call routes to next agent in line, Agent Alert time can be decreased.</span></span>
- <span data-ttu-id="20a5a-221">El enrutamiento **Round Robin** de equilibra las llamadas entrantes para que cada agente de llamadas obtenga el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="20a5a-221">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="20a5a-222">Esto puede ser conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-222">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="20a5a-223">Seleccionar una opción de cancelación de la suscripción</span><span class="sxs-lookup"><span data-stu-id="20a5a-223">Select an agent opt-out option</span></span>

![Captura de pantalla de las opciones de cancelación del agente, con llamadas numeradas](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="20a5a-225">![El icono del número 1 hace referencia a una llamada en el agente](media/teamscallout1.png)
de captura de pantalla anterior que**puede optar por recibir llamadas** puede optar por permitir que los agentes de la cola de llamadas no puedan tomar llamadas de una cola determinada habilitando esta opción.</span><span class="sxs-lookup"><span data-stu-id="20a5a-225">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="20a5a-226">Al habilitar esta opción, todos los agentes de esta cola iniciarán o dejarán de recibir llamadas de esta cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-226">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="20a5a-227">Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).</span><span class="sxs-lookup"><span data-stu-id="20a5a-227">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="20a5a-228">Para acceder a la opción de cancelación de la suscripción, los agentes pueden:</span><span class="sxs-lookup"><span data-stu-id="20a5a-228">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="20a5a-229">Abra **Opciones** en el cliente de Skype for Business de su escritorio.</span><span class="sxs-lookup"><span data-stu-id="20a5a-229">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="20a5a-230">En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.</span><span class="sxs-lookup"><span data-stu-id="20a5a-230">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="20a5a-231">En la página Configuración de usuario, haga clic en **colas de llamadas**y, a continuación, desactive las casillas para anular las colas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-231">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20a5a-232">Los agentes que usen aplicaciones o extremos que no sean de Skype empresarial pueden acceder a la opción de cancelación de la suscripción en [https://aka.ms/cqsettings](https://aka.ms/cqsettings)el portal de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="20a5a-232">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="20a5a-233">Si los agentes se encuentran en clientes de escritorio de Microsoft Teams, pueden dejar de participar usando la configuración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="20a5a-233">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="20a5a-234">![Icono del número 2, que hace referencia a una llamada en la](media/teamscallout2.png)
**configuración de alerta del agente** de captura de pantalla anterior</span><span class="sxs-lookup"><span data-stu-id="20a5a-234">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="20a5a-235">Esto define la duración de un agente de notificación de una llamada antes de que los métodos de enrutamiento de serie o de turnos pasen al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="20a5a-235">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="20a5a-236">La configuración predeterminada es de 30 segundos, pero se puede establecer hasta 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-236">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="20a5a-237">Establecer las opciones de desbordamiento de llamadas y administración de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="20a5a-237">Set the call overflow and timeout handling options</span></span>

![Captura de pantalla de las opciones de control de desbordamiento con llamadas numeradas](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="20a5a-239">![Icono del número 1, que hace referencia a una llamada en la](media/teamscallout1.png)
captura de pantalla anterior**llamadas máximas en la cola** use esta configuración para establecer las llamadas máximas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="20a5a-239">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="20a5a-240">El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="20a5a-240">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="20a5a-241">Cuando se alcanza este límite, la llamada se maneja de la forma que estableces en la configuración **cuando se alcanza el número máximo de llamadas** , a continuación.</span><span class="sxs-lookup"><span data-stu-id="20a5a-241">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="20a5a-242">![Icono del número 2, que hace referencia a una llamada en la](media/teamscallout2.png)
captura de pantalla anterior**cuando se alcanza el número máximo de llamadas** cuando la cola de llamadas alcanza su tamaño máximo (establecido mediante las **llamadas máximas en la configuración de la cola** ), puede elegir qué sucede con las llamadas entrantes nuevas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-242">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="20a5a-243">**Desconectar** La llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="20a5a-243">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="20a5a-244">**Redirigir a** Si elige esta opción, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="20a5a-244">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="20a5a-245">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-245">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="20a5a-246">Puedes configurarlo para que la persona que llama pueda enviarse al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="20a5a-246">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="20a5a-247">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="20a5a-247">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="20a5a-248">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-248">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="20a5a-249">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="20a5a-249">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

<span data-ttu-id="20a5a-250">![El icono del número 3 hace referencia a una llamada en la captura](media/teamscallout3.png)
de pantalla anterior**tiempo de espera de llamada: tiempo de espera máximo** también puede decidir cuánto tiempo puede estar en espera una llamada en la cola antes de que se agote el tiempo de espera y que deba redirigirse o desconectarse.</span><span class="sxs-lookup"><span data-stu-id="20a5a-250">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="20a5a-251">El lugar donde se redirige se basa en el modo en que se establece la configuración **cuando la llamada supera el tiempo de espera** .</span><span class="sxs-lookup"><span data-stu-id="20a5a-251">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="20a5a-252">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-252">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="20a5a-253">El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="20a5a-253">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="20a5a-254">Esto permite manipular el flujo de llamadas con una granularidad más fina.</span><span class="sxs-lookup"><span data-stu-id="20a5a-254">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="20a5a-255">Por ejemplo, puede especificar que las llamadas no contestadas por un agente en un plazo de 30 segundos vayan a un operador automático de búsqueda de directorios.</span><span class="sxs-lookup"><span data-stu-id="20a5a-255">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="20a5a-256">![Icono del número 4, que hace referencia a una llamada en la](media/teamscallout4.png)
captura de pantalla anterior**cuando la llamada supera el tiempo** de espera cuando la llamada alcanza el límite establecido en el valor de **tiempo de espera de una llamada en la cola** , puede elegir qué sucede con la llamada:</span><span class="sxs-lookup"><span data-stu-id="20a5a-256">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="20a5a-257">**Desconectar** La llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="20a5a-257">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="20a5a-258">**Redirigir esta llamada a** Si elige esta opción, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="20a5a-258">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="20a5a-259">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o para tener planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-259">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="20a5a-260">Para configurarlo para que la persona que llama pueda enviarse al buzón de voz, seleccione a una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="20a5a-260">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="20a5a-261">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="20a5a-261">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="20a5a-262">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada con una cola de llamadas o un operador automático que ya haya creado.</span><span class="sxs-lookup"><span data-stu-id="20a5a-262">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="20a5a-263">Cambiar la identificación de llamadas para llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="20a5a-263">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="20a5a-264">Para proteger la identidad de un agente de llamada, cambie la identificación de llamadas para llamadas salientes a una cola de llamadas, operador automático o cualquier número de servicio con el cmdlet **New-CsCallingLineIdentity** como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20a5a-264">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="20a5a-265">A continuación, aplique la Directiva al usuario con el cmdlet **Grant-CallingLineIdentity** como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20a5a-265">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="20a5a-266">Para obtener más información, consulte [cómo se puede usar la identificación de llamadas en su organización](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="20a5a-266">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="20a5a-267">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="20a5a-267">Call queue cmdlets</span></span>

<span data-ttu-id="20a5a-268">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-268">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="20a5a-269">Estos son los cmdlets que usas para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-269">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="20a5a-270">Nuevo: CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20a5a-270">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="20a5a-271">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20a5a-271">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="20a5a-272">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20a5a-272">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="20a5a-273">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20a5a-273">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="20a5a-274">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20a5a-274">More about Windows PowerShell</span></span>

- <span data-ttu-id="20a5a-275">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="20a5a-275">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="20a5a-276">Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración.</span><span class="sxs-lookup"><span data-stu-id="20a5a-276">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="20a5a-277">Puede simplificar su trabajo diario cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="20a5a-277">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="20a5a-278">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="20a5a-278">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="20a5a-279">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="20a5a-279">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="20a5a-280">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="20a5a-280">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="20a5a-281">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en el centro de administración de Microsoft Teams cuando realiza cambios para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="20a5a-281">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="20a5a-282">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="20a5a-282">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="20a5a-283">Administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20a5a-283">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="20a5a-284">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20a5a-284">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="20a5a-285">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="20a5a-285">Related topics</span></span>

[<span data-ttu-id="20a5a-286">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="20a5a-286">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="20a5a-287">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="20a5a-287">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="20a5a-288">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="20a5a-288">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="20a5a-289">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="20a5a-289">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
