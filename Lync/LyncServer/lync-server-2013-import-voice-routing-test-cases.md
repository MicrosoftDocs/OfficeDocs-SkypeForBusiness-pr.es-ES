---
title: 'Lync Server 2013: importación de casos de prueba de enrutamiento de voz'
description: 'Lync Server 2013: importación de casos de prueba de enrutamiento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ce1b144de03406b7b78d6957371ed2bc303e95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547836"
---
# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="62ef8-103">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62ef8-103">Import voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62ef8-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="62ef8-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="62ef8-105">Los casos de prueba permiten probar rutas de voz en su organización: se definen aspectos como el número que se va a marcar y el plan de marcado y la Directiva de voz que se van a usar, y Lync Server 2013 puede comprobar que, teniendo en cuenta las condiciones, el número proporcionado se puede enrutar correctamente a la red RTC.</span><span class="sxs-lookup"><span data-stu-id="62ef8-105">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="62ef8-106">Los casos de prueba, que se pueden crear mediante el panel de control de Lync Server, normalmente solo se guardan en el servidor donde se creó y ejecutó originalmente el caso.</span><span class="sxs-lookup"><span data-stu-id="62ef8-106">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="62ef8-107">Sin embargo, estos casos de prueba pueden exportarse como archivos XML (con la extensión .vtest) y luego importarse en otros servidores.</span><span class="sxs-lookup"><span data-stu-id="62ef8-107">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="62ef8-108">Esto le permite ejecutar las mismas pruebas en diferentes equipos ubicados en diferentes puntos de la topología.</span><span class="sxs-lookup"><span data-stu-id="62ef8-108">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="62ef8-109">Para importar un caso de prueba de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="62ef8-109">To import a voice routing test case</span></span>

1.  <span data-ttu-id="62ef8-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="62ef8-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="62ef8-111">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="62ef8-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="62ef8-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62ef8-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="62ef8-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62ef8-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="62ef8-114">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="62ef8-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="62ef8-115">En el menú **acciones** , haga clic en **importar casos de prueba**.</span><span class="sxs-lookup"><span data-stu-id="62ef8-115">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="62ef8-116">Busque el archivo de caso de prueba (. vtest) que desea importar y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="62ef8-116">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="62ef8-117">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="62ef8-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="62ef8-118">Cuando importe un archivo. vtest, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="62ef8-118">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="62ef8-119">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="62ef8-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62ef8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62ef8-120">See Also</span></span>


[<span data-ttu-id="62ef8-121">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62ef8-121">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

