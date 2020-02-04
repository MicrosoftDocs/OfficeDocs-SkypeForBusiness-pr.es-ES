---
title: Comprobar la federación y el acceso remoto de usuarios externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ad994eb7769dff067195520c2c6fde955910f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="7b281-102">Comprobar la federación y el acceso remoto de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="7b281-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b281-103">_**Última modificación del tema:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="7b281-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="7b281-104">Después de la transición de la ruta de Federación al servidor perimetral de Lync Server 2013, debe realizar algunas pruebas funcionales para comprobar que la Federación se ejecuta según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="7b281-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="7b281-105">Las pruebas de acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos algunos de los siguientes elementos o todos ellos.</span><span class="sxs-lookup"><span data-stu-id="7b281-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="7b281-106">Probar la conectividad de usuarios externos y acceso externo</span><span class="sxs-lookup"><span data-stu-id="7b281-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="7b281-107">Usuarios de al menos un dominio federado, un usuario interno de Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7b281-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="7b281-108">Prueba la mensajería instantánea (mi), la presencia, el audio/vídeo (A/V) y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="7b281-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="7b281-109">Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para el que se haya completado el aprovisionamiento) comunicándose con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7b281-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="7b281-110">Comprobar que los usuarios anónimos pueden unirse a conferencias.</span><span class="sxs-lookup"><span data-stu-id="7b281-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="7b281-111">Un usuario hospedado en Lync Server 2010 con acceso de usuario remoto (iniciar sesión en Lync Server 2010 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7b281-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="7b281-112">Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="7b281-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="7b281-113">Un usuario hospedado en Lync Server 2013 con acceso de usuario remoto (iniciar sesión en Lync Server 2013 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7b281-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="7b281-114">Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="7b281-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

