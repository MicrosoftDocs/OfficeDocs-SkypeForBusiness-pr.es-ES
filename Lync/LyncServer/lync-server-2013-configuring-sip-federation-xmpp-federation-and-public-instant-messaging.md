---
title: Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="ef23f-102">Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef23f-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef23f-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ef23f-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ef23f-104">La Federación, la conectividad de mensajería instantánea pública y el protocolo de presencia y mensajería extensible (XMPP) definen una clase diferente de usuarios externos: usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="ef23f-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="ef23f-105">Los usuarios de una implementación federada de Lync Server o una implementación XMPP tienen acceso a un conjunto limitado de servicios y se autentican mediante la implementación externa.</span><span class="sxs-lookup"><span data-stu-id="ef23f-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="ef23f-106">Los usuarios remotos son miembros de su implementación de Lync Server y tienen acceso a todos los servicios ofrecidos por su implementación.</span><span class="sxs-lookup"><span data-stu-id="ef23f-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ef23f-107">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ef23f-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ef23f-108">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="ef23f-108">has been announced.</span></span> <span data-ttu-id="ef23f-109">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ef23f-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ef23f-110">La conectividad de mensajería instantánea pública es un tipo especial de Federación que permite que un cliente de Lync Server acceda a socios de mensajería instantánea pública configurados mediante la 2013 de Lync.</span><span class="sxs-lookup"><span data-stu-id="ef23f-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="ef23f-111">Los actuales Partners públicos de conectividad de mensajería instantánea son:</span><span class="sxs-lookup"><span data-stu-id="ef23f-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="ef23f-112">America Online</span><span class="sxs-lookup"><span data-stu-id="ef23f-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="ef23f-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="ef23f-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="ef23f-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="ef23f-114">Yahoo\!</span></span>

<span data-ttu-id="ef23f-115">Una configuración de conectividad de mensajería instantánea pública permite a los usuarios de Lync acceder a los usuarios de conectividad de mensajería instantánea pública de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ef23f-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="ef23f-116">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="ef23f-116">IM and Presence</span></span>

  - <span data-ttu-id="ef23f-117">Visibilidad de los contactos de conectividad de mensajería instantánea pública en el cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="ef23f-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="ef23f-118">Conversaciones de mensajería instantánea de persona a persona con contactos</span><span class="sxs-lookup"><span data-stu-id="ef23f-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="ef23f-119">Llamadas de audio y vídeo con usuarios de Windows Live</span><span class="sxs-lookup"><span data-stu-id="ef23f-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="ef23f-120">La Federación de Lync Server define un contrato entre la implementación de Lync Server y otras implementaciones de Office Communications Server 2007 R2 o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef23f-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="ef23f-121">Una configuración federada de Lync Server permite a los usuarios de Lync acceder a usuarios federados mediante las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ef23f-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="ef23f-122">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="ef23f-122">IM and Presence</span></span>

  - <span data-ttu-id="ef23f-123">Creación de contactos federados en el cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="ef23f-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="ef23f-124">La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible.</span><span class="sxs-lookup"><span data-stu-id="ef23f-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="ef23f-125">Una configuración XMPP permite a los usuarios de Lync acceder a usuarios del dominio XMPP permitidos mediante:</span><span class="sxs-lookup"><span data-stu-id="ef23f-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="ef23f-126">Mensajería instantánea y presencia: solo para personas</span><span class="sxs-lookup"><span data-stu-id="ef23f-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="ef23f-127">Creación de los contactos de XMPP federados en el cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="ef23f-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ef23f-p106">La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="ef23f-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="ef23f-130">Federación externa de servidores perimetrales, conectividad pública de mensajería instantánea y proceso de implementación de usuarios XMPP</span><span class="sxs-lookup"><span data-stu-id="ef23f-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef23f-131">Fase</span><span class="sxs-lookup"><span data-stu-id="ef23f-131">Phase</span></span></th>
