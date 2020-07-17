---
title: Autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f66f53b5c1aa25324dbd316ad2d72e7d04c42e0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="46d32-102">Autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46d32-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d32-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="46d32-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="46d32-104">Para cada servidor front-end de Lync Server 2013 o servidor Standard Edition del grupo piloto, debe actualizar la lista de servidores internos que están autorizados a conectarse al servidor perimetral de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="46d32-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="46d32-105">Sin estas actualizaciones, no funcionará la conferencia de audio/vídeo (A/V) externa para los usuarios que se unen al servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="46d32-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="46d32-106">Para autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46d32-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="46d32-107">Desde el servidor perimetral de Office Communications Server 2007 R2, en el grupo **herramientas administrativas** , abra el complemento **Administración de equipos** .</span><span class="sxs-lookup"><span data-stu-id="46d32-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="46d32-108">En el árbol de consola, expanda **Servicios y Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="46d32-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="46d32-109">Haga clic con el botón secundario en **Office Communications Server 2007 R2** y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="46d32-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="46d32-110">Haga clic en la pestaña **Interno**.</span><span class="sxs-lookup"><span data-stu-id="46d32-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="46d32-111">En **Agregar servidor**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="46d32-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="46d32-112">En el cuadro de diálogo **Agregar Office Communications Server**, escriba la información apropiada:</span><span class="sxs-lookup"><span data-stu-id="46d32-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="46d32-113">Especifique el nombre de dominio completo (FQDN) de cada servidor front-end de Lync Server 2013 o servidor Standard Edition, y grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46d32-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="46d32-114">Especifique el FQDN del Director de Lync Server 2013 si configuró una ruta estática en el grupo de servidores que especifica el equipo del próximo salto por su FQDN.</span><span class="sxs-lookup"><span data-stu-id="46d32-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="46d32-115">Una vez que haya agregado una entrada para cada 2013, servidor front-end, servidor Standard Edition, grupo de servidores y director de Lync Server, haga clic en **aplicar** y, a continuación, haga clic en **Aceptar** para cerrar la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="46d32-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

