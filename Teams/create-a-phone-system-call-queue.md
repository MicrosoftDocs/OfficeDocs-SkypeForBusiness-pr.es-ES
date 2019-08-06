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
description: Aprenda a configurar el sistema telefónico para las colas de llamadas en nube con Microsoft Teams.
ms.openlocfilehash: 887c92e398487d3e42f9fc560610683008760105
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207186"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="8663b-103">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="8663b-103">Create a Cloud call queue</span></span>

<span data-ttu-id="8663b-104">Las colas de llamadas en nube pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="8663b-104">Cloud call queues can provide:</span></span>
 
- <span data-ttu-id="8663b-105">Un mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="8663b-105">A greeting message.</span></span>
- <span data-ttu-id="8663b-106">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="8663b-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="8663b-107">Redireccionamiento de llamadas a agentes de llamadas en listas de distribución habilitadas para correo electrónico y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8663b-107">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="8663b-108">Configuración diferentes parámetros, como el tamaño máximo de la cola, el tiempo de espera y las opciones de administración de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-108">Settings different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="8663b-109">Cuando alguien llama a un número de teléfono asociado a una cola de llamadas a través de una [cuenta de recursos](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="8663b-109">When someone calls a phone number that is associated with a call queue via a [resource account](manage-resource-accounts.md):</span></span> 
1. <span data-ttu-id="8663b-110">Escuchan un saludo (si hay alguno configurado)</span><span class="sxs-lookup"><span data-stu-id="8663b-110">They  hear a greeting (if any is set up)</span></span> 
2. <span data-ttu-id="8663b-111">La llamada se coloca en la cola para esperar al siguiente agente de llamada disponible.</span><span class="sxs-lookup"><span data-stu-id="8663b-111">Their call is put in the queue to wait for the next available call agent.</span></span> 
 

<span data-ttu-id="8663b-112">La persona que llama escucha la música mientras está en espera y la llamada se conecta a los agentes de llamadas con el orden FIFO ( *primero en salir* ).</span><span class="sxs-lookup"><span data-stu-id="8663b-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>
 
<span data-ttu-id="8663b-113">Todas las llamadas de la cola se envían a los agentes mediante uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="8663b-113">All calls in the queue are sent to agents by one of the following methods:</span></span>
 
- <span data-ttu-id="8663b-114">Con el enrutamiento del operador, la primera llamada de la cola suena a todos los agentes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8663b-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="8663b-115">Con el enrutamiento en serie, la primera llamada de la cola suena una por una por todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="8663b-116">Con la operación por turnos, el enrutamiento de las llamadas entrantes está equilibrado, de modo que cada agente de llamadas obtiene el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="8663b-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8663b-117">Los agentes de llamadas \*\*\*\* que estén desconectados, que hayan establecido su presencia en **no molestar,** o que hayan decidido no recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>
 
- <span data-ttu-id="8663b-118">Solo una notificación de llamada entrante (para la llamada al principio de la cola) a la vez va a los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="8663b-119">Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="8663b-120">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8663b-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="8663b-121">Paso 1: introducción</span><span class="sxs-lookup"><span data-stu-id="8663b-121">Step 1 — Get started</span></span>

<span data-ttu-id="8663b-122">Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="8663b-122">To get started using call queues, it's important to remember a few things:</span></span>
 
