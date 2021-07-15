---
title: Preparar la red de la organización para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Descubra cómo preparar la red de su organización para Microsoft Teams, incluidos los requisitos de red, la optimización de red y los requisitos de ancho de banda.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420835"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="aa37d-103">Preparar la red de la organización para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="aa37d-104">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="aa37d-104">Network requirements</span></span>

<span data-ttu-id="aa37d-105">Si ya ha [optimizado la red para Microsoft 365 u Office 365](/Office365/Enterprise/assessing-network-connectivity), probablemente estará listo para usar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aa37d-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="aa37d-106">En cualquier caso, y especialmente si tiene que implementar Teams en poco tiempo como su primera carga de trabajo de Microsoft 365 u Office 365 con el fin de dar cabida a **trabajadores remotos**, lea lo siguiente antes de la implementación:</span><span class="sxs-lookup"><span data-stu-id="aa37d-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="aa37d-107">¿Tienen todas sus ubicaciones acceso a Internet para conectarse a Microsoft 365 u Office 365?</span><span class="sxs-lookup"><span data-stu-id="aa37d-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="aa37d-108">Además del tráfico web normal, asegúrese de que ha abierto los puertos TCP y las direcciones IP que aparecen para Teams en [Intervalos de direcciones IP y URL de Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="aa37d-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="aa37d-109">Si necesita federar con Skype Empresarial, ya sea local o en línea, tendrá que configurar algunos registros DNS adicionales.</span><span class="sxs-lookup"><span data-stu-id="aa37d-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="aa37d-110">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="aa37d-110">DNS record</span></span>  |<span data-ttu-id="aa37d-111">Servicio</span><span class="sxs-lookup"><span data-stu-id="aa37d-111">Service</span></span>  |<span data-ttu-id="aa37d-112">Protocolo</span><span class="sxs-lookup"><span data-stu-id="aa37d-112">Protocol</span></span>  |<span data-ttu-id="aa37d-113">Prioridad</span><span class="sxs-lookup"><span data-stu-id="aa37d-113">Priority</span></span>  |<span data-ttu-id="aa37d-114">Peso</span><span class="sxs-lookup"><span data-stu-id="aa37d-114">Weight</span></span>  |<span data-ttu-id="aa37d-115">Puerto</span><span class="sxs-lookup"><span data-stu-id="aa37d-115">Port</span></span>  |<span data-ttu-id="aa37d-116">Destino</span><span class="sxs-lookup"><span data-stu-id="aa37d-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="aa37d-117">SRV</span><span class="sxs-lookup"><span data-stu-id="aa37d-117">SRV</span></span>     |<span data-ttu-id="aa37d-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="aa37d-118">sipfederationtls</span></span>     |<span data-ttu-id="aa37d-119">TCP</span><span class="sxs-lookup"><span data-stu-id="aa37d-119">TCP</span></span>     |<span data-ttu-id="aa37d-120">100</span><span class="sxs-lookup"><span data-stu-id="aa37d-120">100</span></span>     |<span data-ttu-id="aa37d-121">1</span><span class="sxs-lookup"><span data-stu-id="aa37d-121">1</span></span>     |<span data-ttu-id="aa37d-122">5061</span><span class="sxs-lookup"><span data-stu-id="aa37d-122">5061</span></span>     |<span data-ttu-id="aa37d-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="aa37d-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="aa37d-124">¿Tiene un dominio comprobado de Microsoft 365 u Office 365 (por ejemplo, contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="aa37d-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="aa37d-125">Si su organización no ha implementado Microsoft 365 u Office 365, consulte esta [Introducción](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="aa37d-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="aa37d-126">Si su organización aún no ha agregado o configurado un dominio comprobado para Microsoft 365 u Office 365, consulte las [Preguntas más frecuentes de dominios](/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="aa37d-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="aa37d-127">¿Ha implementado su organización Exchange Online y SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="aa37d-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="aa37d-128">Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="aa37d-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="aa37d-129">Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="aa37d-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="aa37d-130">Cuando compruebe que cumple estos requisitos de red, puede que esté listo para la [Implementación de Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aa37d-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="aa37d-131">Tanto si está en una gran multinacional como si sabe que puede tener algunas limitaciones de red, le será útil seguir leyendo para saber cómo evaluar y optimizar su red para Teams.</span><span class="sxs-lookup"><span data-stu-id="aa37d-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa37d-132">**Para instituciones educativas**: si su organización es una institución educativa y usa un Sistema de información de estudiantes (SIS), [implemente School Data Sync](/schooldatasync/) antes de implementar Teams.</span><span class="sxs-lookup"><span data-stu-id="aa37d-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="aa37d-133">**Ejecución local de Skype Empresarial Server**: si su organización ejecuta Skype Empresarial Server (o Lync Server) de forma local, deberá [Configurar Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar su directorio local con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa37d-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="aa37d-134">Procedimiento recomendado: Supervisar su red con el Panel de calidad de llamadas y el análisis de llamadas</span><span class="sxs-lookup"><span data-stu-id="aa37d-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="aa37d-135">Use el [Panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) para sacar conclusiones sobre la calidad de las llamadas y reuniones en Teams.</span><span class="sxs-lookup"><span data-stu-id="aa37d-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="aa37d-136">El Panel de calidad de llamadas le permite seguir de cerca la calidad, la confiabilidad y la experiencia del usuario para optimizar su red.</span><span class="sxs-lookup"><span data-stu-id="aa37d-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="aa37d-137">El Panel de calidad de llamadas examina la telemetría agregada de toda la organización. Esto puede sacar a la luz patrones generales que permitan identificar problemas y planear soluciones.</span><span class="sxs-lookup"><span data-stu-id="aa37d-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="aa37d-138">Además, el Panel de calidad de llamadas proporciona informes de métricas enriquecidos que proporcionan información sobre la calidad, la confiabilidad y la experiencia del usuario generales.</span><span class="sxs-lookup"><span data-stu-id="aa37d-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="aa37d-139">Usará las herramientas de [análisis de llamadas](set-up-call-analytics.md) para investigar los problemas de llamada y reunión de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="aa37d-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="aa37d-140">Optimización de la red</span><span class="sxs-lookup"><span data-stu-id="aa37d-140">Network optimization</span></span>

<span data-ttu-id="aa37d-141">Las siguientes tareas son opcionales. No son necesarias para implementar Teams, especialmente si es una pequeña empresa y ya ha implementado Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa37d-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aa37d-142">Use esta guía para optimizar el rendimiento de la red y de Teams o si sabe que tiene algunas limitaciones de red.</span><span class="sxs-lookup"><span data-stu-id="aa37d-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="aa37d-143">Es posible que quiera realizar una optimización de red adicional si:</span><span class="sxs-lookup"><span data-stu-id="aa37d-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="aa37d-144">Teams se ejecuta lentamente (quizás tenga ancho de banda insuficiente)</span><span class="sxs-lookup"><span data-stu-id="aa37d-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="aa37d-145">Las llamadas siguen desconectándose (puede deberse a firewalls o bloqueadores de proxy)</span><span class="sxs-lookup"><span data-stu-id="aa37d-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="aa37d-146">Las llamadas tienen distorsiones, se cortan o los interlocutores suenan como robots (puede haber fluctuaciones o pérdida de paquetes)</span><span class="sxs-lookup"><span data-stu-id="aa37d-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="aa37d-147">Para obtener una explicación más detallada sobre la optimización de redes, con instrucciones para identificar y corregir los problemas de red, consulte [Principios de conectividad de red de Microsoft 365 y Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span><span class="sxs-lookup"><span data-stu-id="aa37d-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="aa37d-148">Tarea de optimización de red</span><span class="sxs-lookup"><span data-stu-id="aa37d-148">Network optimization task</span></span></th>
<th><span data-ttu-id="aa37d-149">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa37d-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aa37d-150">Planeamiento de red</span><span class="sxs-lookup"><span data-stu-id="aa37d-150">Network planner</span></span></td>
<td><p><span data-ttu-id="aa37d-151">Si necesita ayuda para evaluar la red, incluidos los cálculos de ancho de banda y los requisitos de red en las ubicaciones físicas de su organización, consulte la herramienta <a href="/microsoftteams/network-planner">Planeamiento de red</a>, en el <a href="https://admin.teams.microsoft.com">Centro de administración de Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="aa37d-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="aa37d-152">Cuando proporciona el uso de Teams y los detalles de la red, el Planeamiento de red calcula los requisitos de red para implementar Teams y voz en la nube en las ubicaciones físicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="aa37d-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="aa37d-153">Para ver un escenario de ejemplo, consulte <a href="/microsoftteams/tutorial-network-planner-example">Uso del Planeamiento de red: escenario de ejemplo</a>.</span><span class="sxs-lookup"><span data-stu-id="aa37d-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa37d-154">Asesor para Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="aa37d-155">El <a href="/microsoftteams/use-advisor-teams-roll-out">Asesor de Teams</a> forma parte del <a href="https://admin.teams.microsoft.com">Centro de administración de Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="aa37d-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="aa37d-156">Evalúa el entorno de Microsoft 365 u Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams.</span><span class="sxs-lookup"><span data-stu-id="aa37d-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa37d-157">Resolución de nombres externos</span><span class="sxs-lookup"><span data-stu-id="aa37d-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="aa37d-158">Asegúrese de que todos los equipos cliente que ejecuten el cliente de Teams puedan resolver consultas DNS externas para detectar los servicios proporcionados por Microsoft 365 u Office 365 y de que sus firewall no evitan el acceso.</span><span class="sxs-lookup"><span data-stu-id="aa37d-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="aa37d-159">Para obtener información sobre cómo configurar puertos de firewall, vaya a <a href="/microsoftteams/office-365-urls-ip-address-ranges">Direcciones URL e intervalos IP de Microsoft 365 y Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="aa37d-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa37d-160">Mantener la conservación de sesiones</span><span class="sxs-lookup"><span data-stu-id="aa37d-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="aa37d-161">Asegúrese de que el firewall no cambia las direcciones o puertos de Traducción de Direcciones de Red (NAT) asignados para UDP.</span><span class="sxs-lookup"><span data-stu-id="aa37d-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="aa37d-162">Validar el tamaño del grupo NAT</span><span class="sxs-lookup"><span data-stu-id="aa37d-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="aa37d-163">Valide el tamaño de grupo de Traducción de Direcciones de Red (NAT) necesario para la conectividad de usuario.</span><span class="sxs-lookup"><span data-stu-id="aa37d-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="aa37d-164">Cuando varios usuarios y dispositivos obtienen acceso a Microsoft 365 u Office 365 mediante la <a href="/office365/enterprise/nat-support-with-office-365">Traducción de Direcciones de Red (NAT) o la Traducción de Direcciones de Puertos (PAT)</a>, debe asegurarse de que los dispositivos que se encuentren detrás de cada dirección IP enrutable de forma pública no superen el número admitido.</span><span class="sxs-lookup"><span data-stu-id="aa37d-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="aa37d-165">Asegúrese de que se asignan direcciones IP públicas adecuadas a los grupos de NAT para evitar el agotamiento de puertos.</span><span class="sxs-lookup"><span data-stu-id="aa37d-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="aa37d-166">El agotamiento del puertos contribuye a que los usuarios y dispositivos internos no puedan conectarse al servicio de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa37d-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa37d-167">Enrutamiento a centros de datos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="aa37d-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="aa37d-168"><a href="/office365/enterprise/client-connectivity">Implemente el enrutamiento más eficaz a los centros de datos de Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="aa37d-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="aa37d-169">Identifique las ubicaciones que pueden usar puntos de salida locales o regionales para conectarse a la red de Microsoft de la manera más eficiente posible.</span><span class="sxs-lookup"><span data-stu-id="aa37d-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa37d-170">Detección de Intrusiones y Guía de Prevención</span><span class="sxs-lookup"><span data-stu-id="aa37d-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="aa37d-171">Si su entorno tiene implementado un sistema de <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Detección de Intrusiones</a> o un Sistema de Prevención (IDS/IPS) para obtener una capa adicional de seguridad para conexiones salientes, asegúrese de permitir todas las direcciones URL de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa37d-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa37d-172">Configurar una VPN de túnel dividido</span><span class="sxs-lookup"><span data-stu-id="aa37d-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="aa37d-173">Le recomendamos que proporcione una ruta alternativa para el tráfico de Teams que omita la red privada virtual (VPN). Esto se conoce como <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN de túnel dividido</a>.</span><span class="sxs-lookup"><span data-stu-id="aa37d-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="aa37d-174">De esta forma, el tráfico de Microsoft 365 u Office 365 no pasa por la VPN, sino que va directamente a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa37d-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aa37d-175">Esto tiene un impacto positivo en la calidad de Teams y reduce la carga desde los dispositivos VPN y la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="aa37d-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="aa37d-176">Para implementar una VPN de túnel dividido, consulte con su proveedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="aa37d-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="aa37d-177">Otras razones por las que recomendamos omitir la VPN:</span><span class="sxs-lookup"><span data-stu-id="aa37d-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="aa37d-178">Por lo general las VPN no se diseñan ni se configuran para admitir elementos multimedia en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="aa37d-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="aa37d-179">Es posible que algunas VPN tampoco admitan UDP (necesario para Teams).</span><span class="sxs-lookup"><span data-stu-id="aa37d-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="aa37d-180">Las VPN también introducen una capa adicional de cifrado en el tráfico multimedia que ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="aa37d-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="aa37d-181">La conectividad con Teams puede no ser eficiente debido al tráfico de redirección al origen que pasa a través de un dispositivo VPN.</span><span class="sxs-lookup"><span data-stu-id="aa37d-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa37d-182">Implementar QoS</span><span class="sxs-lookup"><span data-stu-id="aa37d-182">Implement QoS</span></span></td>
<td><span data-ttu-id="aa37d-183"><a href="/microsoftteams/qos-in-teams">Use Calidad del Servicio (QoS)</a> para configurar la prioridad de paquetes.</span><span class="sxs-lookup"><span data-stu-id="aa37d-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="aa37d-184">Esto mejorará la calidad de la llamada en Teams y le ayudará a supervisar y solucionar problemas de calidad de llamada.</span><span class="sxs-lookup"><span data-stu-id="aa37d-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="aa37d-185">QoS debe implementarse en todos los segmentos de una red administrada.</span><span class="sxs-lookup"><span data-stu-id="aa37d-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="aa37d-186">Incluso si una red se aprovisionó correctamente para el ancho de banda, QoS proporciona mitigación de riesgos en caso de eventos de red inesperados.</span><span class="sxs-lookup"><span data-stu-id="aa37d-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="aa37d-187">Con QoS, el tráfico de voz tiene prioridad para que los eventos inesperados no afecten negativamente a la calidad.</span><span class="sxs-lookup"><span data-stu-id="aa37d-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa37d-188">Optimizar la Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="aa37d-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="aa37d-189">Como sucede con las redes VPN, las redes Wi-Fi no se han diseñado ni configurado necesariamente para admitir archivos multimedia en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="aa37d-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="aa37d-190">Planificar una red Wi-Fi u optimizarla para que admita Teams es un aspecto muy relevante en la implementación de calidad.</span><span class="sxs-lookup"><span data-stu-id="aa37d-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="aa37d-191">Tenga en cuenta los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="aa37d-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa37d-192">Implementar QoS o WiFi Multimedia (WMM) le asegura que el tráfico multimedia reciba la prioridad adecuada a través de las redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="aa37d-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="aa37d-193">Planear y optimizar las bandas Wi-Fi y la ubicación del punto de acceso.</span><span class="sxs-lookup"><span data-stu-id="aa37d-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="aa37d-194">El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero a los puntos de acceso normalmente también les afectan otros dispositivos de consumidores que funcionan en esa gama.</span><span class="sxs-lookup"><span data-stu-id="aa37d-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="aa37d-195">El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura.</span><span class="sxs-lookup"><span data-stu-id="aa37d-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="aa37d-196">Los puntos de conexión también necesitan admitir esa gama y se deben configurar para poder aprovechar esas bandas de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="aa37d-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="aa37d-197">Si usa redes Wi-Fi de doble banda, considere la posibilidad de implementar "band steering".</span><span class="sxs-lookup"><span data-stu-id="aa37d-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="aa37d-198"><em>Band steering</em> es una técnica que implementan los proveedores Wi-Fi para que los clientes de doble banda usen el intervalo de 5 GHz.</span><span class="sxs-lookup"><span data-stu-id="aa37d-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="aa37d-199">Cuando los puntos de acceso del mismo canal están demasiado cerca entre sí, pueden generar superposición de señales y competir sin pretenderlo, lo que daría lugar a una mala experiencia para el usuario.</span><span class="sxs-lookup"><span data-stu-id="aa37d-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="aa37d-200">Asegúrese de que los puntos de acceso que están próximos entre ellos se encuentran en canales que no se superponen.</span><span class="sxs-lookup"><span data-stu-id="aa37d-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="aa37d-201">Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="aa37d-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="aa37d-202">Consulte a su proveedor de Wi-Fi para obtener instrucciones específicas.</span><span class="sxs-lookup"><span data-stu-id="aa37d-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="aa37d-203">Requisitos de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="aa37d-203">Bandwidth requirements</span></span>

<span data-ttu-id="aa37d-204">Teams está concebido para ofrece las mejores posibilidades de uso compartido de audio, vídeo y contenido, independientemente de las condiciones de su red.</span><span class="sxs-lookup"><span data-stu-id="aa37d-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="aa37d-205">Dicho esto, cuando el ancho de banda es insuficiente, Teams da prioridad a la calidad de audio sobre la de vídeo.</span><span class="sxs-lookup"><span data-stu-id="aa37d-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="aa37d-206">Cuando el ancho de banda no está limitado, Teams optimiza la calidad multimedia, incluido el audio de alta fidelidad, una resolución de vídeo de hasta 1080p y hasta 30 fps (fotogramas por segundo) para vídeo y contenido.</span><span class="sxs-lookup"><span data-stu-id="aa37d-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="aa37d-207">Esta tabla describe cómo Teams usa el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="aa37d-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="aa37d-208">Teams siempre hace un uso conservador del ancho de banda y puede ofrecer una calidad de vídeo de alta definición con menos de 1,5 Mb/s.</span><span class="sxs-lookup"><span data-stu-id="aa37d-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="aa37d-209">El consumo real de ancho de banda en cada llamada de audio o vídeo o reunión varía en función de varios factores, como el diseño de vídeo, la resolución de vídeo y los fotogramas por segundo del vídeo.</span><span class="sxs-lookup"><span data-stu-id="aa37d-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="aa37d-210">Cuando se disponga de más ancho de banda, la calidad y el uso se incrementarán para proporcionar la mejor experiencia.</span><span class="sxs-lookup"><span data-stu-id="aa37d-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="aa37d-211">**Modalidad**</span><span class="sxs-lookup"><span data-stu-id="aa37d-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="aa37d-212">**Requisitos de ancho de banda (velocidad de bits KB/s subida/bajada)**</span><span class="sxs-lookup"><span data-stu-id="aa37d-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="aa37d-213">**Mínimo**</span><span class="sxs-lookup"><span data-stu-id="aa37d-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="aa37d-214">**Recomendado**</span><span class="sxs-lookup"><span data-stu-id="aa37d-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="aa37d-215">**Mejor rendimiento**</span><span class="sxs-lookup"><span data-stu-id="aa37d-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="aa37d-216">**Audio**</span><span class="sxs-lookup"><span data-stu-id="aa37d-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-217">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="aa37d-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-218">10/10</span><span class="sxs-lookup"><span data-stu-id="aa37d-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-219">58/58</span><span class="sxs-lookup"><span data-stu-id="aa37d-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-220">76/76</span><span class="sxs-lookup"><span data-stu-id="aa37d-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-221">Reuniones</span><span class="sxs-lookup"><span data-stu-id="aa37d-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-222">10/10</span><span class="sxs-lookup"><span data-stu-id="aa37d-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-223">58/58</span><span class="sxs-lookup"><span data-stu-id="aa37d-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-224">76/76</span><span class="sxs-lookup"><span data-stu-id="aa37d-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="aa37d-225">**Vídeo**</span><span class="sxs-lookup"><span data-stu-id="aa37d-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-226">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="aa37d-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-227">150/150</span><span class="sxs-lookup"><span data-stu-id="aa37d-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-228">1 500/1 500</span><span class="sxs-lookup"><span data-stu-id="aa37d-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-229">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="aa37d-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-230">Reuniones</span><span class="sxs-lookup"><span data-stu-id="aa37d-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-231">150/200</span><span class="sxs-lookup"><span data-stu-id="aa37d-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-232">2 500/4 000</span><span class="sxs-lookup"><span data-stu-id="aa37d-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-233">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="aa37d-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="aa37d-234">**Pantalla compartida**</span><span class="sxs-lookup"><span data-stu-id="aa37d-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-235">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="aa37d-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-236">200/200</span><span class="sxs-lookup"><span data-stu-id="aa37d-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-237">1 500/1 500</span><span class="sxs-lookup"><span data-stu-id="aa37d-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-238">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="aa37d-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-239">Reuniones</span><span class="sxs-lookup"><span data-stu-id="aa37d-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-240">250/250</span><span class="sxs-lookup"><span data-stu-id="aa37d-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-241">2 500/2 500</span><span class="sxs-lookup"><span data-stu-id="aa37d-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-242">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="aa37d-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="aa37d-243">**Modo conferencia**</span><span class="sxs-lookup"><span data-stu-id="aa37d-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-244">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="aa37d-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-245">N/D</span><span class="sxs-lookup"><span data-stu-id="aa37d-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-246">N/D</span><span class="sxs-lookup"><span data-stu-id="aa37d-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-247">N/D</span><span class="sxs-lookup"><span data-stu-id="aa37d-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="aa37d-248">Reuniones</span><span class="sxs-lookup"><span data-stu-id="aa37d-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-249">1 000/1 500</span><span class="sxs-lookup"><span data-stu-id="aa37d-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-250">1 500/2 500</span><span class="sxs-lookup"><span data-stu-id="aa37d-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="aa37d-251">2 500/4 000</span><span class="sxs-lookup"><span data-stu-id="aa37d-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="aa37d-252">Los requisitos de ancho de banda **mínimos**, **recomendados** y para **mejor rendimiento** se basan en el uso por punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="aa37d-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="aa37d-253">Normalmente, hay un punto de conexión por usuario, como un equipo o un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="aa37d-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="aa37d-254">Sin embargo, si un usuario se une a una reunión de Teams en *ambos*, un equipo *y* un dispositivo móvil, se asocian dos puntos de conexión a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="aa37d-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="aa37d-255">Los requisitos **mínimos** de ancho de banda para videollamadas son una resolución de hasta 240p, velocidades de fotogramas de contenido de uso compartido de pantalla adaptables de 1,875 a 7,5 fps y vídeo en modo conferencia o galería grande con una resolución de hasta 540p.</span><span class="sxs-lookup"><span data-stu-id="aa37d-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="aa37d-256">Los requisitos de ancho de banda **recomendados** para las videollamadas son una resolución de hasta 1080p<sup>\*</sup>, velocidades de fotogramas de contenido de uso compartido de pantalla adaptables de 7,5 a 30 fps y vídeo en modo conferencia o galería grande con una resolución de hasta 1080p<sup>\*</sup>.</span><span class="sxs-lookup"><span data-stu-id="aa37d-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="aa37d-257">Las instrucciones de **mejor rendimiento** permiten vídeo de mayor fidelidad para reuniones de más asistentes, entornos de pérdida alta y mayor contenido de movimiento con velocidades de fotogramas de contenido de uso compartido de pantalla adaptables de 15 a 30 fps.</span><span class="sxs-lookup"><span data-stu-id="aa37d-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="aa37d-258"><sup>\*</sup>Espere una calidad de hasta 1080p, pero en función de las condiciones de la red, la resolución y la calidad del vídeo se optimizarán en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="aa37d-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="aa37d-259">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aa37d-259">Related Topics</span></span>

[<span data-ttu-id="aa37d-260">Principios de conectividad de red de Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="aa37d-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="aa37d-261">Puntos de conexión a nivel mundial: Skype Empresarial Online y Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="aa37d-262">Servidores proxy para Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="aa37d-263">Multimedia en Teams: por qué las reuniones son sencillas</span><span class="sxs-lookup"><span data-stu-id="aa37d-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="aa37d-264">Multimedia en Teams: profundizar en los flujos de medios</span><span class="sxs-lookup"><span data-stu-id="aa37d-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="aa37d-265">Modelos de identidad y autenticación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="aa37d-266">Cómo implementar Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="aa37d-267">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="aa37d-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
