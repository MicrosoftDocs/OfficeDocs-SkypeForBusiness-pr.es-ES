---
title: Comprobar la federación y el acceso remoto de usuarios externos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a36e92849c59760f831cdebaf59906b546b01d7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="6bbc9-102">Comprobar la federación y el acceso remoto de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="6bbc9-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bbc9-103">_**Última modificación del tema:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="6bbc9-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="6bbc9-104">Después de realizar la transición de la ruta de Federación al servidor perimetral de Lync Server 2013, debe realizar algunas pruebas funcionales para comprobar que la Federación funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="6bbc9-105">Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="6bbc9-106">Comprobación de conectividad de los usuarios externos y el acceso externo</span><span class="sxs-lookup"><span data-stu-id="6bbc9-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="6bbc9-107">Usuarios de al menos un dominio federado, un usuario interno en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="6bbc9-108">Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="6bbc9-109">Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="6bbc9-110">Compruebe que los usuarios anónimos pueden unirse a conferencias.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="6bbc9-111">Un usuario hospedado en Lync Server 2010 con acceso de usuarios remotos (iniciando sesión en Lync Server 2010 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="6bbc9-112">Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="6bbc9-113">Un usuario hospedado en Lync Server 2013 con acceso de usuarios remotos (iniciando sesión en Lync Server 2013 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="6bbc9-114">Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="6bbc9-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

