---
title: 'Lync Server 2013: Crear un caso de prueba de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="34034-102">Crear un caso de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34034-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34034-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="34034-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="34034-104">Para crear un caso de prueba</span><span class="sxs-lookup"><span data-stu-id="34034-104">To create a test case</span></span>

1.  <span data-ttu-id="34034-105">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="34034-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="34034-106">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="34034-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="34034-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34034-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34034-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="34034-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34034-109">En la barra de navegación izquierda, haga clic en **enrutamiento de voz** y luego en **probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="34034-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="34034-110">En la página **probar enrutamiento de voz** , haga clic en **nuevo** para crear un nuevo caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="34034-111">En **nombre**, escriba un nombre único para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="34034-112">El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="34034-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="34034-113">Puede tener hasta 32 caracteres de longitud y puede contener cualquier carácter alfanumérico, además de la barra invertida (\\), el punto (.) o el carácter de subrayado (\_).</span><span class="sxs-lookup"><span data-stu-id="34034-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="34034-114">En **número marcado para probar**, escriba el número marcado que desea usar para probar la configuración de enrutamiento que especifique para este caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="34034-115">En función del plan de marcado, la ruta y la Directiva de voz, este número se normalizará y se mostrará como salida.</span><span class="sxs-lookup"><span data-stu-id="34034-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="34034-116">En la lista **plan de marcado** , seleccione el plan de marcado que se usará al ejecutar la prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="34034-117">El valor predeterminado es el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="34034-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="34034-118">En la lista **Directiva de voz** , seleccione la Directiva de voz que se va a usar al ejecutar la prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="34034-119">El valor predeterminado es la Directiva de voz global.</span><span class="sxs-lookup"><span data-stu-id="34034-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="34034-120">En **traducción prevista**, escriba el número de teléfono en el formato que espera verlo después de la traducción.</span><span class="sxs-lookup"><span data-stu-id="34034-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="34034-121">Este es el valor del número de teléfono que está probando después de que se haya traducido con la primera regla de normalización que coincida en el plan de marcado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="34034-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="34034-122">Al ejecutar el caso de prueba, si el número que está probando no da como resultado el valor de la **traducción esperada**, se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="34034-123">Faculta En la lista de **uso de RTC esperada** , puede seleccionar el registro de uso de la red de telefonía conmutada (RTC) que espera que se use al ejecutar el caso de prueba, en función del plan de marcado y la Directiva de voz especificados.</span><span class="sxs-lookup"><span data-stu-id="34034-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="34034-124">Si se usa un registro de uso de RTC diferente, se produce un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="34034-125">Faculta En la lista de **rutas esperadas** , puede seleccionar la ruta de voz que espera que se use al ejecutar el caso de prueba, en función del plan de marcado y la Directiva de voz especificados.</span><span class="sxs-lookup"><span data-stu-id="34034-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="34034-126">Si se usa una ruta de voz diferente, se produce un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="34034-127">Faculta Haga clic en **Ejecutar** para ejecutar el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="34034-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="34034-128">Los resultados se muestran en el panel derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="34034-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="34034-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34034-129">Click **OK**.</span></span>

14. <span data-ttu-id="34034-130">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="34034-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34034-131">Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="34034-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="34034-132">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="34034-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="34034-133">Si el plan de marcado que se está usando en la prueba normaliza los números de teléfono que comienzan con un signo más (por ejemplo, + 12065551219), ese plan puede provocar errores en la prueba de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="34034-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="34034-134">(El plan de marcado y la ruta de voz funcionan; de hecho, test-CsDialPlan se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="34034-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="34034-135">Sin embargo, la prueba de enrutamiento de voz podría fallar.) Esto es algo que se debe tener en cuenta al probar las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="34034-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34034-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="34034-136">See Also</span></span>


[<span data-ttu-id="34034-137">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34034-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="34034-138">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34034-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="34034-139">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34034-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="34034-140">Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34034-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

