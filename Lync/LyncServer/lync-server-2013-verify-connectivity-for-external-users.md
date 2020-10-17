---
title: 'Lync Server 2013: comprobar la conectividad de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d85b72572ba065f52e93ee34e6cb9324c2f647
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518647"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="49ac4-102">Comprobar la conectividad de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ac4-102">Verify connectivity for external users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ac4-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="49ac4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="49ac4-104">La validación de la conectividad para los usuarios externos requiere garantizar la conectividad de los usuarios al servidor y el puerto para el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="49ac4-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="49ac4-105">Un recurso valioso para confirmar la configuración y la capacidad de conectarse, enviar y recibir mensajes correctos para los escenarios que requiere el acceso de usuarios externos es el sitio analizador de conectividad remota ( <http://www.testocsconnectivity.com> ).</span><span class="sxs-lookup"><span data-stu-id="49ac4-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="49ac4-106">El sitio es administrado y mantenido por el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="49ac4-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="49ac4-107">Para acceder al analizador de conectividad remota, abra el sitio web en un explorador y siga las instrucciones para seleccionar el escenario.</span><span class="sxs-lookup"><span data-stu-id="49ac4-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="49ac4-108">Comprobación de conectividad de los usuarios externos y el acceso externo</span><span class="sxs-lookup"><span data-stu-id="49ac4-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="49ac4-109">Las pruebas para el acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos todos o algunos de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="49ac4-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="49ac4-110">Usuarios de al menos un dominio federado y probar la mensajería instantánea, la presencia, el uso compartido de escritorio y A/V.</span><span class="sxs-lookup"><span data-stu-id="49ac4-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="49ac4-111">Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para los que se haya completado el aprovisionamiento).</span><span class="sxs-lookup"><span data-stu-id="49ac4-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="49ac4-112">Usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="49ac4-112">Anonymous users.</span></span>

  - <span data-ttu-id="49ac4-113">Usuarios de la organización que han iniciado sesión en Lync de forma remota, pero que no usan VPN.</span><span class="sxs-lookup"><span data-stu-id="49ac4-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="49ac4-114">Estas pruebas determinan si el servidor perimetral es:</span><span class="sxs-lookup"><span data-stu-id="49ac4-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="49ac4-115">Escucha en los puertos necesarios mediante el uso de un cliente de Telnet desde fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="49ac4-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="49ac4-116">Ejemplo: Telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="49ac4-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="49ac4-117">Realice la prueba anterior en los puertos que usa en el servidor perimetral o en el grupo de servidores perimetrales en función de la implementación.</span><span class="sxs-lookup"><span data-stu-id="49ac4-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="49ac4-118">Realizar una resolución de DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="49ac4-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="49ac4-119">Desde fuera de la red haga ping a cada uno de los FQDN externos del grupo perimetral o perimetral.</span><span class="sxs-lookup"><span data-stu-id="49ac4-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="49ac4-120">Incluso si se produce un error en el comando ping, verá las direcciones IP, que puede comparar con las que ha asignado.</span><span class="sxs-lookup"><span data-stu-id="49ac4-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

