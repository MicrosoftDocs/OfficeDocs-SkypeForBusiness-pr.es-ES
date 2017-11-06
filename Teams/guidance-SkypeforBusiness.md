---
title: Habilitar Microsoft Teams en paralelo con Skype Empresarial
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guía para usar Skype Empresarial y Microsoft Teams en paralelo."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b1a635fe4abb607064a0e26240ed58715fa43a8d
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="3f048-103">Habilitar Microsoft Teams en paralelo con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3f048-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="3f048-104">Para las organizaciones que tienen implementado actualmente Skype Empresarial Online, la reciente introducción de Microsoft Teams supone una oportunidad para evaluar el potencial de Microsoft Teams como una única solución de colaboración y comunicaciones y un reto para evaluar las dos soluciones y cómo coexisten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3f048-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="3f048-105">Si Microsoft Teams cumple los requisitos de negocio que tiene hoy en día, podrá comenzar a adoptarlo hasta que se convierta en la única solución de colaboración y comunicaciones de su organización.</span><span class="sxs-lookup"><span data-stu-id="3f048-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="3f048-106">Microsoft Teams está habilitado de forma predeterminada en todos los inquilinos que reúnen las condiciones.</span><span class="sxs-lookup"><span data-stu-id="3f048-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="3f048-107">Por lo tanto, tiene que decidir cómo va a administrar Microsoft Teams en paralelo con Skype Empresarial y seguir cumpliendo las expectativas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f048-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="3f048-108">En general, hay dos recorridos de cliente en paralelo principales.</span><span class="sxs-lookup"><span data-stu-id="3f048-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="3f048-109">Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f048-109">They are:</span></span>

