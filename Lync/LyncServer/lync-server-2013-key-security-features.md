---
title: 'Lync Server 2013: características de seguridad clave'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="6d8c6-102">Características de seguridad clave de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d8c6-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d8c6-103">_**Última modificación del tema:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="6d8c6-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="6d8c6-104">Lync Server 2013 incluye varias características de seguridad, entre las que se incluyen la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="6d8c6-105">Este artículo proporciona información general de alto nivel sobre la seguridad de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="6d8c6-106">Características de seguridad clave de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d8c6-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="6d8c6-107">La seguridad es un tema muy amplio.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-107">Security is a very broad topic.</span></span> <span data-ttu-id="6d8c6-108">La seguridad alcanza todas las características de Lync Server 2013, así como las bases de datos, los servicios y el hardware que componen un ecosistema de Lync.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="6d8c6-109">En este artículo, se describen algunas de las características de Lync Server 2013 especialmente diseñadas para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="6d8c6-110">Herramientas de planeación y diseño</span><span class="sxs-lookup"><span data-stu-id="6d8c6-110">Planning and Design Tools</span></span>

<span data-ttu-id="6d8c6-111">Lync Server 2013 ofrece dos herramientas para facilitar la planeación y el diseño y reducir la posibilidad de que se configuren los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="6d8c6-112">La herramienta de planeación de la **topología** automatiza gran parte del proceso de diseño de la topología.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="6d8c6-113">Puede exportar los resultados de la herramienta de planeación a Topology Builder, que es la herramienta necesaria para instalar cada servidor que ejecute Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="6d8c6-114">El **Generador de topologías** almacena toda la información de configuración en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="6d8c6-115">Para obtener más información sobre estas herramientas, consulte [planificación de Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="6d8c6-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="6d8c6-116">Almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="6d8c6-116">Central Management Store</span></span>

<span data-ttu-id="6d8c6-117">En Lync Server 2013, los datos de configuración de los servidores y los servicios forman parte del almacén central de administración.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="6d8c6-118">El almacén central de administración proporciona un sólido almacenamiento schematized de los datos necesarios para definir, configurar, mantener, administrar, describir y utilizar una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="6d8c6-119">También comprueba los datos para asegurarse de que la configuración es coherente.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="6d8c6-120">Todos los cambios realizados a esta configuración se producen en el almacén de administración central, excepto los problemas de "sin sincronizar".</span><span class="sxs-lookup"><span data-stu-id="6d8c6-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="6d8c6-p104">Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluyendo los servidores perimetrales y las aplicaciones de sucursal con funciones de supervivencia. Un servicio que se ejecuta de forma predeterminada en el contexto del servicio de red es el encargado de administrar la replicación, de modo que los permisos y derechos se reducen a los de un simple usuario del equipo.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-p104">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances. Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="6d8c6-123">Autenticación de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="6d8c6-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="6d8c6-124">En Lync Server 2013, se puede configurar la autenticación entre servidores mediante el protocolo de autorización abierta (OAuth).</span><span class="sxs-lookup"><span data-stu-id="6d8c6-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="6d8c6-125">Por ejemplo, puede configurar Lync Server 2013 para que se autentique con un servidor que ejecute Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="6d8c6-126">Con el protocolo OAuth, Lync Server y el servidor Exchange pueden confiar entre sí.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="6d8c6-127">Esto proporciona la posibilidad de integrar los productos de forma sencilla.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="6d8c6-128">Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="6d8c6-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="6d8c6-129">Administración basada en Windows PowerShell e interfaz de administración basada en web</span><span class="sxs-lookup"><span data-stu-id="6d8c6-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="6d8c6-130">Lync Server 2013 ofrece una interfaz de administración eficaz, creada en la interfaz de línea de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="6d8c6-131">Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="6d8c6-132">Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="6d8c6-133">Para obtener más información sobre la compatibilidad de administración de Windows PowerShell en Lync Server 2013, vea [consola de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="6d8c6-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="6d8c6-134">Control de acceso basado en roles (RBAC)</span><span class="sxs-lookup"><span data-stu-id="6d8c6-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="6d8c6-135">Microsoft Lync Server 2013 ofrece control de acceso basado en roles (RBAC) que permite delegar tareas administrativas a la vez que se mantienen los altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="6d8c6-136">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="6d8c6-137">Lync Server 2013 introduce la capacidad de crear un nuevo rol y también la capacidad de modificar un rol existente.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="6d8c6-138">Para obtener más información, vea [planificación de control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="6d8c6-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="6d8c6-139">Traducción de direcciones de red (NAT)</span><span class="sxs-lookup"><span data-stu-id="6d8c6-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="6d8c6-140">Lync Server 2013 no admite el uso de la traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero admite la colocación de la interfaz externa del servicio perimetral de acceso, el servicio perimetral de conferencias web y el servicio perimetral a/V tras una enrutador o firewall que realiza la traducción de direcciones de red (NAT) para topologías de servidores perimetrales individuales y a escala.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="6d8c6-141">Si hay varios servidores perimetrales tras un equilibrador de carga de hardware, no se podrá utilizar NAT.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="6d8c6-142">Si hay varios servidores perimetrales que utilizan NAT en sus interfaces externas, se necesitará aplicar equilibrio de carga de sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="6d8c6-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="6d8c6-143">El equilibrio de carga de DNS permite, al mismo tiempo, reducir el número de direcciones IP públicas por servidor perimetral en grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="6d8c6-144">Para obtener más información, consulte[planear el acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6d8c6-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d8c6-145">Si su empresa se federa con otra que tenga una implementación de Microsoft Office Communications Server 2007 y necesita utilizar audio/vídeo entre su empresa y la empresa federada, los requisitos de los puertos serán los correspondientes a la versión antigua de servidores perimetrales que se haya implementado.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="6d8c6-146">Por ejemplo, los intervalos de puertos necesarios para esas versiones anteriores deben abrirse en ambas empresas hasta que el socio federado actualice sus servidores perimetrales a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="6d8c6-147">En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="6d8c6-148">Certificados simplificados para servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="6d8c6-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="6d8c6-149">El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="6d8c6-150">Ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing</span><span class="sxs-lookup"><span data-stu-id="6d8c6-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="6d8c6-151">Lync Server 2013 se ha diseñado y desarrollado en conformidad con el ciclo de vida de desarrollo de seguridad de Microsoft Trustworthy Computing (SDL <http://go.microsoft.com/fwlink/?linkid=68761>), que se describe en.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="6d8c6-152">**Confianza por diseño**   el primer paso en la creación de un sistema de comunicaciones unificado más seguro era diseñar modelos de amenazas y probar cada característica tal como se diseñó.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="6d8c6-153">Además, Microsoft realiza pruebas fuera del comportamiento diseñado para encontrar vulnerabilidades de seguridad derivadas del comportamiento inesperado del producto.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="6d8c6-154">Se incorporaron muchas mejoras relacionadas con la seguridad, tanto al proceso como a las prácticas de codificación.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="6d8c6-155">Las herramientas de tiempo de compilación detectan excesos de almacenaje y otras amenazas de seguridad antes de que el código se incorpore al producto final.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="6d8c6-156">Obviamente, es imposible realizar diseños contra amenazas de seguridad desconocidas.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="6d8c6-157">Ningún sistema puede garantizar la seguridad total.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-157">No system can guarantee complete security.</span></span> <span data-ttu-id="6d8c6-158">Sin embargo, dado que el desarrollo del producto ha adoptado principios de diseño seguros desde el principio, Lync Server 2013 incorpora tecnologías de seguridad estándar del sector como parte fundamental de su arquitectura.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="6d8c6-159">**Digno de confianza**de forma predeterminada, las comunicaciones de red en Lync Server 2013 están cifradas.   </span><span class="sxs-lookup"><span data-stu-id="6d8c6-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="6d8c6-160">Como todos los servidores usan certificados y autenticación Kerberos, TLS, protocolo seguro de transporte en tiempo real (SRTP) y otras técnicas de cifrado estándar de la industria, incluido el cifrado estándar de cifrado avanzado de 128 bits (AES), casi todas las Lync Los datos del servidor están protegidos en la red.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="6d8c6-161">Además, el control de acceso basado en roles permite implementar servidores que ejecuten Lync Server 2013 para que cada rol de servidor solo ejecute los servicios y solo tenga los permisos relacionados con esos servicios, que son adecuados para el rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="6d8c6-162">**Confianza por implementación**   toda la documentación de Lync Server 2013 incluye las prácticas recomendadas y las recomendaciones para ayudarle a determinar y configurar los niveles de seguridad óptimos para su implementación y evaluar los riesgos de seguridad de activar no predeterminado Opciones.</span><span class="sxs-lookup"><span data-stu-id="6d8c6-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

