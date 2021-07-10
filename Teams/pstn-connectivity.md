---
title: Opciones de conectividad RTC
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Obtenga más información sobre Teams de llamadas (conectividad RTC) y las decisiones que tome para su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354526"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="fca00-103">Opciones de conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="fca00-103">PSTN connectivity options</span></span>

<span data-ttu-id="fca00-104">Microsoft proporciona funcionalidades completas de Exchange de sucursales privadas (PBX) para su organización a través de Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="fca00-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="fca00-105">Sin embargo, para permitir a los usuarios realizar llamadas fuera de su organización, debe conectarse Sistema telefónico a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="fca00-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="fca00-106">Este artículo se centra en las opciones de conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="fca00-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="fca00-107">Para obtener más información sobre las soluciones de voz de Microsoft, incitar a los detalles sobre Sistema telefónico características, vea Planear su [Teams de voz.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="fca00-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="fca00-108">Para conectar Sistema telefónico a la RTC, puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fca00-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="fca00-109">[**Plan de llamadas**](#phone-system-with-calling-plan).</span><span class="sxs-lookup"><span data-stu-id="fca00-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="fca00-110">Una solución todo en la nube con Microsoft como operador rtc.</span><span class="sxs-lookup"><span data-stu-id="fca00-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="fca00-111">[**Enrutamiento directo**](#phone-system-with-direct-routing), que le permite usar su propio operador RTC conectando los controladores de borde de sesión (SBC) a Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="fca00-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="fca00-112">[**Operador Conectar**](#phone-system-with-operator-connect), que actualmente solo está disponible en **versión preliminar pública.**</span><span class="sxs-lookup"><span data-stu-id="fca00-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="fca00-113">Con operador Conectar, si su operador existente es un participante en el programa operador de Microsoft Conectar, pueden administrar las llamadas RTC y los controladores de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="fca00-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="fca00-114">También puede elegir una combinación de opciones, que le permite diseñar una solución para un entorno complejo o administrar una migración de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="fca00-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="fca00-115">Tenga en cuenta que la opción o las opciones que elija afectan a la configuración de Sistema telefónico características.</span><span class="sxs-lookup"><span data-stu-id="fca00-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="fca00-116">Para obtener más información, vea [Consideraciones de configuración](#configuration-considerations) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="fca00-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="fca00-117">Sistema telefónico con plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="fca00-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="fca00-118">Sistema telefónico con Plan de llamadas es la solución de voz de Microsoft en la nube para Teams usuarios.</span><span class="sxs-lookup"><span data-stu-id="fca00-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="fca00-119">Esta es la opción más sencilla que se conecta Sistema telefónico a la RTC.</span><span class="sxs-lookup"><span data-stu-id="fca00-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="fca00-120">Con esta opción, Microsoft actúa como su operador RTC, como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="fca00-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![Diagrama 1 muestra Sistema telefónico con plan de llamadas](media/voice-solutions-simple.png)

<span data-ttu-id="fca00-122">Si responde sí a lo siguiente, Sistema telefónico con Plan de llamadas es la solución adecuada para usted:</span><span class="sxs-lookup"><span data-stu-id="fca00-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="fca00-123">Plan de llamadas está disponible en su región.</span><span class="sxs-lookup"><span data-stu-id="fca00-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="fca00-124">No es necesario conservar el operador RTC actual.</span><span class="sxs-lookup"><span data-stu-id="fca00-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="fca00-125">Desea usar el acceso administrado por Microsoft a la RTC.</span><span class="sxs-lookup"><span data-stu-id="fca00-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="fca00-126">Con esta opción:</span><span class="sxs-lookup"><span data-stu-id="fca00-126">With this option:</span></span> 

- <span data-ttu-id="fca00-127">Obtiene un Teléfono Microsoft con planes de llamadas nacionales o internacionales agregados que permiten llamar a teléfonos de todo el mundo (dependiendo del nivel de servicio que se esté autorizando).</span><span class="sxs-lookup"><span data-stu-id="fca00-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="fca00-128">No necesita la implementación o el mantenimiento de una implementación local porque el plan de llamadas funciona &mdash; sin Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fca00-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="fca00-129">Nota: Si es necesario, puede elegir conectar un controlador de borde de sesión (SBC) compatible a través del enrutamiento directo para la interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros compatibles con el SBC.</span><span class="sxs-lookup"><span data-stu-id="fca00-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="fca00-130">Esta opción requiere una conexión ininterrumpida a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fca00-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="fca00-131">Para obtener más información sobre el plan de llamadas, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fca00-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="fca00-132">¿Qué plan de llamada es adecuado para usted?</span><span class="sxs-lookup"><span data-stu-id="fca00-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="fca00-133">Cómo comprar un plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="fca00-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="fca00-134">Países y regiones donde el Plan de llamadas está disponible</span><span class="sxs-lookup"><span data-stu-id="fca00-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="fca00-135">Configurar plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="fca00-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="fca00-136">Sistema telefónico con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="fca00-137">Esta opción conecta Sistema telefónico a la red de telefonía mediante enrutamiento directo, como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="fca00-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![Diagrama 5 muestra Sistema telefónico con enrutamiento directo](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="fca00-139">Si responde sí a las siguientes preguntas, Sistema telefónico enrutamiento directo es la solución adecuada para usted:</span><span class="sxs-lookup"><span data-stu-id="fca00-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="fca00-140">Desea usar Teams con Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="fca00-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="fca00-141">Debe conservar el operador RTC actual.</span><span class="sxs-lookup"><span data-stu-id="fca00-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="fca00-142">Desea mezclar el enrutamiento, con algunas llamadas pasando por el Plan de llamadas, otras a través de su operador.</span><span class="sxs-lookup"><span data-stu-id="fca00-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="fca00-143">Necesita interoperar con PBX y/o equipos de terceros, como los paginadores generales, dispositivos analógicos, entre otros.</span><span class="sxs-lookup"><span data-stu-id="fca00-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="fca00-144">Con esta opción:</span><span class="sxs-lookup"><span data-stu-id="fca00-144">With this option:</span></span>

- <span data-ttu-id="fca00-145">Conecta su propio controlador de borde de sesión (SBC) compatible con Sistema telefónico sin necesidad de software local adicional.</span><span class="sxs-lookup"><span data-stu-id="fca00-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="fca00-146">Puede usar prácticamente cualquier operador de telefonía con Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="fca00-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="fca00-147">Puede configurar y administrar esta opción, o puede configurarla y administrarla su operador o partner (pregunte si su operador o partner proporciona esta opción).</span><span class="sxs-lookup"><span data-stu-id="fca00-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="fca00-148">Puede configurar la interoperabilidad entre los equipos de telefonía, como pbx de terceros y &mdash; dispositivos analógicos &mdash; y Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="fca00-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="fca00-149">Esta opción requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fca00-149">This option requires the following:</span></span>

- <span data-ttu-id="fca00-150">Conexión ininterrumpida a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fca00-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="fca00-151">Implementar y mantener un SBC compatible.</span><span class="sxs-lookup"><span data-stu-id="fca00-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="fca00-152">Un contrato con un operador de terceros.</span><span class="sxs-lookup"><span data-stu-id="fca00-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="fca00-153">(A menos que se implemente como una opción para proporcionar conexión a PBX de terceros, dispositivos analógicos u otro equipo de telefonía para los usuarios que están en Sistema telefónico con plan de llamadas).</span><span class="sxs-lookup"><span data-stu-id="fca00-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="fca00-154">Para obtener más información sobre enrutamiento directo, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fca00-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="fca00-155">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="fca00-156">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="fca00-157">Administrar directivas de enrutamiento de voz para su uso con Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="fca00-158">Planear enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="fca00-159">Lista de controladores de borde de sesión certificados para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="fca00-160">Sistema telefónico con operador Conectar</span><span class="sxs-lookup"><span data-stu-id="fca00-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="fca00-161">Con Operador Conectar, actualmente en versión preliminar pública, si su operador existente es un participante en el programa Operador de Microsoft Conectar, puede administrar el servicio para llevar llamadas RTC Teams.</span><span class="sxs-lookup"><span data-stu-id="fca00-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="fca00-162">Su operador administra los servicios de llamadas RTC y los controladores de borde de sesión (SBC), lo que le permite ahorrar en la compra y administración de hardware.</span><span class="sxs-lookup"><span data-stu-id="fca00-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="fca00-163">La Conectar operador podría ser la solución adecuada para su organización si:</span><span class="sxs-lookup"><span data-stu-id="fca00-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="fca00-164">Microsoft Calling Plan no está disponible en su ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="fca00-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="fca00-165">Su operador preferido es un participante del programa de Conectar microsoft.</span><span class="sxs-lookup"><span data-stu-id="fca00-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="fca00-166">Desea buscar un operador nuevo para habilitar las llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="fca00-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="fca00-167">Para obtener información sobre las ventajas y requisitos de Operador Conectar, y para obtener una lista de operadores que participan en este programa, vea [Plan operador Conectar](operator-connect-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fca00-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="fca00-168">Para obtener información sobre cómo configurar el operador Conectar, vea [Configurar operador Conectar](operator-connect-configure.md).</span><span class="sxs-lookup"><span data-stu-id="fca00-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="fca00-169">Consideraciones de configuración</span><span class="sxs-lookup"><span data-stu-id="fca00-169">Configuration considerations</span></span>

<span data-ttu-id="fca00-170">La mayoría Sistema telefónico características son las mismas, independientemente de la opción de conectividad RTC que elija.</span><span class="sxs-lookup"><span data-stu-id="fca00-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="fca00-171">Por ejemplo, la configuración de llamadas sin responder y reenvío, la transferencia de llamadas, la música personalizada en espera, el parque de llamadas, la línea compartida y las aplicaciones de voz están disponibles.</span><span class="sxs-lookup"><span data-stu-id="fca00-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="fca00-172">Para obtener una lista completa de Sistema telefónico características, vea Esto es lo [que obtiene](here-s-what-you-get-with-phone-system.md)con Sistema telefónico .</span><span class="sxs-lookup"><span data-stu-id="fca00-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="fca00-173">Sin embargo, hay algunas diferencias en la funcionalidad que afectan a la forma en que se configuran determinadas Sistema telefónico características.</span><span class="sxs-lookup"><span data-stu-id="fca00-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="fca00-174">Por ejemplo, enrutamiento directo requiere pasos adicionales para configurar el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fca00-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="fca00-175">Como otro ejemplo, Enrutamiento directo proporciona enrutamiento basado en ubicación (LBR) para que pueda restringir la omisión de peaje en determinadas ubicaciones geográficas donde no está permitido.</span><span class="sxs-lookup"><span data-stu-id="fca00-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="fca00-176">Teléfono de números</span><span class="sxs-lookup"><span data-stu-id="fca00-176">Phone number management</span></span>

<span data-ttu-id="fca00-177">Microsoft tiene dos tipos de números de teléfono disponibles: números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización, y números de servicio, disponibles como números de servicio gratuitos y de pago.</span><span class="sxs-lookup"><span data-stu-id="fca00-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="fca00-178">Los números de servicio tienen mayor capacidad de llamada simultánea que los números de suscriptor y se pueden asignar a servicios como Audioconferencia, Operadores automáticos o Colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fca00-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="fca00-179">Tendrá que decidir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fca00-179">You will need to decide:</span></span>

- <span data-ttu-id="fca00-180">¿Qué ubicaciones de usuario necesitan nuevos números de teléfono de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="fca00-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="fca00-181">¿Qué tipo de número de teléfono (suscriptor o servicio) necesito?</span><span class="sxs-lookup"><span data-stu-id="fca00-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="fca00-182">¿Cómo puedo portabilidad de números de teléfono existentes a Teams?</span><span class="sxs-lookup"><span data-stu-id="fca00-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="fca00-183">La forma en que adquiere y administra los números de teléfono varía en función de la opción de conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="fca00-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="fca00-184">Para obtener información sobre cómo administrar números de teléfono para el plan de llamadas, vea [Administrar números de teléfono para su organización.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="fca00-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="fca00-185">Para obtener información sobre cómo administrar números de teléfono para enrutamiento directo, vea Configurar el número de teléfono y habilitar la voz y el correo [de voz empresariales.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)</span><span class="sxs-lookup"><span data-stu-id="fca00-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="fca00-186">Para obtener información sobre cómo administrar números de teléfono con Conectar operador, vea Configurar números de teléfono con [operador Conectar](operator-connect-configure.md#set-up-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="fca00-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="fca00-187">Planes de marcado y enrutamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="fca00-187">Call routing and dial plans</span></span>

<span data-ttu-id="fca00-188">La forma de configurar el enrutamiento de llamadas varía en función de la opción de conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="fca00-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="fca00-189">En el caso de los planes de llamadas, la mayor parte del enrutamiento de llamadas se administra mediante la infraestructura del Plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fca00-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="fca00-190">Configure los planes de marcado de usuario para fines de traducción de números para la autorización de llamadas y el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fca00-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="fca00-191">Para obtener más información, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="fca00-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="fca00-192">Para enrutamiento directo, debe configurar el enrutamiento de llamadas especificando las rutas de voz y asignando directivas de enrutamiento de voz a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fca00-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="fca00-193">Puede configurar los planes de marcado para la traducción de números en el nivel de tronco para garantizar la interoperabilidad con los controladores de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="fca00-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="fca00-194">Para obtener más información, vea Configurar enrutamiento [de voz para enrutamiento](direct-routing-voice-routing.md)directo, Administrar directivas de enrutamiento [de](manage-voice-routing-policies.md) voz y Traducir números [de teléfono.](direct-routing-translate-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="fca00-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="fca00-195">En el Conectar operador, el operador administra la mayor parte del enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fca00-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="fca00-196">Configure los planes de marcado de usuario para fines de traducción de números para la autorización de llamadas y el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fca00-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="fca00-197">Para obtener más información, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="fca00-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="fca00-198">Location-Based enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="fca00-199">En algunos países y regiones, es ilegal omitir el operador RTC para reducir los costos de llamadas de larga distancia.</span><span class="sxs-lookup"><span data-stu-id="fca00-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="fca00-200">Location-Based enrutamiento automático (LBR) para enrutamiento directo le permite restringir la omisión de peaje para Teams usuarios en función de su ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="fca00-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="fca00-201">Para obtener más información sobre cómo planear y configurar LBR, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="fca00-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="fca00-202">Planear enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="fca00-203">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="fca00-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="fca00-204">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="fca00-205">Caso práctico de Contoso: Location-Based enrutamiento</span><span class="sxs-lookup"><span data-stu-id="fca00-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="fca00-206">Describe cómo una corporación multinacional ficticia, Contoso, implementó Location-Based enrutamiento para su organización.</span><span class="sxs-lookup"><span data-stu-id="fca00-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="fca00-207">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fca00-207">Emergency calling</span></span>

<span data-ttu-id="fca00-208">La forma en que configura las llamadas de emergencia varía en función de la opción de conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="fca00-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="fca00-209">Para el Plan de llamadas, cada usuario se habilita automáticamente para las llamadas de emergencia y es necesario que tenga una dirección de emergencia registrada asociada con su número de teléfono asignado.</span><span class="sxs-lookup"><span data-stu-id="fca00-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="fca00-210">Se admiten las llamadas de emergencia dinámicas (basadas en la ubicación del Teams cliente).</span><span class="sxs-lookup"><span data-stu-id="fca00-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="fca00-211">Para enrutamiento directo, debe definir directivas de llamadas de emergencia para los usuarios mediante una directiva de enrutamiento de llamadas de emergencia de Teams (TeamsEmergencyCallRoutingPolicy) para definir los números de emergencia y su destino de enrutamiento asociado.</span><span class="sxs-lookup"><span data-stu-id="fca00-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="fca00-212">Las ubicaciones de emergencia registradas no son compatibles con los usuarios de Enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="fca00-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="fca00-213">Para las llamadas de emergencia dinámicas, se requiere una configuración adicional para el enrutamiento de llamadas de emergencia y, posiblemente, para la conectividad de partners.</span><span class="sxs-lookup"><span data-stu-id="fca00-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="fca00-214">En el caso de Conectar operador, cada usuario está habilitado automáticamente para las llamadas de emergencia y es necesario que tenga una dirección de emergencia registrada asociada con su número de teléfono asignado, pero solo el partner del operador puede establecerlo.</span><span class="sxs-lookup"><span data-stu-id="fca00-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="fca00-215">Se admiten las llamadas de emergencia dinámicas (basadas en la ubicación del Teams cliente).</span><span class="sxs-lookup"><span data-stu-id="fca00-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="fca00-216">Para obtener más información sobre conceptos y terminología de llamadas de emergencia y cómo configurar las llamadas de emergencia y las llamadas de emergencia dinámicas, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="fca00-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="fca00-217">Administrar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fca00-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="fca00-218">Planear y configurar las llamadas de emergencia dinámicas</span><span class="sxs-lookup"><span data-stu-id="fca00-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="fca00-219">Administrar directivas de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fca00-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="fca00-220">Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fca00-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="fca00-221">Caso práctico de Contoso: Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fca00-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="fca00-222">Describe cómo una corporación multinacional ficticia, Contoso, implementó llamadas de emergencia para su organización.</span><span class="sxs-lookup"><span data-stu-id="fca00-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="fca00-223">Topología de red para características de voz</span><span class="sxs-lookup"><span data-stu-id="fca00-223">Network topology for voice features</span></span>

<span data-ttu-id="fca00-224">Si va a implementar llamadas de emergencia dinámicas o Location-Based enrutamiento directo, debe configurar la configuración de red para usarla con estas características en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fca00-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="fca00-225">Para obtener información sobre cómo configurar la configuración de red para regiones de red, sitios de red, subredes de red y direcciones IP de confianza, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="fca00-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="fca00-226">Configuración de red para las características de voz en la nube Microsoft Teams: conceptos y terminología</span><span class="sxs-lookup"><span data-stu-id="fca00-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="fca00-227">Administre la topología de red para las características de voz en la nube en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fca00-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



