---
title: 'Lync Server 2013: ejecutar pruebas de enrutamiento de voz informal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="83706-102">Ejecutar pruebas de enrutamiento de voz informal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83706-103">_**Última modificación del tema:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="83706-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="83706-104">Puede usar el cuadro de diálogo **crear información de caso de prueba de enrutamiento de voz** para ejecutar pruebas informales antes de crear un caso de prueba real.</span><span class="sxs-lookup"><span data-stu-id="83706-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="83706-105">Cuando esté satisfecho con el resultado de una prueba, tiene la opción de guardarla como caso de prueba formal.</span><span class="sxs-lookup"><span data-stu-id="83706-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="83706-106">Para ejecutar una prueba de enrutamiento de voz informal</span><span class="sxs-lookup"><span data-stu-id="83706-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="83706-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="83706-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="83706-108">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="83706-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="83706-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83706-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="83706-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83706-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="83706-111">En la barra de navegación izquierda, haga clic en **enrutamiento de voz**y, a continuación, en **probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="83706-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="83706-112">En la página **probar enrutamiento de voz** , haga clic en **crear ruta de voz información del caso de prueba**.</span><span class="sxs-lookup"><span data-stu-id="83706-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="83706-113">En el campo **número marcado** , escriba el número de teléfono que desea usar para esta prueba.</span><span class="sxs-lookup"><span data-stu-id="83706-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="83706-114">Este número se normalizará y se mostrará en el campo **Número normalizado** del panel **resultados** .</span><span class="sxs-lookup"><span data-stu-id="83706-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="83706-115">En la lista **plan de marcado** , seleccione el plan de marcado que se va a usar para probar el número marcado.</span><span class="sxs-lookup"><span data-stu-id="83706-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="83706-116">El valor predeterminado es el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="83706-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="83706-117">Al ejecutar la prueba, la primera regla de normalización del plan de marcado que coincida con el número marcado se mostrará en el campo **regla** de normalización del panel **resultados** .</span><span class="sxs-lookup"><span data-stu-id="83706-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="83706-118">En la lista **Directiva de voz** , seleccione la Directiva de voz que se va a usar para probar el número marcado.</span><span class="sxs-lookup"><span data-stu-id="83706-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="83706-119">El valor predeterminado es la Directiva de voz global.</span><span class="sxs-lookup"><span data-stu-id="83706-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="83706-120">Al ejecutar la prueba, se mostrará el primer registro de uso de RTC coincidente en esta directiva de voz en el **primer campo uso de RTC** del panel **resultados** .</span><span class="sxs-lookup"><span data-stu-id="83706-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="83706-121">Además, la primera ruta de voz coincidente asociada con este registro de uso de RTC se mostrará en el **primer** campo de ruta.</span><span class="sxs-lookup"><span data-stu-id="83706-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="83706-122">Faculta Active la casilla de verificación rellenar **desde el usuario** si desea probar el número marcado con la Directiva de voz asignada a un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="83706-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="83706-123">Haga clic en **examinar** para mostrar el cuadro de diálogo **Seleccionar usuarios de voz de empresa** .</span><span class="sxs-lookup"><span data-stu-id="83706-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="83706-124">Haga clic en **Buscar** para mostrar la lista de usuarios que están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="83706-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="83706-125">Haga doble clic en el nombre de usuario cuya directiva de voz asignada desea usar para esta prueba.</span><span class="sxs-lookup"><span data-stu-id="83706-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="83706-126">El campo de **Directiva** se rellena con la Directiva de voz asignada al usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="83706-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="83706-127">Al ejecutar la prueba, se mostrará el primer registro de uso de la red telefónica conmutada (RTC) en esta directiva de voz en el primer campo de **uso de RTC** del panel **resultados** .</span><span class="sxs-lookup"><span data-stu-id="83706-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="83706-128">Además, la primera ruta de voz coincidente asociada con este registro de uso de RTC se mostrará en el **primer** campo de ruta.</span><span class="sxs-lookup"><span data-stu-id="83706-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="83706-129">Haga clic en **Ejecutar** para ejecutar el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="83706-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="83706-130">Los resultados se muestran en el panel derecho del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="83706-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="83706-131">Faculta Haga clic en **Guardar como** si desea guardar esta configuración de prueba como un caso de prueba formal.</span><span class="sxs-lookup"><span data-stu-id="83706-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="83706-132">En el campo **nombre** del cuadro de diálogo **Guardar información de caso de prueba de enrutamiento de voz** , escriba un nombre único para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="83706-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="83706-133">El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="83706-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="83706-134">Puede tener hasta 32 caracteres de longitud y puede contener cualquier carácter alfanumérico, además de la barra invertida (\\), el punto (.) o el carácter de subrayado (\_).</span><span class="sxs-lookup"><span data-stu-id="83706-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="83706-135">Tenga en cuenta que los campos restantes en el cuadro de diálogo **Guardar información del caso de prueba de enrutamiento de voz** son de solo lectura y se rellenan previamente desde la configuración de prueba informal *y* los resultados.</span><span class="sxs-lookup"><span data-stu-id="83706-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="83706-136">Compruebe que esta es la configuración que desea guardar para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="83706-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83706-137">Los valores de los resultados de la prueba se usan para rellenar previamente los campos en el cuadro de diálogo <STRONG>Guardar información de caso de prueba de enrutamiento de voz</STRONG> de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="83706-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="83706-138">La <STRONG>traducción esperada</STRONG> se rellena previamente con el valor del campo de <STRONG>Número normalizado</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="83706-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="83706-139">La <STRONG>ruta esperada</STRONG> se ha rellenado previamente con el valor del primer campo de <STRONG>ruta</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="83706-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="83706-140">El <STRONG>registro de uso de RTC esperado</STRONG> se rellenó con el valor en el <STRONG>primer campo uso de RTC</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="83706-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="83706-141">Si durante la ejecución de prueba no se encontraron coincidencias para cualquiera de estos valores, el campo correspondiente estará vacío en el cuadro de diálogo <STRONG>Guardar información del caso de prueba de enrutamiento de voz</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="83706-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="83706-142">Haga clic en **Aceptar** para guardar el caso de prueba, o haga clic en **Cancelar** para volver al cuadro de diálogo **ver información del caso de prueba de enrutamiento de voz** para seguir desarrollando la prueba antes de guardarla.</span><span class="sxs-lookup"><span data-stu-id="83706-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="83706-143">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="83706-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83706-144">Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="83706-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="83706-145">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="83706-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83706-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="83706-146">See Also</span></span>


[<span data-ttu-id="83706-147">Crear un caso de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="83706-148">Ejecutar los casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="83706-149">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="83706-150">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="83706-151">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="83706-152">Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83706-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

