---
title: Crear o modificar una regla de normalización mediante la creación de una regla de normalización
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519d4d8ee00e0922d40155c541b0f869df095ab1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="75524-102">Crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75524-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75524-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="75524-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="75524-104">Complete los pasos siguientes si desea crear o modificar una regla de normalización en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75524-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="75524-105">Como alternativa, si desea crear o modificar una regla de normalización de forma manual, vea [crear o modificar una regla de normalización de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="75524-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="75524-106">Para definir una regla mediante la creación de una regla de normalización</span><span class="sxs-lookup"><span data-stu-id="75524-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="75524-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="75524-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="75524-108">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="75524-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="75524-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75524-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75524-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75524-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75524-111">Faculta Siga los pasos que se indican en [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) al paso 11 o [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) a paso 10.</span><span class="sxs-lookup"><span data-stu-id="75524-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="75524-112">En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="75524-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="75524-113">(Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="75524-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="75524-114">En **Generar regla de normalización**, escriba valores en los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="75524-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="75524-115">**Dígitos iniciales (**   opcional) especifique los dígitos iniciales de los números marcados que desea que coincidan con el diseño.</span><span class="sxs-lookup"><span data-stu-id="75524-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="75524-116">Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.</span><span class="sxs-lookup"><span data-stu-id="75524-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="75524-117">**Longitud**   especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincide con números marcados que tienen al menos esta longitud o que coinciden con números marcados de cualquier longitud.</span><span class="sxs-lookup"><span data-stu-id="75524-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="75524-118">**Dígitos para quitar**   (opcional) especifique la cantidad de dígitos iniciales que quiere que se quiten de los números marcados a los que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="75524-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="75524-119">**Dígitos para agregar**   (opcional) especifique los dígitos que desea agregar a los números marcados que desea que coincidan con el patrón.</span><span class="sxs-lookup"><span data-stu-id="75524-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="75524-p105">Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**. Por ejemplo, si deja en blanco **Dígitos iniciales**, escriba **7** en el campo **Longitud** y seleccione **Exactamente**, e introduzca **0** en **Dígitos que se quitarán**, la expresión regular que se creará como resultado en **Patrón con el que hacer coincidir** es:</span><span class="sxs-lookup"><span data-stu-id="75524-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="75524-122">**^ (\\d{7}) $**</span><span class="sxs-lookup"><span data-stu-id="75524-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="75524-123">En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="75524-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="75524-124">Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="75524-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="75524-125">Por ejemplo, si el patrón de coincidencia es **^\\({7}d) $** , **$1** en la regla de traducción representa los números marcados de 7 dígitos.</span><span class="sxs-lookup"><span data-stu-id="75524-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="75524-126">(Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).</span><span class="sxs-lookup"><span data-stu-id="75524-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="75524-127">Por ejemplo, si el **modelo de coincidencia** contiene **^\\({7}d) $** como patrón para los números marcados y la **regla de traducción** contiene **+ 1425 $1** como patrón para E. 164 números de teléfono, la regla normaliza 5550100 a + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="75524-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="75524-128">(Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.</span><span class="sxs-lookup"><span data-stu-id="75524-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="75524-p107">(Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.</span><span class="sxs-lookup"><span data-stu-id="75524-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="75524-131">Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="75524-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="75524-132">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="75524-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="75524-133">Haga clic en **Aceptar** para guardar la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="75524-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="75524-134">Haga clic en **Aceptar** para guardar el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="75524-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="75524-135">En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="75524-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="75524-136">Cuando cree o cambie una regla de normalización, debe ejecutar el
comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="75524-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="75524-137">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="75524-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75524-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="75524-138">See Also</span></span>


[<span data-ttu-id="75524-139">Crear o modificar una regla de normalización manualmente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75524-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="75524-140">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75524-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="75524-141">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75524-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="75524-142">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75524-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="75524-143">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75524-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

