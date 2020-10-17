---
title: 'Lync Server 2013: configuración del estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76c9b0b3e091a45e637780a58646253746559a23
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502127"
---
# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="831d8-102">Configuración del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-102">Configuring Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="831d8-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="831d8-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="831d8-104">El estacionamiento de llamadas permite a un usuario de Enterprise Voice poner una llamada en espera desde un teléfono y, después, recuperar la llamada más adelante marcando un número interno (conocido como una *órbita*de estacionamiento de llamadas) desde cualquier teléfono.</span><span class="sxs-lookup"><span data-stu-id="831d8-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="831d8-105">Los componentes que llaman a los usos de estacionamiento se instalan y habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="831d8-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="831d8-106">Sin embargo, debe configurar el estacionamiento de llamadas antes de que esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="831d8-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="831d8-107">Esta sección le guiará a través de la configuración del estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="831d8-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="831d8-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="831d8-108">In This Section</span></span>

  - [<span data-ttu-id="831d8-109">Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="831d8-110">Proceso de implementación del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="831d8-111">Configurar la tabla de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="831d8-112">Configurar las opciones del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="831d8-113">Personalizar la música de estacionamiento de llamadas en espera en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="831d8-114">Habilitar el estacionamiento de llamadas para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="831d8-115">Comprobar reglas de normalización para el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="831d8-116">Opcional Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831d8-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

