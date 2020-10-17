---
title: 'Lync Server 2013: comprobar el diseño de la topología'
description: 'Lync Server 2013: comprobar el diseño de la topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560196"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="16cdd-103">Comprobar el diseño de la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16cdd-103">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16cdd-104">_**Última modificación del tema:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="16cdd-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="16cdd-105">El generador de topologías comprueba automáticamente la topología.</span><span class="sxs-lookup"><span data-stu-id="16cdd-105">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="16cdd-106">Cualquier error de topología se identifica como un error de validación, que se indica mediante el icono de error de validación junto al rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="16cdd-106">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="16cdd-107">Es importante comprobar también que la topología representa correctamente la topología de su implementación.</span><span class="sxs-lookup"><span data-stu-id="16cdd-107">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="16cdd-108">Para comprobar la topología antes de su publicación</span><span class="sxs-lookup"><span data-stu-id="16cdd-108">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="16cdd-109">Compruebe que todas las URL sencillas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="16cdd-109">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="16cdd-110">Confirme que el servidor basado en SQL Server está en línea y disponible para el equipo en el que está instalado el generador de topologías, incluidas las reglas de Firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="16cdd-110">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="16cdd-111">Confirme que el recurso compartido de archivos esté disponible y que los permisos correctos estén definidos.</span><span class="sxs-lookup"><span data-stu-id="16cdd-111">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="16cdd-112">Confirme que se han definido en la topología los roles de servidor correctos que cumplen los requisitos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="16cdd-112">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="16cdd-113">Compruebe que los servidores existen en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="16cdd-113">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="16cdd-114">Esto se producirá automáticamente si ha incorporado los servidores al dominio.</span><span class="sxs-lookup"><span data-stu-id="16cdd-114">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="16cdd-115">Una vez que haya verificado la topología y comprobado que no existen errores de validación, estará listo para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="16cdd-115">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="16cdd-116">Si hay errores de validación, deberá corregirlos para poder publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="16cdd-116">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="16cdd-117">Para obtener más información sobre la publicación de la topología, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="16cdd-117">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

