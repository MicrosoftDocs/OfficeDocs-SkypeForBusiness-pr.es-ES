---
title: Importación de directivas y parámetros
description: Importar directivas y configuración.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569036"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="6eb79-103">Importación de directivas y parámetros</span><span class="sxs-lookup"><span data-stu-id="6eb79-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eb79-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6eb79-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6eb79-105">Tras combinar la información de topología de Office Communications Server 2007 R2 con el grupo piloto de Lync Server 2013, debe ejecutar un cmdlet del shell de administración de Lync Server 2013 para migrar las directivas y las opciones de configuración de Office Communications Server 2007 R2 al grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb79-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="6eb79-106">El cmdlet **Import-CsLegacyConfiguration** importa directivas, rutas de voz, planes de marcado, direcciones URL de Communicator Web Access y números de acceso telefónico a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb79-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="6eb79-107">Para migrar directivas y configuración</span><span class="sxs-lookup"><span data-stu-id="6eb79-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="6eb79-108">En el servidor front-end de Lync Server 2013, inicie el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6eb79-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="6eb79-109">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6eb79-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="6eb79-110">Una vez importadas las directivas, siga el procedimiento que se indica a continuación para ver las directivas importadas en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6eb79-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="6eb79-111">Par ver directivas importadas</span><span class="sxs-lookup"><span data-stu-id="6eb79-111">To view imported policies</span></span>

1.  <span data-ttu-id="6eb79-112">Abra el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb79-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="6eb79-113">Haga clic en **Enrutamiento de voz** y vea las directivas importadas.</span><span class="sxs-lookup"><span data-stu-id="6eb79-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="6eb79-114">Haga clic en **Conferencia** y vea las directivas importadas.</span><span class="sxs-lookup"><span data-stu-id="6eb79-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="6eb79-115">Haga clic en **Federación y acceso externo** y vea las directivas importadas.</span><span class="sxs-lookup"><span data-stu-id="6eb79-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="6eb79-116">Haga clic en **Supervisión y archivado** y vea las directivas importadas.</span><span class="sxs-lookup"><span data-stu-id="6eb79-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

