---
title: 'Lync Server 2013: implementación del control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2cb64b3ca2d8e7d0c520e1d8ff4ee896895e13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="9a3c2-102">Implementación del control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a3c2-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a3c2-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="9a3c2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9a3c2-104">En esta sección se le guiará a través del proceso de implementación de la funcionalidad de control remoto de llamadas para usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="9a3c2-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a3c2-105">Aunque las características de control remoto de llamadas están disponibles para los usuarios remotos que se encuentran fuera del firewall de su organización, los detalles sobre la implementación de escenarios de acceso externo no se abordan en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="9a3c2-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="9a3c2-106">Para obtener más información sobre cómo implementar el acceso de usuarios externos, consulte <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="9a3c2-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a3c2-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9a3c2-107">In This Section</span></span>

  - [<span data-ttu-id="9a3c2-108">Configuración de Lync Server 2013 para enrutar a una puerta de enlace SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="9a3c2-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="9a3c2-109">Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a3c2-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="9a3c2-110">Configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a3c2-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="9a3c2-111">[Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (solo si la puerta de enlace está configurada para usar TCP)</span><span class="sxs-lookup"><span data-stu-id="9a3c2-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="9a3c2-112">Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a3c2-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="9a3c2-113">Control remoto de llamadas y normalización de números de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a3c2-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="9a3c2-114">[Quitar un host autorizado heredado en Lync Server 2013 (opcional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (solo si está migrando usuarios previamente habilitados para el control remoto de llamadas)</span><span class="sxs-lookup"><span data-stu-id="9a3c2-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9a3c2-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9a3c2-115">Related Sections</span></span>

[<span data-ttu-id="9a3c2-116">Planeación del control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a3c2-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

