---
title: Crear o modificar una regla de conversión para la presentación de id. llamada en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumen: obtenga información sobre cómo definir una regla de conversión mediante la herramienta Crear una regla de conversión en Skype Empresarial Server.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804201"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="c4e80-103">Crear o modificar una regla de conversión para la presentación de id. llamada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c4e80-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="c4e80-104">**Resumen:** Obtenga información sobre cómo definir una regla de conversión mediante la herramienta Crear una regla de conversión en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c4e80-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="c4e80-105">Siga estos pasos si desea definir una regla de conversión  especificando un conjunto de valores en la herramienta Crear una regla de conversión y habilitando el Panel de control de Skype Empresarial Server para generar el patrón de coincidencia y la regla de conversión correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c4e80-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="c4e80-106">Como alternativa, puede escribir una expresión regular manualmente para definir el patrón de coincidencia y la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="c4e80-107">Para obtener más información, [vea Crear o modificar una regla de conversión manualmente.](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4e80-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="c4e80-108">Para definir una regla mediante la herramienta Crear una regla de conversión</span><span class="sxs-lookup"><span data-stu-id="c4e80-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="c4e80-109">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c4e80-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c4e80-110">Para empezar a definir una regla de conversión, siga los pasos descritos en Configurar un tronco con desvío de medios en Skype Empresarial [Server](configure-trunk-with-media-bypass.md) a través del paso 10 o Configurar un tronco sin desvío de medios en Skype [Empresarial Server](configure-trunk-without-media-bypass.md) a través del paso 9.</span><span class="sxs-lookup"><span data-stu-id="c4e80-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c4e80-111">En **Nombre** de la  página **Nueva regla de conversión** o Editar regla de conversión, escriba un nombre que describa el patrón de número que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="c4e80-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c4e80-112">(Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, marcación de larga distancia internacional de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="c4e80-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c4e80-113">En la **sección Generar una regla de conversión** del cuadro de diálogo, escriba valores en los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="c4e80-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="c4e80-114">**Dígitos iniciales:**(opcional) Especifique los dígitos iniciales de los números que desea que coincidan con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c4e80-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="c4e80-115">Por ejemplo, escriba + en este campo para que coincida con los números en formato E.164 (que comienzan por +).</span><span class="sxs-lookup"><span data-stu-id="c4e80-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="c4e80-116">**Longitud:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con los números de esta longitud exactamente, al menos esta longitud o cualquier longitud.</span><span class="sxs-lookup"><span data-stu-id="c4e80-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="c4e80-117">Por ejemplo, escriba 11 y seleccione Al menos en la lista desplegable para que coincida con números de al menos 11 dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="c4e80-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="c4e80-118">**Dígitos para quitar:**(opcional) Especifique el número de dígitos iniciales que se quitarán.</span><span class="sxs-lookup"><span data-stu-id="c4e80-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="c4e80-119">Por ejemplo, escriba 1 para quitar el signo + del principio del número.</span><span class="sxs-lookup"><span data-stu-id="c4e80-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="c4e80-120">**Dígitos para agregar:**(opcional) Especifique los dígitos que se deben anteponer a los números traducidos.</span><span class="sxs-lookup"><span data-stu-id="c4e80-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="c4e80-121">Por ejemplo, escriba 011 si desea que se antepone 011 a los números traducidos cuando se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="c4e80-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="c4e80-122">Los valores especificados en estos campos se reflejan en los campos **Patrón** para coincidir y Regla **de** conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-122">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="c4e80-123">Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **campo Patrón** para que coincida es:</span><span class="sxs-lookup"><span data-stu-id="c4e80-123">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="c4e80-124">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="c4e80-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="c4e80-125">El **campo de regla** de conversión especifica un patrón para el formato de los números traducidos.</span><span class="sxs-lookup"><span data-stu-id="c4e80-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="c4e80-126">Este patrón tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="c4e80-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="c4e80-127">Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón de coincidencia</span><span class="sxs-lookup"><span data-stu-id="c4e80-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="c4e80-128">(Opcional) Un valor que se puede anteponer entrando en el campo **Dígitos para** agregar</span><span class="sxs-lookup"><span data-stu-id="c4e80-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="c4e80-129">Con los valores de ejemplo anteriores, aparece 011$1 en el **campo de regla de** conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="c4e80-130">Cuando se aplica esta regla de conversión, +441235551010 pasa a ser 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="c4e80-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="c4e80-131">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="c4e80-132">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="c4e80-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="c4e80-133">En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="c4e80-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c4e80-134">Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c4e80-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c4e80-135">Para obtener más información, [consulte Publicar cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c4e80-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="c4e80-136">Para definir una regla de conversión de forma manual</span><span class="sxs-lookup"><span data-stu-id="c4e80-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="c4e80-137">Abrir el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c4e80-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="c4e80-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or Configure a trunk without media bypass in Skype for Business [Server](configure-trunk-without-media-bypass.md) through step 9.</span><span class="sxs-lookup"><span data-stu-id="c4e80-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c4e80-139">En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c4e80-140">(Opcional) En **Descripción,** escriba una descripción de la regla de conversión, por ejemplo, marcación de larga distancia internacional de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="c4e80-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c4e80-141">Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="c4e80-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="c4e80-142">Especifique lo siguiente en  **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="c4e80-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="c4e80-143">En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="c4e80-144">En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="c4e80-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="c4e80-145">Por ejemplo, si escribe ^ (\d \d+)$ en Coincidir con este patrón y 011$1 en la regla de conversión, la regla traducirá \+ {9} +441235551010 a 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="c4e80-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="c4e80-146">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="c4e80-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="c4e80-147">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="c4e80-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="c4e80-148">En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="c4e80-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4e80-149">Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c4e80-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c4e80-150">Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c4e80-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4e80-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4e80-151">See also</span></span>

[<span data-ttu-id="c4e80-152">Configurar un tronco con desvío de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c4e80-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="c4e80-153">Configurar un tronco sin desvío de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c4e80-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="c4e80-154">Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c4e80-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="c4e80-155">Implementar la omisión de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c4e80-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

