---
title: 'Lync Server 2013: configuración del Director'
description: 'Lync Server 2013: configuración del director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b917000dec6d30fdec2963ff1e464fbb9a70805
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554116"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="42c7c-103">Configuración del Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42c7c-103">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42c7c-104">_**Última modificación del tema:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="42c7c-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="42c7c-105">Si está habilitando el acceso para los usuarios externos mediante la implementación de servidores perimetrales, una opción es implementar un director.</span><span class="sxs-lookup"><span data-stu-id="42c7c-105">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="42c7c-106">Un director es un servidor que ejecuta Microsoft Lync Server 2013 que autentica solicitudes de usuario, pero no aloja ninguna cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="42c7c-106">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="42c7c-107">Ahora, esto no es un requisito, pero es muy útil si está preocupado por el rendimiento y desea ayudar a simplificar las solicitudes de autenticación.</span><span class="sxs-lookup"><span data-stu-id="42c7c-107">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="42c7c-108">Si decide que esta es una buena idea para su organización, los pasos para configurar un director o un grupo de directores son similares a la configuración de un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="42c7c-108">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="42c7c-109">Una vez que haya definido los directores en el generador de topologías, tendrá que realizar los pasos que se indican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="42c7c-109">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42c7c-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="42c7c-110">In This Section</span></span>

  - [<span data-ttu-id="42c7c-111">Instalar el almacén de configuración local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42c7c-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="42c7c-112">Instalación de Lync Server 2013 en el director</span><span class="sxs-lookup"><span data-stu-id="42c7c-112">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="42c7c-113">Configurar certificados para el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42c7c-113">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="42c7c-114">Iniciar servicios en el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42c7c-114">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="42c7c-115">Probar el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42c7c-115">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="42c7c-116">Configurar el Sign-In de cliente automático para usar el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42c7c-116">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

