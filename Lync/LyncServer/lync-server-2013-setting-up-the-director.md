---
title: 'Lync Server 2013: Configuración del director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de0fe7b06bbeed714aca444e75086fba9579e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="0781f-102">Configuración del director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0781f-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0781f-103">_**Última modificación del tema:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="0781f-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="0781f-104">Si va a habilitar el acceso para los usuarios externos mediante la implementación de servidores perimetrales, una opción es implementar un director.</span><span class="sxs-lookup"><span data-stu-id="0781f-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="0781f-105">Un director es un servidor que ejecuta Microsoft Lync Server 2013 que autentica las solicitudes de usuario, pero no aloja ninguna cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0781f-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="0781f-106">Ahora, esto no es necesario, pero es muy útil si está preocupado por el rendimiento y desea ayudar a simplificar las solicitudes de autenticación.</span><span class="sxs-lookup"><span data-stu-id="0781f-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="0781f-107">Si decide que esta es una buena idea para su organización, los pasos para configurar un director o un grupo de directores son similares a la configuración de un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0781f-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="0781f-108">Una vez que haya definido los directores en el generador de topología, tendrá que realizar los pasos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="0781f-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0781f-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0781f-109">In This Section</span></span>

  - [<span data-ttu-id="0781f-110">Instalar el almacén de configuración local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0781f-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="0781f-111">Instalar Lync Server 2013 en el director</span><span class="sxs-lookup"><span data-stu-id="0781f-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="0781f-112">Configurar los certificados para el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0781f-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="0781f-113">Iniciar servicios en el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0781f-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="0781f-114">Probar el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0781f-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="0781f-115">Configurar el inicio de sesión automático de los clientes para usar el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0781f-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

