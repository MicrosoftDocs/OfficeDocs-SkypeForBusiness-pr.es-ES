---
title: 'Lync Server 2013: requisitos del sistema de nombres de dominio (DNS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="5f226-102">Requisitos del sistema de nombres de dominio (DNS) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f226-103">_**Última modificación del tema:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="5f226-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="5f226-104">Para implementar Lync Server, debe crear registros de sistema de nombres de dominio (DNS) que permitan la detección de clientes y servidores y, opcionalmente, la compatibilidad con el inicio de sesión automático de los clientes si su organización desea ser compatible.</span><span class="sxs-lookup"><span data-stu-id="5f226-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="5f226-105">Lync Server usa DNS de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="5f226-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="5f226-106">Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.</span><span class="sxs-lookup"><span data-stu-id="5f226-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="5f226-107">Para permitir que los clientes detecten el grupo de servidores front-end o el servidor Standard Edition usado para diversas transacciones SIP.</span><span class="sxs-lookup"><span data-stu-id="5f226-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="5f226-108">Para permitir que los dispositivos de comunicaciones unificadas (UC) que no han iniciado sesión detecten el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.</span><span class="sxs-lookup"><span data-stu-id="5f226-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="5f226-109">Para permitir que los servidores externos y los clientes se conecten a los servidores perimetrales o al proxy inverso HTTP para la mensajería instantánea (mi) o las conferencias.</span><span class="sxs-lookup"><span data-stu-id="5f226-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="5f226-110">Para permitir que los dispositivos de comunicaciones unificadas externas se conecten al servicio Web de actualización de dispositivos a través de servidores perimetrales o el proxy inverso HTTP, y obtenga actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="5f226-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="5f226-111">Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f226-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f226-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5f226-112">In This Section</span></span>

  - [<span data-ttu-id="5f226-113">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="5f226-114">Requisitos de DNS para grupos de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="5f226-115">Requisitos de DNS para servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="5f226-116">Requisitos de DNS para direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="5f226-117">Requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="5f226-118">Requisitos de DNS para la movilidad con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="5f226-119">Equilibrio de carga de DNS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f226-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