- <span data-ttu-id="8663b-123">Se necesita una cola de llamadas para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="8663b-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="8663b-124">Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="8663b-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="8663b-125">Cuando asigne un número de teléfono a una cuenta de recursos, ahora puede usar la [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md)del sistema telefónico para el coste.</span><span class="sxs-lookup"><span data-stu-id="8663b-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="8663b-126">El sistema telefónico permite números de teléfono en el nivel de la organización para su uso con los servicios de cola de llamadas y los operadores automáticos de bajo costo.</span><span class="sxs-lookup"><span data-stu-id="8663b-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="8663b-127">Los números del servicio de enrutamiento directo para colas de llamadas solo se admiten para usuarios y agentes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8663b-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="8663b-128">Para redirigir las llamadas a las personas de su organización que están conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8663b-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="8663b-129">Consulte [asignar licencias de Skype empresarial](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="8663b-129">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="8663b-130">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8663b-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8663b-131">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8663b-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
 
- <span data-ttu-id="8663b-132">Para obtener más información sobre los planes de llamadas de Office 365, consulte planes de llamadas y [sistemas telefónicos](calling-plan-landing-page.md) y [planes de llamadas para Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8663b-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="8663b-133">Solo puede asignar colas de llamadas en la nube números de teléfono de pago y gratuitos que recibió en el **centro de administración de Microsoft Teams** o transferidos desde otro proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="8663b-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="8663b-134">Para los números de servicio gratuitos se requieren créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="8663b-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8663b-135">Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.</span><span class="sxs-lookup"><span data-stu-id="8663b-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
 
- <span data-ttu-id="8663b-136">Los siguientes clientes son compatibles con los agentes de llamadas asociados a una cola de llamadas en la nube:</span><span class="sxs-lookup"><span data-stu-id="8663b-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="8663b-137">Cliente de escritorio de Skype empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="8663b-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="8663b-138">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="8663b-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="8663b-139">Todos los modelos de teléfono IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8663b-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="8663b-140">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="8663b-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="8663b-141">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="8663b-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="8663b-142">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="8663b-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="8663b-143">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="8663b-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="8663b-144">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="8663b-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="8663b-145">Cliente de Windows de Microsoft Teams (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="8663b-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="8663b-146">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="8663b-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="8663b-147">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="8663b-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="8663b-148">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="8663b-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="8663b-149">Paso 2: obtener o transferir números de servicio de pago o gratuitos</span><span class="sxs-lookup"><span data-stu-id="8663b-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="8663b-150">Antes de crear y configurar las colas de llamadas, debes obtener o transferir tus números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="8663b-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="8663b-151">Una vez que obtenga los números de teléfono de pago o gratuitos, aparecerán en el **Centro** > de administración de Microsoft Teams**números de teléfono**de**voz** > del**portal** > heredados, y el **tipo de número** aparecerá como **Servicio:** gratuito.</span><span class="sxs-lookup"><span data-stu-id="8663b-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="8663b-152">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8663b-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
 
> [!NOTE]
> <span data-ttu-id="8663b-153">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio.</span><span class="sxs-lookup"><span data-stu-id="8663b-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="8663b-154">En su lugar, vaya a [administrar números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8663b-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="8663b-155">Si está configurando varios operadores automáticos, es posible que solo tenga que asignar un número de teléfono a la cuenta de recursos del operador automático principal, que puede dirigir a las personas que llaman a las colas de llamadas o a los operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="8663b-155">If you are setting up multiple auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="8663b-156">En estas situaciones, debe crear todos los operadores automáticos y las colas de llamadas en el sistema sin asignar opciones de marcado y, después, editar la configuración más adelante.</span><span class="sxs-lookup"><span data-stu-id="8663b-156">In those situations you should create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="8663b-157">Esto es necesario porque no tienes permiso para crear una opción de vinculación a una cola de llamadas o a un operador automático que aún no exista.</span><span class="sxs-lookup"><span data-stu-id="8663b-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>
 
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="8663b-158">Paso 3: crear una nueva cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="8663b-158">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="8663b-159">Cada cola de llamadas debe tener una cuenta de [recursos](manage-resource-accounts.md)asociada.</span><span class="sxs-lookup"><span data-stu-id="8663b-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="8663b-160">Debe crear primero la cuenta de recursos y, a continuación, asociarla a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8663b-161">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8663b-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8663b-162">En el **centro de administración de Microsoft Teams**,**colas de llamadas**de **voz** > y, a continuación, haga clic en **+ Agregar nuevo**:</span><span class="sxs-lookup"><span data-stu-id="8663b-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="8663b-163">Establecer el nombre para mostrar de la cola de llamadas y la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="8663b-163">Set the call queue display name and resource account</span></span>

![captura de pantalla de una nueva cola de llamadas con llamadas numeradas](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="8663b-165">![Icono del número 1, que hace referencia a una llamada en el](media/sfbcallout1.png)
**nombre** de captura de pantalla anterior escriba un nombre descriptivo para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="8663b-166">Este nombre es obligatorio y puede contener hasta 64 caracteres, incluidos los espacios.</span><span class="sxs-lookup"><span data-stu-id="8663b-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="8663b-167">Este nombre se muestra en la notificación de la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="8663b-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="8663b-169">**Agregar cuentas** Seleccione una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="8663b-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="8663b-170">La cuenta de recursos puede estar asociada o no a un número de teléfono gratuito de servicio o a un número de teléfono gratuito para la cola de llamadas, pero cada cola de llamadas requiere una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="8663b-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="8663b-171">Si no hay ninguna lista, debe obtener números de servicio y asignarlos a una cuenta de recursos antes de poder crear esta cola de llamadas, como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8663b-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="8663b-172">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="8663b-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="8663b-173">Tendrá que crear una cuenta de recursos como se describe en [administrar cuentas de recursos en Teams](manage-resource-accounts.md) si desea que la cola de llamadas tenga un número de teléfono asociado.</span><span class="sxs-lookup"><span data-stu-id="8663b-173">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="8663b-174">Si quiere o necesita asignar un **dominio** , lo puede asignar a la cuenta de recursos de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="8663b-175">Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera</span><span class="sxs-lookup"><span data-stu-id="8663b-175">Set the greeting and music played while on hold</span></span>

![captura de pantalla de las opciones de saludo y música con llamadas numeradas](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
 
* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="8663b-178">**Saludo**: este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="8663b-178">**Greeting** is optional.</span></span> <span data-ttu-id="8663b-179">Este es el saludo que se reproduce para las personas que llaman al número de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="8663b-180">Puede cargar un archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="8663b-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="8663b-182">**Música en espera** Puede usar la música predeterminada en espera proporcionada con la cola de llamadas, o bien puede cargar un archivo de audio en formato. wav, MP3 o. WMA para usarlo como música personalizada en espera.</span><span class="sxs-lookup"><span data-stu-id="8663b-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="8663b-183">Selecciona las opciones de contestador automático</span><span class="sxs-lookup"><span data-stu-id="8663b-183">Select the call answering options</span></span>

![captura de pantalla de las opciones de contestador automático con llamadas numeradas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="8663b-186">Puede seleccionar hasta 200 agentes de llamadas que pertenecen a cualquiera de las siguientes listas o grupos de correo:</span><span class="sxs-lookup"><span data-stu-id="8663b-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="8663b-187">Grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="8663b-187">Office 365 group</span></span>
- <span data-ttu-id="8663b-188">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="8663b-188">Security group</span></span>
- <span data-ttu-id="8663b-189">Lista de distribución</span><span class="sxs-lookup"><span data-stu-id="8663b-189">Distribution list</span></span>

<span data-ttu-id="8663b-190">Los agentes de llamadas \*\*\*\* seleccionados deben ser usuarios conectados con una licencia de **sistema telefónico** y una licencia de Enterprise Voice habilitada **o** tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-190">Call agents selected must **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8663b-191">Esto también se aplica si desea redirigir las llamadas a las personas de su organización que están conectadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-191">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="8663b-192">Estas personas deben tener una licencia de **sistema telefónico** y la telefonía IP empresarial habilitada **o** tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-192">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="8663b-193">Para obtener más información, vea [asignar licencias de Skype empresarial](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [asignar licencias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [el plan de llamadas es adecuado para usted](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) .</span><span class="sxs-lookup"><span data-stu-id="8663b-193">For more information see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="8663b-194">Para habilitar un agente para telefonía IP empresarial, puede usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8663b-194">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8663b-195">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8663b-195">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="8663b-196">Usuarios en línea con una licencia de **sistema telefónico** o un plan de llamadas que se agregan a un grupo de Office 365. una lista de distribución habilitada para correo electrónico. o un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8663b-196">Online users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="8663b-197">Puede demorar hasta tres horas en un agente recién agregado de una lista de distribución o un grupo de seguridad para empezar a recibir llamadas de una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-197">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="8663b-198">Una lista de distribución o un grupo de seguridad recién creados puede demorar 48 horas en estar disponible para usarse con las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="8663b-199">Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="8663b-199">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="8663b-200">Si los agentes usan la aplicación Microsoft Teams para recibir llamadas en la cola de llamadas, deben estar en modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8663b-200">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

![captura de pantalla del panel agregar agentes de llamadas](media/skype-for-business-add-agents-to-call-queue.png)

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="8663b-203">**Método de enrutamiento** Puede elegir entre **operador**, **serie**o **Round Robin** para el método de distribución de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-203">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="8663b-204">De manera predeterminada, todas las colas de llamadas nuevas y existentes tienen un enrutamiento a operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8663b-204">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="8663b-205">Cuando se usa el enrutamiento de operador, la primera llamada en la cola sonará a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8663b-205">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="8663b-206">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="8663b-206">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="8663b-207">El **enrutamiento del operador** hace que la primera llamada de la cola suene a todos los agentes de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8663b-207">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="8663b-208">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="8663b-208">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="8663b-209">El **enrutamiento serie** llamará a los agentes de llamadas entrantes uno por uno, empezando desde el principio de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-209">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="8663b-210">Los agentes no se pueden pedir dentro de la lista de agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-210">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="8663b-211">Si un agente omite o no contesta una llamada, se realizará una llamada al siguiente agente de la lista y se probará con todos los agentes, de uno a uno, hasta que se responda la llamada o se agote el tiempo de espera en la cola.</span><span class="sxs-lookup"><span data-stu-id="8663b-211">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="8663b-212">El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola.</span><span class="sxs-lookup"><span data-stu-id="8663b-212">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="8663b-213">El enrutamiento **Round Robin** de equilibra las llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="8663b-213">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="8663b-214">Esto puede ser muy conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-214">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="8663b-215">Seleccionar una opción de cancelación de la suscripción</span><span class="sxs-lookup"><span data-stu-id="8663b-215">Select an agent opt-out option</span></span>

![captura de pantalla de las opciones de cancelación del agente, con llamadas numeradas](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
 
* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="8663b-218">El **agente puede dejar de recibir llamadas** Habilita esta opción para permitir que los agentes de la cola de llamadas no puedan tomar llamadas de una cola en particular.</span><span class="sxs-lookup"><span data-stu-id="8663b-218">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="8663b-219">Al habilitar esta opción, todos los agentes de esta cola iniciarán o dejarán de recibir llamadas de esta cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-219">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="8663b-220">Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).</span><span class="sxs-lookup"><span data-stu-id="8663b-220">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="8663b-221">Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8663b-221">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="8663b-222">Abra **Opciones** en el cliente de Skype for Business de su escritorio.</span><span class="sxs-lookup"><span data-stu-id="8663b-222">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="8663b-223">En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.</span><span class="sxs-lookup"><span data-stu-id="8663b-223">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="8663b-224">En la página Configuración de usuario, haga clic en **colas de llamadas**y, a continuación, desactive las casillas de las colas para las que desee optar.</span><span class="sxs-lookup"><span data-stu-id="8663b-224">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8663b-225">Los agentes que usen aplicaciones o extremos que no sean de Skype empresarial pueden acceder a la opción de cancelación de la suscripción en [https://aka.ms/cqsettings](https://aka.ms/cqsettings)el portal de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="8663b-225">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="8663b-226">![Icono del número 2, que hace referencia a una llamada en la](media/sfbcallout2.png)
**configuración de alerta del agente** de captura de pantalla anterior</span><span class="sxs-lookup"><span data-stu-id="8663b-226">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="8663b-227">Esto define la duración de un agente de notificación de una llamada antes de que los métodos de enrutamiento de serie o de turnos pasen al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="8663b-227">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="8663b-228">La configuración predeterminada es de 30 segundos, pero se puede establecer hasta 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="8663b-228">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="8663b-229">Establecer las opciones de desbordamiento de llamadas y administración de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="8663b-229">Set the call overflow and timeout handling options</span></span>

![captura de pantalla de las opciones de control de desbordamiento con llamadas numeradas](media/3f018734-16fe-458b-827d-71fc25155cde.png)
 
* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="8663b-232">**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8663b-232">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="8663b-233">El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="8663b-233">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="8663b-234">Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="8663b-234">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="8663b-236">**Cuando se alcanza el número máximo de llamadas** Cuando la cola de llamadas alcanza su tamaño máximo (establecido mediante las **llamadas máximas en la configuración de la cola** ), puede elegir qué sucede con las llamadas entrantes nuevas.</span><span class="sxs-lookup"><span data-stu-id="8663b-236">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="8663b-237">**Desconectar**: la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="8663b-237">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="8663b-238">**Redirigir a** Si elige esta opción, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8663b-238">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="8663b-239">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o tener un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-239">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="8663b-240">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="8663b-240">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8663b-241">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="8663b-241">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="8663b-242">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="8663b-242">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="8663b-243">**Aplicación de voz** Seleccione el nombre de una cola de llamadas o del operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="8663b-243">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout3.png)

<span data-ttu-id="8663b-245">**Tiempo de espera de llamada: tiempo de espera máximo** También puede decidir cuánto tiempo puede estar en espera una llamada en la cola antes de que se agote el tiempo de espera y deba redirigirse o desconectarse.</span><span class="sxs-lookup"><span data-stu-id="8663b-245">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="8663b-246">Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**.</span><span class="sxs-lookup"><span data-stu-id="8663b-246">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="8663b-247">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="8663b-247">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="8663b-248">El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="8663b-248">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="8663b-249">Esto permite manipular el flujo de llamadas con una granularidad más fina.</span><span class="sxs-lookup"><span data-stu-id="8663b-249">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="8663b-250">Por ejemplo, puede especificar que las llamadas no contestadas por un agente en un plazo de 30 segundos vayan a un operador automático de búsqueda de directorios.</span><span class="sxs-lookup"><span data-stu-id="8663b-250">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

<span data-ttu-id="8663b-252">**Cuando la llamada supera el tiempo de salida** Cuando la llamada alcanza el límite establecido en el valor de **tiempo que puede esperar una llamada en la cola** , puede elegir lo que le sucede a esta llamada:</span><span class="sxs-lookup"><span data-stu-id="8663b-252">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="8663b-253">**Desconectar**: la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="8663b-253">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="8663b-254">**Redirigir esta llamada a** Si elige esta opción, tendrá las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8663b-254">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="8663b-255">**Persona de su empresa** Un usuario en línea con una licencia de **sistema telefónico** y estar habilitado para telefonía IP empresarial o para tener planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="8663b-256">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="8663b-256">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8663b-257">Para ello, seleccione una **persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="8663b-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="8663b-258">Para obtener información sobre las licencias necesarias para el buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="8663b-258">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="8663b-259">**Aplicación de voz** Seleccione el nombre de una cola de llamadas o del operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="8663b-259">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="8663b-260">Cambiar la identificación de llamadas de un usuario para las llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="8663b-260">Changing a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="8663b-261">Puede proteger la identidad de un usuario si cambia la identificación de llamadas para las llamadas salientes a una cola de llamadas, a un operador automático o a cualquier número de servicio mediante la creación de una directiva con el cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="8663b-261">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="8663b-262">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8663b-262">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="8663b-263">A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="8663b-263">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="8663b-264">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8663b-264">To do this, run:</span></span>
 
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="8663b-265">Puede obtener más información sobre cómo realizar cambios en la configuración de identificación de llamadas de su organización en el artículo [cómo se puede usar la identificación de llamadas en su organización](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="8663b-265">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="8663b-266">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="8663b-266">Call queue cmdlets</span></span>

<span data-ttu-id="8663b-267">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-267">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="8663b-268">Estos son los cmdlets que necesita para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8663b-268">Here are the cmdlets that you need to manage a call queue.</span></span>
 
- [<span data-ttu-id="8663b-269">Nuevo: CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8663b-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="8663b-270">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8663b-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="8663b-271">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8663b-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="8663b-272">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8663b-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="8663b-273">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8663b-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="8663b-274">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="8663b-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8663b-275">Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración que puede simplificar su trabajo diario, cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="8663b-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8663b-276">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="8663b-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="8663b-277">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8663b-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="8663b-278">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="8663b-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="8663b-279">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar solo el centro de administración de Microsoft Teams, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="8663b-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8663b-280">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="8663b-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="8663b-281">Administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8663b-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="8663b-282">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8663b-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="8663b-283">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8663b-283">Related topics</span></span>

[<span data-ttu-id="8663b-284">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="8663b-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="8663b-285">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="8663b-285">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="8663b-286">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="8663b-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="8663b-287">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="8663b-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
