---
title: Configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública
description: Configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b83c29da75c99e7a338bfd7732aec8ec49cbf47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556966"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="25ebb-103">Configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25ebb-103">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25ebb-104">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="25ebb-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="25ebb-105">La federación, la conectividad de mensajería instantánea pública y el protocolo extensible de mensajería y presencia (XMPP) definen una clase diferente de usuarios externos: los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="25ebb-105">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="25ebb-106">Los usuarios de una implementación de Lync Server o una implementación de XMPP federadas tienen acceso a un conjunto limitado de servicios y se autentican mediante la implementación externa.</span><span class="sxs-lookup"><span data-stu-id="25ebb-106">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="25ebb-107">Los usuarios remotos son miembros de su implementación de Lync Server y tienen acceso a todos los servicios ofrecidos por su implementación de.</span><span class="sxs-lookup"><span data-stu-id="25ebb-107">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="25ebb-108">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="25ebb-108">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="25ebb-109">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="25ebb-109">has been announced.</span></span> <span data-ttu-id="25ebb-110">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25ebb-110">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="25ebb-111">La conectividad de mensajería instantánea pública es un tipo especial de Federación que permite a un cliente de Lync Server tener acceso a asociados de mensajería instantánea pública configurado con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="25ebb-111">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="25ebb-112">Actualmente, los socios de conectividad de mensajería instantánea pública son:</span><span class="sxs-lookup"><span data-stu-id="25ebb-112">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="25ebb-113">America Online</span><span class="sxs-lookup"><span data-stu-id="25ebb-113">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="25ebb-114">Windows Live</span><span class="sxs-lookup"><span data-stu-id="25ebb-114">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="25ebb-115">Toolbar\!</span><span class="sxs-lookup"><span data-stu-id="25ebb-115">Yahoo\!</span></span>

<span data-ttu-id="25ebb-116">Una configuración de conectividad de mensajería instantánea pública permite a los usuarios de Lync obtener acceso a usuarios de conectividad de mensajería instantánea pública mediante:</span><span class="sxs-lookup"><span data-stu-id="25ebb-116">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="25ebb-117">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="25ebb-117">IM and Presence</span></span>

  - <span data-ttu-id="25ebb-118">Visibilidad de contactos de conectividad de mensajería instantánea pública en el cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="25ebb-118">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="25ebb-119">Conversaciones de MI de persona a persona con contactos</span><span class="sxs-lookup"><span data-stu-id="25ebb-119">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="25ebb-120">Llamadas de audio y vídeo con usuarios de Windows Live</span><span class="sxs-lookup"><span data-stu-id="25ebb-120">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="25ebb-p104">La federación de Lync Server define un acuerdo entre su implementación de Lync Server y otras implementaciones de Office Communications Server 2007 R2 o Lync Server. Una configuración federada de Lync Server permite a los usuarios de Lync obtener acceso a usuarios federados mediante:</span><span class="sxs-lookup"><span data-stu-id="25ebb-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="25ebb-123">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="25ebb-123">IM and Presence</span></span>

  - <span data-ttu-id="25ebb-124">Creación de contactos federados en el cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="25ebb-124">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="25ebb-p105">La federación XMPP define una implementación externa basándose en el protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync obtener acceso a usuarios de dominios XMPP mediante:</span><span class="sxs-lookup"><span data-stu-id="25ebb-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="25ebb-127">Mensajería instantánea y presencia (solo de persona a persona)</span><span class="sxs-lookup"><span data-stu-id="25ebb-127">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="25ebb-128">Creación de contactos federados XMPP en el cliente Lync</span><span class="sxs-lookup"><span data-stu-id="25ebb-128">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="25ebb-129">La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="25ebb-129">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="25ebb-130">Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="25ebb-130">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="25ebb-131">Federación externa de servidor perimetral, conectividad de mensajería instantánea pública y proceso de implementación de usuarios de XMPP</span><span class="sxs-lookup"><span data-stu-id="25ebb-131">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25ebb-132">Fase</span><span class="sxs-lookup"><span data-stu-id="25ebb-132">Phase</span></span></th>
