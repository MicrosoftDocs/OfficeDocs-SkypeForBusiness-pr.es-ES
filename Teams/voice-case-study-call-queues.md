---
title: Caso práctico de Contoso de voz de Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121298"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="6f233-103">Caso práctico de Contoso: Operadores automáticos y colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="6f233-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="6f233-104">Contoso estaba familiarizado con los operadores automáticos y las colas de llamadas desde su implementación local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f233-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6f233-105">Para comprender cómo configurar operadores automáticos en la nube y colas de llamadas, revisaron Planear operadores automáticos de Teams y colas [de llamadas.](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="6f233-106">Requisitos según el tipo de sitio</span><span class="sxs-lookup"><span data-stu-id="6f233-106">Requirements depending on site type</span></span>

<span data-ttu-id="6f233-107">Según el tipo de sitio, Contoso tenía las siguientes necesidades:</span><span class="sxs-lookup"><span data-stu-id="6f233-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="6f233-108">Tipo de sitio A: Sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="6f233-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="6f233-109">Tipo de sitio A necesario para mantener el mismo número de teléfono asociado al recepcionista que el número de sus operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="6f233-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="6f233-110">Los departamentos clave de cada uno de estos sitios tendrían sus propias colas de llamadas que se enrutaría a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="6f233-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="6f233-111">Había una mezcla de sitios que usaban sistema telefónico con enrutamiento directo y sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6f233-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="6f233-112">Tipo de sitio B: Skype Empresarial Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="6f233-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="6f233-113">El tipo de sitio B tenía operadores automáticos y colas de llamadas existentes que necesitaban migrar a Teams.</span><span class="sxs-lookup"><span data-stu-id="6f233-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="6f233-114">Contoso necesitaba mantener los números de teléfono asociados con los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="6f233-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="6f233-115">Contoso movió la mayoría de estos sitios al sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6f233-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="6f233-116">Sin embargo, en las pocas ubicaciones en las que los planes de llamadas no estaba disponible, Contoso movió estos sitios a una configuración de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="6f233-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="6f233-117">Tipo de sitio C: Skype Empresarial Telefonía IP empresarial & sistema tradicional de telefonía heredada</span><span class="sxs-lookup"><span data-stu-id="6f233-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="6f233-118">El tipo de sitio C tenía operadores automáticos existentes que residían en el sistema de telefonía tradicional heredado.</span><span class="sxs-lookup"><span data-stu-id="6f233-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="6f233-119">Las decisiones y configuraciones de este sitio eran las mismas que el tipo de sitio A.</span><span class="sxs-lookup"><span data-stu-id="6f233-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="6f233-120">Para todos los tipos de sitio, Contoso hizo las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="6f233-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="6f233-121">P: ¿Usaremos números nuevos o existentes?</span><span class="sxs-lookup"><span data-stu-id="6f233-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="6f233-122">A: Contoso decidió usar números de teléfono existentes para asignarse a la cuenta de servicio para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="6f233-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="6f233-123">P: ¿Cuándo estará disponible el operador automático para aceptar llamadas entrantes?</span><span class="sxs-lookup"><span data-stu-id="6f233-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="6f233-124">A: Contoso decidió establecer el horario laboral y hacer que las llamadas recibidas después del horario laboral se redirijan a un operador automático "después del horario laboral".</span><span class="sxs-lookup"><span data-stu-id="6f233-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="6f233-125">P: ¿Cómo se enrutarán las llamadas a los miembros de una cola de llamadas: enrutamiento de operador, serie o round robin?</span><span class="sxs-lookup"><span data-stu-id="6f233-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="6f233-126">A: Contoso decidió usar el enrutamiento de Attendant,</span><span class="sxs-lookup"><span data-stu-id="6f233-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="6f233-127">P: ¿Cómo determinaremos cuándo un usuario debe o no recibir una llamada?</span><span class="sxs-lookup"><span data-stu-id="6f233-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="6f233-128">A: Contoso decidió usar las opciones de administración de llamadas para determinar si el agente está disponible: enrutamiento basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="6f233-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="6f233-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="6f233-129">Configuration</span></span>

<span data-ttu-id="6f233-130">Los pasos para configurar un operador automático y una cola de llamadas incluyen los siguientes esquemas en [Administrar cuentas de recursos:](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="6f233-131">Obtener un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="6f233-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="6f233-132">Obtener un sistema telefónico gratuito: licencia de usuario virtual o una licencia de sistema telefónico de pago para usar con la cuenta de recursos o una licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="6f233-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="6f233-133">Cree la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6f233-133">Create the resource account.</span></span> <span data-ttu-id="6f233-134">Se requiere un operador automático o una cola de llamadas para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="6f233-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="6f233-135">Asignar el sistema telefónico o un sistema telefónico: licencia de usuario virtual a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6f233-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="6f233-136">Para obtener más información, vea [Microsoft 365 Phone System : licencia de usuario virtual.](./teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="6f233-137">Asigne un número de teléfono de servicio a la cuenta de recursos a la que asignó licencias.</span><span class="sxs-lookup"><span data-stu-id="6f233-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="6f233-138">Crear una cola de llamadas del sistema telefónico o un operador automático</span><span class="sxs-lookup"><span data-stu-id="6f233-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="6f233-139">Vincule la cuenta de recursos con una cola de llamadas o un operador automático.</span><span class="sxs-lookup"><span data-stu-id="6f233-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="6f233-140">Sitios con sistema telefónico con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="6f233-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="6f233-141">Contoso tenía que configurar el número de teléfono proporcionado por el operador local como el número de servicio en Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f233-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="6f233-142">Para configurar un número de teléfono disponible a través de Enrutamiento directo, Contoso siguió las instrucciones que se encuentran en [Administrar cuentas de recursos.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="6f233-143">Como Office 365 no es consciente de los números de teléfono locales, Contoso usó PowerShell para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="6f233-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="6f233-144">Para configurar el operador automático en la nube, Contoso siguió los pasos descritos en [Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="6f233-145">Para configurar una cola de llamadas en la nube, Contoso siguió los pasos descritos en [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="6f233-146">Sitios con sistema telefónico con plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="6f233-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="6f233-147">Contoso tenía que portabilidad el número de teléfono que se usaba para Skype Empresarial Telefonía IP empresarial operadores automáticos a Office 365 Phone System.</span><span class="sxs-lookup"><span data-stu-id="6f233-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="6f233-148">Esto permitía asignar el mismo número que un número de servicio para usarlo como operador automático.</span><span class="sxs-lookup"><span data-stu-id="6f233-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="6f233-149">Para portabilidad del número de teléfono, Contoso siguió las instrucciones de Transferir números de teléfono a [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) y obtuvo instrucciones adicionales en Administrar números de teléfono [para su organización.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="6f233-150">Para configurar un operador automático en la nube, Contoso siguió los pasos descritos en [Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="6f233-151">Para configurar una cola de llamadas en la nube, Contoso siguió los pasos descritos en [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6f233-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

