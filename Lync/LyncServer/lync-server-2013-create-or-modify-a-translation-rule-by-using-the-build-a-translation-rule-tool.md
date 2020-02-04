---
title: Crear o modificar una regla de traducción con la herramienta generar una regla de traducción
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
ms.openlocfilehash: d45ca4e04146a175ec2782aa798ac27559fce495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="ff5ff-102">Crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5ff-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff5ff-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="ff5ff-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="ff5ff-104">Siga estos pasos si desea definir una regla de traducción escribiendo un conjunto de valores en la herramienta **generar una regla de traducción** y habilitando el panel de control de Lync Server para generar la regla de traducción y el patrón de coincidencia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="ff5ff-105">También tiene la opción de escribir una expresión regular manualmente para definir el patrón de correspondencia y la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="ff5ff-106">Para obtener más información, vea [crear o modificar una regla de traducción de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="ff5ff-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="ff5ff-107">Para definir una regla mediante el uso de la herramienta Crear una regla de conversión</span><span class="sxs-lookup"><span data-stu-id="ff5ff-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="ff5ff-108">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ff5ff-109">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ff5ff-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ff5ff-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff5ff-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ff5ff-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff5ff-112">Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin evitar los medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) a paso 9.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="ff5ff-113">En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="ff5ff-114">(Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International long-distance dialing**.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="ff5ff-115">En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff5ff-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="ff5ff-116">**Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="ff5ff-117">Por ejemplo, escriba **+** en este campo para encontrarse números en formato E. 164 (que comienzan con +).</span><span class="sxs-lookup"><span data-stu-id="ff5ff-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="ff5ff-p105">**Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba **11** y seleccione **At least** en la lista desplegable para que haya coincidencias con números de al menos 11 dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="ff5ff-120">**Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="ff5ff-121">Por ejemplo, escriba **1** para quitar el **+** principio del número.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="ff5ff-p107">**Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba **011** si desea que se agregue 011 a los números convertidos cuando se aplique la regla.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="ff5ff-p108">Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:</span><span class="sxs-lookup"><span data-stu-id="ff5ff-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="ff5ff-126">**^\\+ (\\d{9}\\+) $**</span><span class="sxs-lookup"><span data-stu-id="ff5ff-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="ff5ff-p109">El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="ff5ff-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="ff5ff-129">Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón con el que hacer coincidir.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="ff5ff-130">(Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="ff5ff-131">Al usar los valores del ejemplo anterior, aparecerá **011$1** en el campo **Regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="ff5ff-132">Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="ff5ff-133">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="ff5ff-134">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="ff5ff-135">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ff5ff-136">Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ff5ff-137">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="ff5ff-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff5ff-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff5ff-138">See Also</span></span>


[<span data-ttu-id="ff5ff-139">Crear o modificar una regla de traducción de forma manual en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5ff-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="ff5ff-140">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5ff-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ff5ff-141">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5ff-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="ff5ff-142">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5ff-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ff5ff-143">Opciones de omisión de multimedia global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5ff-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

