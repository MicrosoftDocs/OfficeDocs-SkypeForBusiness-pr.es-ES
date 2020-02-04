---
title: 'Lync Server 2013: Implementar el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba083650b9a068d48e28bf8af0c51b4b25b5c227
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="b8d4c-102">Implementar el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8d4c-103">_**Última modificación del tema:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="b8d4c-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="b8d4c-104">La implementación de componentes de Edge para Microsoft Lync Server 2013 permite a los usuarios externos que no han iniciado sesión en la red interna de su organización, incluidos usuarios remotos autenticados y anónimos, socios federados (incluidos socios de XMPP), clientes móviles y usuarios de servicios de mensajería instantánea (mi) públicos para comunicarse con otros usuarios de su organización mediante Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8d4c-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="b8d4c-105">Los procesos de implementación y configuración de Lync Server 2013 no difieren significativamente de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b8d4c-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="b8d4c-106">Las herramientas de instalación y administración son muy parecidas a las de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b8d4c-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8d4c-107">La instalación y configuración&nbsp;del servidor perimetral 2013 de Microsoft Lync Server pueden ser un proceso complejo que requiere una cantidad potencialmente importante de planificación y coordinación con sus equipos internos, entre los que se incluyen, entre otros, consideraciones de seguridad, redes, firewalls, sistema de nombres de dominio (DNS), equilibrador de carga e infraestructura de clave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="b8d4c-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="b8d4c-108">Le recomendamos encarecidamente que revise y use la documentación y el proceso de planeamiento que se proporcionan antes de implementar sus componentes de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b8d4c-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="b8d4c-109">Esto le ayudará a limitar el número y la frecuencia de los cambios y la frecuencia de los cambios no deseados a medida que avanza por el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="b8d4c-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="b8d4c-110">Para obtener información sobre cómo planear el acceso de usuarios externos, vea <A href="lync-server-2013-planning-for-external-user-access.md">planear el acceso de usuarios externos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8d4c-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b8d4c-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b8d4c-111">In This Section</span></span>

  - [<span data-ttu-id="b8d4c-112">Lista de comprobación de la implementación del acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="b8d4c-113">Requisitos del sistema para componentes perimetrales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="b8d4c-114">Preparar la instalación de los servidores en la red del perímetro para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="b8d4c-115">Creación de una topología perimetral y de director Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="b8d4c-116">[Configuración del Director en Lync Server 2013](lync-server-2013-setting-up-the-director.md) (opcional)</span><span class="sxs-lookup"><span data-stu-id="b8d4c-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="b8d4c-117">Configuración de servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="b8d4c-118">Configuración de los servidores proxy inversos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="b8d4c-119">Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="b8d4c-120">Guía de aprovisionamiento para la conectividad entre Lync y Skype en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="b8d4c-121">Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="b8d4c-122">Implementar la movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="b8d4c-123">Comprobación de la implementación perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d4c-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

