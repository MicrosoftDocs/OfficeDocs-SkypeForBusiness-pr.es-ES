---
title: Creación o modificación de una regla de conversión mediante la herramienta generar una regla de conversión
description: Cree o modifique una regla de conversión mediante la herramienta generar una regla de conversión.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116048fff834e797bca76a895f45cd0ebc83ab94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574526"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="ac122-103">Crear o modificar una regla de conversión mediante la herramienta generar una regla de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac122-103">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac122-104">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="ac122-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="ac122-105">Siga estos pasos si desea definir una regla de conversión introduciendo un conjunto de valores en la herramienta **generar una regla de conversión** y habilitando el panel de control de Lync Server para generar el patrón de coincidencia y la regla de conversión correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ac122-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="ac122-106">Como alternativa, puede escribir manualmente una expresión regular para definir el patrón de coincidencia y la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="ac122-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="ac122-107">Para obtener más información, consulte [crear o modificar una regla de conversión de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="ac122-107">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="ac122-108">Para definir una regla mediante la herramienta generar una regla de conversión</span><span class="sxs-lookup"><span data-stu-id="ac122-108">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="ac122-109">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ac122-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ac122-110">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ac122-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ac122-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac122-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ac122-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ac122-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ac122-113">Para empezar a definir una regla de conversión, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) a paso 9.</span><span class="sxs-lookup"><span data-stu-id="ac122-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="ac122-114">En **nombre** en la página **nueva regla de conversión** o **Editar regla de conversión** , escriba un nombre que describa el patrón de número que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="ac122-114">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="ac122-115">Opcional En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International Long-Distance dialing**.</span><span class="sxs-lookup"><span data-stu-id="ac122-115">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="ac122-116">En la sección **crear una regla de conversión** del cuadro de diálogo, escriba los valores en los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac122-116">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="ac122-117">**Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números con los que desea que se ajuste la trama.</span><span class="sxs-lookup"><span data-stu-id="ac122-117">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="ac122-118">Por ejemplo, escriba **+** en este campo para hacer coincidir números en formato E. 164 (que comienzan con +).</span><span class="sxs-lookup"><span data-stu-id="ac122-118">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="ac122-119">**Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con los números que tengan esta longitud, como mínimo, esta longitud o cualquier longitud.</span><span class="sxs-lookup"><span data-stu-id="ac122-119">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="ac122-120">Por ejemplo, escriba **11** y seleccione **al menos** en la lista desplegable para hacer coincidir los números con una longitud de al menos 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac122-120">For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="ac122-121">**Dígitos que se quitarán**: (opcional) especifique el número de dígitos iniciales que se quitarán.</span><span class="sxs-lookup"><span data-stu-id="ac122-121">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="ac122-122">Por ejemplo, escriba **1** para quitar el **+** principio del número.</span><span class="sxs-lookup"><span data-stu-id="ac122-122">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="ac122-123">**Dígitos que se agregarán**: (opcional) especifique los dígitos que se van a anteponer a los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="ac122-123">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="ac122-124">Por ejemplo, escriba **011** si desea anteponer 011 a los números convertidos cuando se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="ac122-124">For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="ac122-125">Los valores que escriba en estos campos se reflejarán en los campos **patrón para coincidir** y **regla de conversión** .</span><span class="sxs-lookup"><span data-stu-id="ac122-125">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="ac122-126">Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante del **patrón para coincidir con** el campo es:</span><span class="sxs-lookup"><span data-stu-id="ac122-126">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="ac122-127">**^\\+ ( \\ d {9} \\ d +) $**</span><span class="sxs-lookup"><span data-stu-id="ac122-127">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="ac122-128">El campo **regla de conversión** especifica un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="ac122-128">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="ac122-129">Este patrón consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="ac122-129">This pattern has two parts:</span></span>
    
      - <span data-ttu-id="ac122-130">Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ac122-130">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="ac122-131">Opcional Un valor que puede anteponer si lo especifica en el campo **dígitos que se agregarán**</span><span class="sxs-lookup"><span data-stu-id="ac122-131">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="ac122-132">Con los valores del ejemplo anterior, se muestra **011 $1** en el campo **regla de conversión** .</span><span class="sxs-lookup"><span data-stu-id="ac122-132">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="ac122-133">Cuando se aplica esta regla de conversión, + 441235551010 se convierte en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="ac122-133">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="ac122-134">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="ac122-134">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="ac122-135">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="ac122-135">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="ac122-136">En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="ac122-136">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ac122-137">Siempre que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ac122-137">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ac122-138">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="ac122-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac122-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac122-139">See Also</span></span>


[<span data-ttu-id="ac122-140">Crear o modificar una regla de conversión de forma manual en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac122-140">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="ac122-141">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac122-141">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ac122-142">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac122-142">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="ac122-143">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac122-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ac122-144">Opciones de omisión de medios globales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac122-144">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

