---
title: 'Lync Server 2013: configurar la base de datos de ubicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b7bf02e809597092ca2212cacb3fd78336a0be2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="72547-102">Configurar la base de datos de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72547-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72547-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="72547-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="72547-p101">Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones. Si no configura ninguna base de datos de ubicaciones, y **Ubicación obligatoria** se ha establecido como **Sí** o **Declinación de responsabilidades** en la directiva de ubicación, se le pedirá al usuario que introduzca manualmente una ubicación.</span><span class="sxs-lookup"><span data-stu-id="72547-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="72547-106">Para configurar la base de datos de ubicaciones, deberá realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="72547-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="72547-107">Llene la base de datos con una búsqueda de elementos de red a las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="72547-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="72547-108">Si usa una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), debe incluir la \<Elin\> en el campo NombreCompañía.</span><span class="sxs-lookup"><span data-stu-id="72547-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="72547-109">Validar las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="72547-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="72547-110">Publicar la base de datos actualizada.</span><span class="sxs-lookup"><span data-stu-id="72547-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72547-111">También puede optar por definir una base de datos secundaria de origen de ubicaciones, para usarla en lugar de la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="72547-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="72547-112">Para obtener más información, consulte <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurar un servicio de información de ubicaciones secundarias en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="72547-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72547-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="72547-113">In This Section</span></span>

  - [<span data-ttu-id="72547-114">Rellenar la base de datos de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72547-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="72547-115">Validar direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72547-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="72547-116">Publicar la base de datos de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72547-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

