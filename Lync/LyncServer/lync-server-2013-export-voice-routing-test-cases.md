---
title: 'Lync Server 2013: exportar casos de prueba de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d014d9c2748a5e6479c0f86ebd32255f3361ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="6f88e-102">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f88e-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f88e-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6f88e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6f88e-104">Los casos de prueba proporcionan una forma de probar rutas de voz en su organización: puede definir aspectos como el número que se va a marcar y el plan de marcado y la Directiva de voz que se van a usar, y Lync Server puede comprobar que, dadas las condiciones, el número proporcionado puede se enrutó correctamente a la red RTC.</span><span class="sxs-lookup"><span data-stu-id="6f88e-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="6f88e-105">Los casos de prueba, que se pueden crear mediante el panel de control de Lync Server, normalmente solo se guardan en el servidor donde se creó y ejecutó originalmente el caso.</span><span class="sxs-lookup"><span data-stu-id="6f88e-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="6f88e-106">Sin embargo, estos casos de prueba pueden exportarse como archivos XML (con la extensión .vtest) y luego importarse en otros servidores.</span><span class="sxs-lookup"><span data-stu-id="6f88e-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="6f88e-107">Esto le permite ejecutar las mismas pruebas en diferentes equipos ubicados en diferentes puntos de la topología.</span><span class="sxs-lookup"><span data-stu-id="6f88e-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="6f88e-108">Para exportar un caso de prueba de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="6f88e-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="6f88e-109">En el panel de control de Lync Server, haga clic en **enrutamiento de voz** y en **probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="6f88e-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="6f88e-p102">En la pestaña **Probar enrutamiento de voz**, Seleccione el caso de prueba (o los casos de prueba) que va a exportar. Para seleccionar varios casos de prueba, haga clic en el primer caso que se va a exportar, luego mantenga presionada la tecla Ctrl y seleccione los casos adicionales.</span><span class="sxs-lookup"><span data-stu-id="6f88e-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="6f88e-112">Haga clic en **Acciones** y luego en **Exportar casos de prueba**.</span><span class="sxs-lookup"><span data-stu-id="6f88e-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="6f88e-p103">En el cuadro de diálogo **Guardar como**, seleccione una carpeta para almacenar los casos de prueba exportados y escriba un nombre para el archivo XML resultante en el cuadro **Nombre de archivo**. Tenga en cuenta que si va a exportar varios casos de prueba, todos ellos se guardarán en un fichero XML.</span><span class="sxs-lookup"><span data-stu-id="6f88e-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="6f88e-115">Para guardar los casos de prueba, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f88e-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f88e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f88e-116">See Also</span></span>


[<span data-ttu-id="6f88e-117">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f88e-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