-   <span data-ttu-id="3f048-110">**Opción 1:** recorrido de cliente no administrado en paralelo.</span><span class="sxs-lookup"><span data-stu-id="3f048-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="3f048-111">TI no controla de forma activa la experiencia en paralelo y se autoriza a los usuarios a que elijan la aplicación que prefieren.</span><span class="sxs-lookup"><span data-stu-id="3f048-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="3f048-112">**Opción 2:** recorrido de cliente administrado en paralelo.</span><span class="sxs-lookup"><span data-stu-id="3f048-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="3f048-113">TI controla la experiencia en paralelo y guía a los usuarios a lo largo del recorrido que se hace para introducir gradualmente Microsoft Teams: primero se introduce un espacio de trabajo de colaboración nuevo basado en chats con chat privado, después las experiencias de reuniones y, por último, las experiencias de llamada de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![Diagrama de dos recorridos paralelos de clientes: gestionado y no gestionado.](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="3f048-115">Ventajas y consideraciones en paralelo</span><span class="sxs-lookup"><span data-stu-id="3f048-115">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="3f048-116">Cada recorrido tiene ventajas y consideraciones que hay que evaluar a la hora de determinar el camino que se debe ir tomando en función del perfil de su organización.</span><span class="sxs-lookup"><span data-stu-id="3f048-116">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="3f048-117">En la tabla siguiente se comparan los recorridos de cliente en paralelo que hay: administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="3f048-117">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f048-118">Rutas de migración</span><span class="sxs-lookup"><span data-stu-id="3f048-118">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="3f048-119">En paralelo no administrado</span><span class="sxs-lookup"><span data-stu-id="3f048-119">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="3f048-120">En paralelo administrado</span><span class="sxs-lookup"><span data-stu-id="3f048-120">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="3f048-121"><strong>Perfil de la organización</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-121"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="3f048-122">Normalmente, organizaciones pequeñas que no tienen recursos de TI dedicados</span><span class="sxs-lookup"><span data-stu-id="3f048-122">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="3f048-123">TI deja que el usuario decida qué herramientas prefiere para su trabajo</span><span class="sxs-lookup"><span data-stu-id="3f048-123">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="3f048-124">El uso principal de Skype Empresarial es MI/P y reuniones</span><span class="sxs-lookup"><span data-stu-id="3f048-124">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="3f048-125">Normalmente, organizaciones medianas o grandes</span><span class="sxs-lookup"><span data-stu-id="3f048-125">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="3f048-126">TI quiere controlar el despliegue de las nuevas herramientas con mayor rigurosidad</span><span class="sxs-lookup"><span data-stu-id="3f048-126">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="3f048-127">Mayor adopción de Skype Empresarial en este momento</span><span class="sxs-lookup"><span data-stu-id="3f048-127">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="3f048-128">Red e infraestructura más complejas</span><span class="sxs-lookup"><span data-stu-id="3f048-128">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="3f048-129">Varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="3f048-129">Multiple locations</span></span></p>
<li><span data-ttu-id="3f048-130">Se prefiere una aplicación con funcionalidades exclusivas de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="3f048-130">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3f048-131"><strong>Ventajas</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-131"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="3f048-132">Se aprovechan funcionalidades en Microsoft Teams que no están disponibles en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3f048-132">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="3f048-133">Un lugar de trabajo moderno y mejorado dentro de Office 365</span><span class="sxs-lookup"><span data-stu-id="3f048-133">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="3f048-134">Mayor flexibilidad para el usuario</span><span class="sxs-lookup"><span data-stu-id="3f048-134">Increased user flexibility</span></span></li>
<li><span data-ttu-id="3f048-135">Se habilitan todas las funcionalidades a la vez</span><span class="sxs-lookup"><span data-stu-id="3f048-135">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="3f048-136">Se aprovechan funcionalidades en Microsoft Teams que no están disponibles en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3f048-136">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="3f048-137">Un lugar de trabajo moderno y mejorado dentro de Office 365</span><span class="sxs-lookup"><span data-stu-id="3f048-137">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="3f048-138">Se minimiza el impacto en la productividad de los usuarios</span><span class="sxs-lookup"><span data-stu-id="3f048-138">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="3f048-139">Se reduce la superposición de funcionalidades</span><span class="sxs-lookup"><span data-stu-id="3f048-139">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="3f048-140">Se simplifica la elección de herramientas en escenarios de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="3f048-140">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="3f048-141">TI y las empresas pueden habilitar funcionalidades según convenga a la organización</span><span class="sxs-lookup"><span data-stu-id="3f048-141">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="3f048-142">Se controla el ritmo de cambio de los usuarios</span><span class="sxs-lookup"><span data-stu-id="3f048-142">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3f048-143"><strong>Consideraciones</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-143"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="3f048-144">Varias aplicaciones con funcionalidades similares que se solapan</span><span class="sxs-lookup"><span data-stu-id="3f048-144">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="3f048-145">Aumenta las probabilidades de confundir al usuario, lo que deriva en más llamadas de soporte, informática en la sombra y repercusiones en la productividad</span><span class="sxs-lookup"><span data-stu-id="3f048-145">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="3f048-146">La supervisión y planificación de red debe teniendo en cuenta dos servicios</span><span class="sxs-lookup"><span data-stu-id="3f048-146">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="3f048-147">Se necesitan más esfuerzos inmediatos de administración del cambio: reconocimiento, formación y soporte</span><span class="sxs-lookup"><span data-stu-id="3f048-147">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="3f048-148">Los usuarios pueden experimentar limitaciones en la interoperabilidad entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3f048-148">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="3f048-149">TI mantiene un control granular, desde licencias a experiencias de usuario, que requiere ciclos adicionales de planificación e implementación</span><span class="sxs-lookup"><span data-stu-id="3f048-149">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="3f048-150">La acción y los conocimientos de los usuarios hacen que se deshabiliten determinadas funcionalidades en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f048-150">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="3f048-151">Los esfuerzos de administración de cambios hacen que se deshabiliten determinadas funcionalidades en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f048-151">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="3f048-152">La supervisión y planificación de red debe teniendo en cuenta dos servicios</span><span class="sxs-lookup"><span data-stu-id="3f048-152">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="3f048-153">Los usuarios pueden experimentar limitaciones en la interoperabilidad entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3f048-153">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="3f048-154">Recorrido de cliente no administrado en paralelo</span><span class="sxs-lookup"><span data-stu-id="3f048-154">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![Diagrama del recorrido de cliente no administrado en paralelo.](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="3f048-156">En un recorrido de cliente no administrado en paralelo, Microsoft Teams se presenta como una solución de colaboración (un espacio de trabajo basado en chats, canales, aplicaciones, integración con otras cargas de trabajo de Office 365, etc.) que involucra a software cliente y clientes web en equipos de escritorio (PC o Mac) y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="3f048-156">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="3f048-157">De forma predeterminada, Microsoft Teams tiene funcionalidades que se solapan con las de Skype Empresarial; entre ellas, las llamadas y chats privados y las reuniones programadas.</span><span class="sxs-lookup"><span data-stu-id="3f048-157">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="3f048-158">Esto implica que Microsoft Teams proporciona finalmente servicios completos de colaboración y comunicaciones a la organización y, al mismo tiempo, Skype Empresarial ofrece funcionalidades similares.</span><span class="sxs-lookup"><span data-stu-id="3f048-158">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="3f048-159">Microsoft Teams admite la interoperabilidad con usuarios de Skype Empresarial Online. Cuando inicien Microsoft Teams, se les dará la oportunidad de elegir la aplicación de llamadas y chat que prefieren.</span><span class="sxs-lookup"><span data-stu-id="3f048-159">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="3f048-160">Si un usuario elige Microsoft Teams como su aplicación preferida y otro usuario no ha instalado Microsoft Teams o elige Skype Empresarial como la aplicación de llamadas y chat que prefiere, podrán seguir chateando y llamándose a través de las funcionalidades de interoperabilidad que forman parte de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-160">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="3f048-161">Microsoft trata de mejorar constantemente las experiencias de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="3f048-161">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="3f048-162">Es posible que al principio haya casos en los que la interoperabilidad no cumpla las expectativas del usuario.</span><span class="sxs-lookup"><span data-stu-id="3f048-162">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="3f048-163">Como Skype Empresarial sigue estando disponible para todos los usuarios, podrán cambiar a Skype Empresarial cuando se dispongan a usar funcionalidades que aún no puede prestar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-163">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="3f048-164">Las reuniones programadas de Microsoft Teams es otra de las funcionalidades con las que los usuarios pueden programar reuniones con Microsoft Teams o reuniones con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f048-164">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="3f048-165">Cada una de ellas tiene sus propias ventajas y, a lo largo del tiempo, cuando la experiencia de reuniones de Microsoft Teams cumpla los requisitos empresariales o supere las funcionalidades de las reuniones de Skype Empresarial, esperamos que los usuarios se vayan pasando poco a poco a las reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-165">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="3f048-166">En este recorrido de cliente no administrado en paralelo, prepare a su equipo de asistencia al cliente para que pueda gestionar llamadas de usuarios que tienen problemas con las funcionalidades de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="3f048-166">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="3f048-167">O, si no, informe a los usuarios de cuándo les conviene elegir reuniones de Microsoft Teams antes que de Skype Empresarial y viceversa.</span><span class="sxs-lookup"><span data-stu-id="3f048-167">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="3f048-168">Este recorrido de cliente en paralelo puede aplicarse en su organización. En ese caso, los usuarios se muestran más receptivos a la naturaleza de la experiencia en paralelo no administrada y la organización permite que los usuarios elijan libremente las herramientas de colaboración y comunicaciones que se adecúan mejor a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="3f048-168">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="3f048-169">Recorrido de cliente administrado en paralelo</span><span class="sxs-lookup"><span data-stu-id="3f048-169">Managed side-by-side customer journey</span></span>
-------------------------------------

