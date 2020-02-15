---
title: 'Lync Server 2013: comprobar el diseño de la topología'
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
ms.openlocfilehash: c6968dfca2072ca9a6c0e5008528e27a14f01447
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="cdabd-102">Comprobar el diseño de la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdabd-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdabd-103">_**Última modificación del tema:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="cdabd-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="cdabd-104">El generador de topologías comprueba automáticamente la topología.</span><span class="sxs-lookup"><span data-stu-id="cdabd-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="cdabd-105">Cualquier error de topología se identifica como un error de validación, que se indica mediante el icono de error de validación junto al rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="cdabd-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="cdabd-106">Es importante comprobar también que la topología representa correctamente la topología de su implementación.</span><span class="sxs-lookup"><span data-stu-id="cdabd-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="cdabd-107">Para comprobar la topología antes de su publicación</span><span class="sxs-lookup"><span data-stu-id="cdabd-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="cdabd-108">Compruebe que todas las URL sencillas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="cdabd-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="cdabd-109">Confirme que el servidor basado en SQL Server está en línea y disponible para el equipo en el que está instalado el generador de topologías, incluidas las reglas de Firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="cdabd-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="cdabd-110">Confirme que el recurso compartido de archivos esté disponible y que los permisos correctos estén definidos.</span><span class="sxs-lookup"><span data-stu-id="cdabd-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="cdabd-111">Confirme que se han definido en la topología los roles de servidor correctos que cumplen los requisitos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="cdabd-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="cdabd-112">Compruebe que los servidores existen en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cdabd-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="cdabd-113">Esto se producirá automáticamente si ha incorporado los servidores al dominio.</span><span class="sxs-lookup"><span data-stu-id="cdabd-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="cdabd-114">Una vez que haya verificado la topología y comprobado que no existen errores de validación, estará listo para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="cdabd-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="cdabd-115">Si hay errores de validación, deberá corregirlos para poder publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="cdabd-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="cdabd-116">Para obtener más información sobre la publicación de la topología, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="cdabd-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