<th><span data-ttu-id="ef23f-132">Pasos</span><span class="sxs-lookup"><span data-stu-id="ef23f-132">Steps</span></span></th>
<th><span data-ttu-id="ef23f-133">Permisos</span><span class="sxs-lookup"><span data-stu-id="ef23f-133">Permissions</span></span></th>
<th><span data-ttu-id="ef23f-134">Documentación</span><span class="sxs-lookup"><span data-stu-id="ef23f-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef23f-135">Determinar las opciones para agregar a la implementación perimetral existente</span><span class="sxs-lookup"><span data-stu-id="ef23f-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="ef23f-136">Ejecute el generador de topología para editar la configuración del servidor perimetral y crear y publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="ef23f-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="ef23f-137">La topología de borde existente replicará los cambios del almacén de administración central en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="ef23f-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="ef23f-138">Grupo administradores de dominio y grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ef23f-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="ef23f-139">Puede editar una topología con una cuenta que sea miembro del grupo usuarios locales, pero la publicación de una topología requiere una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ef23f-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="ef23f-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología perimetral y de director Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef23f-141">Prepararse para la configuración</span><span class="sxs-lookup"><span data-stu-id="ef23f-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ef23f-142">Asegúrese de que se cumplan los requisitos previos del sistema.</span><span class="sxs-lookup"><span data-stu-id="ef23f-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="ef23f-143">Configurar registros DNS internos y externos para admitir la conectividad de mensajería instantánea pública, la Federación de Lync y la Federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="ef23f-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="ef23f-144">Configurar puertos y protocolos en el firewall para admitir los tipos de Federación que se están implementando</span><span class="sxs-lookup"><span data-stu-id="ef23f-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="ef23f-145">Obtenga e instale certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="ef23f-145">Obtain and install public certificates.</span></span> <span data-ttu-id="ef23f-146">El tiempo necesario para obtener certificados depende de la entidad emisora de certificados (CA) que emite el certificado.</span><span class="sxs-lookup"><span data-stu-id="ef23f-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="ef23f-147">Este paso es opcional en este punto de la implementación.</span><span class="sxs-lookup"><span data-stu-id="ef23f-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="ef23f-148">Si no realiza este paso en este punto, debe hacerlo durante la configuración del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="ef23f-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="ef23f-149">El servicio de servidor perimetral no se puede iniciar hasta que se obtengan los certificados</span><span class="sxs-lookup"><span data-stu-id="ef23f-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ef23f-150">Según corresponda a su organización, puesto que estos roles suelen dividirse entre numerosos grupos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef23f-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="ef23f-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef23f-152">Configurar servidores perimetrales para escenarios de Federación</span><span class="sxs-lookup"><span data-stu-id="ef23f-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ef23f-153">Transporte el archivo de configuración de la topología exportada a cada servidor perimetral o permita que se complete la replicación</span><span class="sxs-lookup"><span data-stu-id="ef23f-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="ef23f-154">Volver a ejecutar el Asistente para la implementación para instalar componentes complementarios para la Federación</span><span class="sxs-lookup"><span data-stu-id="ef23f-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="ef23f-155">Configurar los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="ef23f-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="ef23f-156">Solicitar e instalar certificados para cada servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ef23f-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="ef23f-157">Reiniciar los servicios del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ef23f-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ef23f-158">Grupo administradores</span><span class="sxs-lookup"><span data-stu-id="ef23f-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ef23f-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configuración de federación de Lync en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ef23f-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Establecer conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ef23f-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurar la federación XMPP en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef23f-162">Configurar la compatibilidad con el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ef23f-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ef23f-163">Usar el acceso de usuarios externos del panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ef23f-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="ef23f-164">Configurar la Directiva de acceso externo para habilitar las comunicaciones con usuarios federados o usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="ef23f-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="ef23f-165">Configurar dominios federados SIP para permitir o bloquear dominios</span><span class="sxs-lookup"><span data-stu-id="ef23f-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="ef23f-166">Habilitar proveedores federados SIP para proveedores de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="ef23f-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="ef23f-167">Configurar socios de XMPP federados por dominio XMPP</span><span class="sxs-lookup"><span data-stu-id="ef23f-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ef23f-168">RTCUniversalServerAdmins una cuenta de usuario o grupo que está asignada al rol CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef23f-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="ef23f-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ef23f-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef23f-171">Comprobar la configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ef23f-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="ef23f-172">Comprobar la Conectividad del servidor y la replicación de datos de configuración desde servidores internos</span><span class="sxs-lookup"><span data-stu-id="ef23f-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="ef23f-173">Para la verificación de la replicación, RTCUniversalServerAdmins cuenta de usuario o grupo que se asigna al CSAdministrator roleFor la verificación de la conectividad de los usuarios, un usuario para cada tipo de usuario federado.</span><span class="sxs-lookup"><span data-stu-id="ef23f-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="ef23f-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobación de la implementación perimetral en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ef23f-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="ef23f-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

