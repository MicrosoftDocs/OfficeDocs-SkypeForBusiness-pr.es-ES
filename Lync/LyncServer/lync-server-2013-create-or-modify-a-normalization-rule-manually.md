---
title: 'Lync Server 2013: Crear o modificar una regla de normalización manualmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="edc38-102">Crear o modificar una regla de normalización manualmente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc38-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edc38-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="edc38-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="edc38-104">Complete los pasos siguientes si desea crear o modificar una regla de normalización de forma manual.</span><span class="sxs-lookup"><span data-stu-id="edc38-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="edc38-105">Si desea crear o modificar una regla de normalización mediante la creación de una regla de normalización en el panel de control de Lync Server, vea [crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span><span class="sxs-lookup"><span data-stu-id="edc38-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="edc38-106">Para definir una regla de normalización de forma manual</span><span class="sxs-lookup"><span data-stu-id="edc38-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="edc38-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="edc38-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="edc38-108">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="edc38-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="edc38-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="edc38-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="edc38-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="edc38-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="edc38-111">Faculta Siga los pasos que se indican en [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) o [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="edc38-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="edc38-112">En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, asigne a la regla de normalización el nombre **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="edc38-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="edc38-113">(Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="edc38-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="edc38-114">En **Crear regla de normalización**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="edc38-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="edc38-115">Especifique lo siguiente en **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="edc38-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="edc38-116">En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.</span><span class="sxs-lookup"><span data-stu-id="edc38-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="edc38-117">En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.</span><span class="sxs-lookup"><span data-stu-id="edc38-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="edc38-118">Por ejemplo, si introduce **\\^ (d{7}) $** en **coincidir con este patrón** y **+ 1425 $1** en la **regla de traducción**, la regla normaliza 5550100 a + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="edc38-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="edc38-119">(Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.</span><span class="sxs-lookup"><span data-stu-id="edc38-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="edc38-p104">(Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.</span><span class="sxs-lookup"><span data-stu-id="edc38-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="edc38-122">Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="edc38-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="edc38-123">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="edc38-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="edc38-124">Haga clic en **Aceptar** para guardar la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="edc38-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="edc38-125">Haga clic en **Aceptar** para guardar el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="edc38-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="edc38-126">En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="edc38-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="edc38-127">Cuando cree o cambie una regla de normalización, debe ejecutar el
comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="edc38-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="edc38-128">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="edc38-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="edc38-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="edc38-129">See Also</span></span>


[<span data-ttu-id="edc38-130">Crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc38-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="edc38-131">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc38-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="edc38-132">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc38-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="edc38-133">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc38-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="edc38-134">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc38-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