<th><span data-ttu-id="25ebb-133">Pasos</span><span class="sxs-lookup"><span data-stu-id="25ebb-133">Steps</span></span></th>
<th><span data-ttu-id="25ebb-134">Permisos</span><span class="sxs-lookup"><span data-stu-id="25ebb-134">Permissions</span></span></th>
<th><span data-ttu-id="25ebb-135">Documentación</span><span class="sxs-lookup"><span data-stu-id="25ebb-135">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25ebb-136">Determine las opciones para agregar la implementación de servidor perimetral existente</span><span class="sxs-lookup"><span data-stu-id="25ebb-136">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="25ebb-137">Ejecute el generador de topologías para editar la configuración del servidor perimetral y cree y publique la topología.</span><span class="sxs-lookup"><span data-stu-id="25ebb-137">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="25ebb-138">La topología perimetral existente replicará los cambios del almacén de administración central en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="25ebb-138">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="25ebb-139">Grupo Administradores de dominio y grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25ebb-139">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="25ebb-140">Puede editar una topología mediante una cuenta que es miembro del grupo de usuarios locales pero publicar una topología requiere una cuenta que es miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="25ebb-140">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="25ebb-141"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología perimetral y de Director en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-141"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ebb-142">Prepararse para el programa de instalación</span><span class="sxs-lookup"><span data-stu-id="25ebb-142">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="25ebb-143">Asegúrese de que se cumplen los requisitos previos del sistema.</span><span class="sxs-lookup"><span data-stu-id="25ebb-143">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="25ebb-144">Configure registros DNS internos y externos para admitir la conectividad de mensajería instantánea pública, la federación de Lync y la federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="25ebb-144">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="25ebb-145">Configure puertos y protocolos en el firewall para admitir los tipos de federación que va a implementar</span><span class="sxs-lookup"><span data-stu-id="25ebb-145">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="25ebb-p108">Obtenga e instale certificados públicos. El tiempo necesario para obtener certificados depende de qué entidad de certificación (CA) emite el certificado. Este paso es opcional en este punto de la implementación. Si no lleva a cabo este paso en este momento, debe hacerlo durante la configuración del servidor perimetral. No se puede iniciar el servicio de servidor perimetral hasta que se obtengan certificados.</span><span class="sxs-lookup"><span data-stu-id="25ebb-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="25ebb-151">Según corresponda a su organización, ya que estas funciones se suelen dividir entre numerosos grupos de trabajo</span><span class="sxs-lookup"><span data-stu-id="25ebb-151">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="25ebb-152"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-152"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ebb-153">Configure los servidores perimetrales para escenarios de federación</span><span class="sxs-lookup"><span data-stu-id="25ebb-153">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="25ebb-154">Transporte el archivo de configuración de topología exportado a cada servidor perimetral o permita la replicación para completar</span><span class="sxs-lookup"><span data-stu-id="25ebb-154">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="25ebb-155">Vuelva a ejecutar el Asistente para implementación para instalar componentes auxiliares para la federación</span><span class="sxs-lookup"><span data-stu-id="25ebb-155">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="25ebb-156">Configure los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="25ebb-156">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="25ebb-157">Solicite e instale certificados para cada servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="25ebb-157">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="25ebb-158">Reinicie los servicios de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="25ebb-158">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="25ebb-159">Grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="25ebb-159">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="25ebb-160"><a href="lync-server-2013-setting-up-lync-federation.md">Configuración de la Federación de Lync en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-160"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="25ebb-161"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuración de la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-161"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="25ebb-162"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuración de la Federación XMPP en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-162"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ebb-163">Configure la compatibilidad para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="25ebb-163">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="25ebb-164">Usar el acceso de usuarios externos del panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="25ebb-164">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="25ebb-165">Configure la directiva de acceso externo para habilitar las comunicaciones con usuarios federados o usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="25ebb-165">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="25ebb-166">Configure los dominios federados SIP para permitir o bloquear dominios</span><span class="sxs-lookup"><span data-stu-id="25ebb-166">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="25ebb-167">Habilite proveedores federados SIP para proveedores de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="25ebb-167">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="25ebb-168">Configure socios federados de XMPP para el dominio XMPP</span><span class="sxs-lookup"><span data-stu-id="25ebb-168">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="25ebb-169">Grupo RTCUniversalServerAdmins o cuenta de usuario que se asigna al rol CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="25ebb-169">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="25ebb-170"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuración de la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-170"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="25ebb-171"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-171"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ebb-172">Compruebe la configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="25ebb-172">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="25ebb-173">Compruebe la conectividad de servidor y la replicación de datos de configuración de servidores internos</span><span class="sxs-lookup"><span data-stu-id="25ebb-173">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="25ebb-174">Para la comprobación de la replicación, el grupo RTCUniversalServerAdmins o la cuenta de usuario que se asigna al rol CSAdministrator. Para la comprobación de la conectividad de usuario, un usuario para cada tipo de usuario federado</span><span class="sxs-lookup"><span data-stu-id="25ebb-174">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="25ebb-175"><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobar la implementación perimetral en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-175"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="25ebb-176"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="25ebb-176"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