![Diagrama del recorrido de cliente administrado en paralelo.](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="3f048-171">Un recorrido administrado de cliente en paralelo se inicia cuando la organización quiere controlar más la introducción de Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-171">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="3f048-172">El **primer paso** de este recorrido consiste en crear un proyecto piloto limitado de Microsoft Teams enfocado en requisitos de colaboración moderna (un espacio de trabajo basado en chats, canales, aplicaciones, integración con otras cargas de trabajo de Office 365, etc.).</span><span class="sxs-lookup"><span data-stu-id="3f048-172">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="3f048-173">El chat privado y las reuniones de canal ah hoc de Microsoft Teams están habilitados para que los usuarios del proyecto piloto puedan evaluar las experiencias de chat privado y de reuniones de Microsoft Teams si así lo deciden.</span><span class="sxs-lookup"><span data-stu-id="3f048-173">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="3f048-174">Las funcionalidades de llamadas privadas y reuniones programadas de Microsoft Teams no están habilitadas en esta fase.</span><span class="sxs-lookup"><span data-stu-id="3f048-174">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="3f048-175">Para comenzar con el piloto, vaya a [Crear un proyecto piloto de Microsoft Teams junto a Skype Empresarial](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="3f048-175">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="3f048-176">El **segundo paso** de este recorrido consiste en ampliar el lanzamiento de Microsoft Teams para la colaboración moderna con chat privado a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="3f048-176">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="3f048-177">Las reuniones programadas y las llamadas privadas siguen deshabilitadas en Microsoft Teams para reducir la superposición con las funcionalidades de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f048-177">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="3f048-178">En esta fase, tiene que pensar si la aplicación de chat que se marcará como preferida para toda la organización será Microsoft Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f048-178">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="3f048-179">Si se elige Microsoft Teams, prepare a los usuarios para que identifiquen los primeros retos de interoperabilidad que surgirán cuando se comuniquen con otras partes de la organización.</span><span class="sxs-lookup"><span data-stu-id="3f048-179">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="3f048-180">Si se elige Skype Empresarial, los chats privados de Microsoft Teams seguirán en Microsoft Teams y los usuarios finales podrán beneficiarse de forma inmediata de la naturaleza multiplataforma persistente de las funcionalidades de chat dentro de Microsoft Teams. Así, podrán seguir usando Skype Empresarial para los chats privados entre usuarios de Skype Empresarial, dentro de la organización y en toda ella.</span><span class="sxs-lookup"><span data-stu-id="3f048-180">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3f048-181">Nota</span><span class="sxs-lookup"><span data-stu-id="3f048-181">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3f048-182">Por ahora, la opción de elegir la aplicación de chat preferida solo está disponible a nivel de cliente.</span><span class="sxs-lookup"><span data-stu-id="3f048-182">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="3f048-183">Habrá que realizar una campaña de formación y adopción para extender la configuración a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="3f048-183">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="3f048-184">El **tercer paso** del recorrido de cliente gestionado en paralelo se inicia cuando la organización decide que las funcionalidades y la experiencia de reuniones de Microsoft Teams cumplen todos sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="3f048-184">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="3f048-185">Al habilitar las reuniones privadas y de canal en Microsoft Teams, se ofrece a los usuarios opciones para programar reuniones de Microsoft Teams y reuniones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f048-185">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="3f048-186">Por lo tanto, se espera que, con el tiempo, los usuarios se vayan pasando naturalmente a las reuniones de Microsoft Teams conforme se le vayan incorporando novedades.</span><span class="sxs-lookup"><span data-stu-id="3f048-186">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="3f048-187">Para que el paso de Skype Empresarial a Microsoft Teams se haga correctamente, recomendamos implementar un programa sólido de administración de cambios que incluya formación, soporte y comunicaciones donde se explique lo que aporta Microsoft Teams a los usuarios, con instrucciones claras sobre cómo empezar a usarlo.</span><span class="sxs-lookup"><span data-stu-id="3f048-187">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="3f048-188">Aproveche nuestros recursos de [preparación de usuarios](http://aka.ms/UserReadiness) para que le ayuden a diseñar su campaña de reconocimiento.</span><span class="sxs-lookup"><span data-stu-id="3f048-188">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="3f048-189">El **cuarto paso** del recorrido de cliente administrado en paralelo comienza cuando se habilitan las llamadas en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-189">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="3f048-190">Las funcionalidades de interoperabilidad de Microsoft Teams tendrán un gran peso en este paso para garantizar que la experiencia en paralelo se desarrolle sin problemas.</span><span class="sxs-lookup"><span data-stu-id="3f048-190">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="3f048-191">Idealmente, para forzar que se use Microsoft Teams para realizar llamadas privadas, Microsoft Teams se establece como la aplicación de llamadas predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f048-191">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="3f048-192">Conforme vaya pasando el tiempo, toda la organización podrá confiar únicamente en Microsoft Teams para cumplir los requisitos de colaboración y comunicaciones y continuar con el **quinto paso**.</span><span class="sxs-lookup"><span data-stu-id="3f048-192">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="3f048-193">Si desea ver las nuevas características que se incluirán en Microsoft Teams, vea el [Mapa de ruta de Office 365](http://aka.ms/TeamsRoadmap).</span><span class="sxs-lookup"><span data-stu-id="3f048-193">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="3f048-194">Administrar la experiencia en paralelo</span><span class="sxs-lookup"><span data-stu-id="3f048-194">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="3f048-195">Microsoft Teams está habilitado de forma predeterminada en aquellas organizaciones que tienen suscripciones de Office 365 válidas.</span><span class="sxs-lookup"><span data-stu-id="3f048-195">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="3f048-196">Si su organización cumple el perfil del recorrido de cliente no administrado en paralelo, recomendados encarecidamente que siga por ese camino para promover una adopción orgánica de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-196">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="3f048-197">A Microsoft Teams se puede acceder a través de clientes de escritorio con navegadores web modernos que no requieren privilegio de administrador de TI (para la instalación, en este momento solo se aplica a PC) y clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="3f048-197">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="3f048-198">Todas las funcionalidades de Microsoft Teams (llamadas y chats privados, y reuniones ad hoc y programadas) y las aplicaciones están habilitadas de forma predeterminada, de manera que los usuarios pueden probar y usar las funcionalidades que mejor se adaptan a lo que necesitan.</span><span class="sxs-lookup"><span data-stu-id="3f048-198">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="3f048-199">La primera vez que se utiliza, Microsoft Teams guía a los usuarios para que elijan su aplicación de llamadas y chat preferida (Microsoft Teams o Skype Empresarial).</span><span class="sxs-lookup"><span data-stu-id="3f048-199">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="3f048-200">En caso de que su organización requiera que las nuevas herramientas, como Microsoft Teams, se deben lanzar siguiendo un proceso más controlado, se pueden tener en cuenta las siguientes opciones para su recorrido de cliente administrado en paralelo. Son estas:</span><span class="sxs-lookup"><span data-stu-id="3f048-200">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="3f048-201">Experiencia piloto y lanzamiento de Microsoft Teams para colaboración.</span><span class="sxs-lookup"><span data-stu-id="3f048-201">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="3f048-202">Vea [Crear un proyecto piloto de Microsoft Teams junto a Skype Empresarial](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="3f048-202">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="3f048-203">Lanzamiento de Microsoft Teams para reuniones</span><span class="sxs-lookup"><span data-stu-id="3f048-203">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="3f048-204">Lanzamiento de Microsoft Teams para llamadas</span><span class="sxs-lookup"><span data-stu-id="3f048-204">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="3f048-205">Experiencia piloto y lanzamiento de Microsoft Teams para colaboración</span><span class="sxs-lookup"><span data-stu-id="3f048-205">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="3f048-206">En esencia, Microsoft Teams se creó en torno al chat persistente y la integración con Office 365 mediante la mejora de Grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f048-206">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="3f048-207">Dado que, de forma predeterminada, los usuarios de su organización que tienen una licencia de suscripción a Office 365 apta están habilitado para poder usar Microsoft Teams, se crea una experiencia piloto limitada de Microsoft Teams en la que se deshabilita la licencia de Microsoft Teams de todos los usuarios que no pertenecen a este grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="3f048-207">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="3f048-208">Para centrarse en el lanzamiento de Microsoft Teams como solución de chat privado y colaboración, y reducir la confusión que genera en los usuarios tener varias funcionalidades que se solapan con Skype Empresarial, puede cambiar las siguientes configuraciones en el nivel de inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f048-208">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="3f048-209">Para cambiar estas configuraciones de Office 365, vea [Configurar Microsoft Teams en su organización de Office 365](Office-365-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3f048-209">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f048-210">Sección</span><span class="sxs-lookup"><span data-stu-id="3f048-210">Section</span></span></th>
<th align="left"><span data-ttu-id="3f048-211">Configuración</span><span class="sxs-lookup"><span data-stu-id="3f048-211">Setting</span></span></th>
<th align="left"><span data-ttu-id="3f048-212">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f048-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="3f048-213">Llamadas y reuniones</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-213">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="3f048-214">Permitir la programación de reuniones privadas: <strong>Desactivado</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-214">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="3f048-215">Permitir la programación de reuniones de canal: <strong>Desactivado</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-215">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="3f048-216">Permitir llamada privada: <strong>Desactivado</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-216">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="3f048-217">Al deshabilitar esta opción, los usuarios no podrán programar reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="3f048-217">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="3f048-218">Al deshabilitar esta opción, los usuarios no podrán programar reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="3f048-218">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="3f048-219">Al deshabilitar esta opción, los usuarios no podrán hacer llamadas privadas (audio y vídeo)</span><span class="sxs-lookup"><span data-stu-id="3f048-219">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3f048-220">Nota</span><span class="sxs-lookup"><span data-stu-id="3f048-220">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3f048-221">Debe deshabilitar las llamadas privadas a usuarios profesionales, de empresa e invitados (si el acceso de invitado existe en su organización).</span><span class="sxs-lookup"><span data-stu-id="3f048-221">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="3f048-222">Con esta configuración, se les puede mostrar a los usuarios cómo funcionan las reuniones en Microsoft Teams al promover el uso de las reuniones de canal ad hoc y al permitir el uso de la voz, el vídeo y la pantalla compartida como parte de la experiencia de colaboración moderna.</span><span class="sxs-lookup"><span data-stu-id="3f048-222">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="3f048-223">Los usuarios finales también se benefician de las funcionalidades de chat privado, multiplataforma y persistencia de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-223">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="3f048-224">Cuando la experiencia piloto de Microsoft Teams se desarrolla con éxito para el chat privado y la colaboración, se puede seguir con un amplio lanzamiento en toda la organización proporcionando licencias de Microsoft Teams a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f048-224">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3f048-225">Nota</span><span class="sxs-lookup"><span data-stu-id="3f048-225">Note</span></span></p></td>
<td align="left"><span data-ttu-id="3f048-226">Durante el piloto y en la fase dos, cuando se habilita el chat privado, un usuario de Microsoft Teams que chatee con un usuario de Skype Empresarial no podrá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f048-226">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="3f048-227">
- Iniciar videollamada desde una sesión de chat</span><span class="sxs-lookup"><span data-stu-id="3f048-227">
- Start video call from a chat session</span></span><br><span data-ttu-id="3f048-228">
- Transferir archivos</span><span class="sxs-lookup"><span data-stu-id="3f048-228">
- Transfers files</span></span> <br><span data-ttu-id="3f048-229">
- Iniciar una llamada con varios participantes desde la sesión de chat</span><span class="sxs-lookup"><span data-stu-id="3f048-229">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="3f048-230">
- Los usuarios no podrán iniciar una sesión de escritorio compartido</span><span class="sxs-lookup"><span data-stu-id="3f048-230">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="3f048-231">Lanzamiento de Microsoft Teams para reuniones</span><span class="sxs-lookup"><span data-stu-id="3f048-231">Rollout of Teams for meetings</span></span>

<span data-ttu-id="3f048-232">A medida que los usuarios se vayan acostumbrando a colaborar con Microsoft Teams, se considerará a las reuniones programadas como la siguiente funcionalidad en ser habilitada en la organización.</span><span class="sxs-lookup"><span data-stu-id="3f048-232">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3f048-233">Nota</span><span class="sxs-lookup"><span data-stu-id="3f048-233">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3f048-234">Los organizadores de las reuniones programadas deben tener sus buzones de correo en Exchange Online multiempresa (o en Exchange Online Dedicated vNext).</span><span class="sxs-lookup"><span data-stu-id="3f048-234">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="3f048-235">Las siguientes opciones se pueden configurar en el nivel de inquilino para habilitar las reuniones programadas en Microsoft Teams. Estas opciones solo se aplican a usuarios profesionales y de empresa.</span><span class="sxs-lookup"><span data-stu-id="3f048-235">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f048-236">Sección</span><span class="sxs-lookup"><span data-stu-id="3f048-236">Section</span></span></th>
<th align="left"><span data-ttu-id="3f048-237">Configuración</span><span class="sxs-lookup"><span data-stu-id="3f048-237">Setting</span></span></th>
<th align="left"><span data-ttu-id="3f048-238">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f048-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="3f048-239">Llamadas y reuniones</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-239">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="3f048-240">Permitir la programación de reuniones privadas: <strong>Activado</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-240">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="3f048-241">Permitir la programación de reuniones de canal: <strong>Activado</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-241">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="3f048-242">Al habilitar esta opción, los usuarios podrán programar reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="3f048-242">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="3f048-243">Al habilitar esta opción, los usuarios podrán programar reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="3f048-243">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f048-244">Las reuniones programadas se pueden organizar a través del cliente de escritorio de Microsoft Teams, un navegador o Microsoft Outlook con el complemento de reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-244">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="3f048-245">Una vez que se habilitan las reuniones programadas de Microsoft Teams, recomendamos que se comience a mostrar a los usuarios cómo se crean reuniones de Microsoft Teams o cómo se actualizan reuniones existentes de Skype Empresarial para convertirlas en reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-245">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="3f048-246">Lanzamiento de Microsoft Teams para llamadas</span><span class="sxs-lookup"><span data-stu-id="3f048-246">Rollout of Teams for calling</span></span>

<span data-ttu-id="3f048-247">Las llamadas privadas es la funcionalidad de Microsoft Teams que estará en continuo desarrollo y, a lo largo del tiempo, se convertirá en un reemplazo muy atractivo de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f048-247">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="3f048-248">Cuando su organización considere que las funcionalidades de llamada privada de Microsoft Teams cumplen los requisitos empresariales clave, se podrán configurar las siguientes opciones a nivel de inquilino para habilitar las llamadas privadas en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-248">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f048-249">Sección</span><span class="sxs-lookup"><span data-stu-id="3f048-249">Section</span></span></th>
<th align="left"><span data-ttu-id="3f048-250">Configuración</span><span class="sxs-lookup"><span data-stu-id="3f048-250">Setting</span></span></th>
<th align="left"><span data-ttu-id="3f048-251">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f048-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="3f048-252">Llamadas y reuniones</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-252">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="3f048-253">Permitir llamada privada: <strong>Activado</strong></span><span class="sxs-lookup"><span data-stu-id="3f048-253">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="3f048-254">Al habilitar esta opción, los usuarios podrán hacer llamadas privadas (audio y vídeo).</span><span class="sxs-lookup"><span data-stu-id="3f048-254">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3f048-255">Nota</span><span class="sxs-lookup"><span data-stu-id="3f048-255">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3f048-256">Permitir que los usuarios chateen en privado: al habilitar esta opción, los usuarios podrán chatear con otros usuarios en privado.</span><span class="sxs-lookup"><span data-stu-id="3f048-256">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="3f048-257">En esta fase, a todos los usuarios se les debe indicar que elijan Microsoft Teams como la aplicación de llamadas preferida.</span><span class="sxs-lookup"><span data-stu-id="3f048-257">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="3f048-258">Al tener habilitadas las llamadas privadas, Microsoft Teams ofrecerá todas las funcionalidades que proporciona ahora Skype Empresarial y los usuarios podrán comenzar a usar Microsoft Teams para cumplir todos los requisitos de colaboración y comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="3f048-258">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="3f048-259"><strong>Próxima acción:</strong> cuando Microsoft Teams esté funcionando en paralelo con Skype Empresarial, [genere nuevos valores a través de la adopción de usuarios](continue-journey.md), a la vez que sigue su recorrido de Skype Empresarial a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f048-259"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>