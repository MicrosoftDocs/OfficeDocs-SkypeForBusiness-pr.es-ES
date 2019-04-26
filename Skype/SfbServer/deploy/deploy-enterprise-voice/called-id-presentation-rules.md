---
title: Crear o modificar una regla de conversión para llamado presentación del identificador de Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumen: Obtenga información sobre cómo definir una regla de conversión mediante la compilación una herramienta de la regla de conversión de Skype para Business Server.'
ms.openlocfilehash: 947dc6a76482fc5b00efaeb71463b35eab9f9cea
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223750"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="e798b-103">Crear o modificar una regla de conversión para llamado presentación del identificador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e798b-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="e798b-104">**Resumen:** Obtenga información sobre cómo definir una regla de conversión mediante la compilación una herramienta de la regla de conversión de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e798b-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="e798b-105">Siga estos pasos si desea definir una regla de conversión especificando un conjunto de valores en la herramienta de **creación de una regla de conversión** y habilitación de Skype para Panel de Control de servidor empresarial generar el patrón coincidente correspondiente y la regla de conversión para usted.</span><span class="sxs-lookup"><span data-stu-id="e798b-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="e798b-106">También tiene la opción de escribir una expresión regular manualmente para definir el patrón de correspondencia y la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="e798b-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="e798b-107">Para obtener más información, consulte [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="e798b-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="e798b-108">Para definir una regla mediante el uso de la herramienta Crear una regla de conversión</span><span class="sxs-lookup"><span data-stu-id="e798b-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="e798b-109">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e798b-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="e798b-110">Para empezar a definir una regla de conversión, siga los pasos descritos en [Configure un tronco con medios de desvío en Skype para Business Server](configure-trunk-with-media-bypass.md) a través de paso 10 o [Configure un tronco sin medios desvío en Skype para Business Server](configure-trunk-without-media-bypass.md) hasta el paso 9.</span><span class="sxs-lookup"><span data-stu-id="e798b-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e798b-111">En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="e798b-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e798b-112">(Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo marcado de larga distancia internacional de Ee.uu..</span><span class="sxs-lookup"><span data-stu-id="e798b-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e798b-113">En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e798b-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="e798b-114">**Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="e798b-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="e798b-115">Por ejemplo, escriba + en este campo para que se cree una correspondencia con números en formato E.164 (que comienzan con +).</span><span class="sxs-lookup"><span data-stu-id="e798b-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="e798b-116">**Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud.</span><span class="sxs-lookup"><span data-stu-id="e798b-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="e798b-117">Por ejemplo, escriba 11 y selectAt menos en la lista desplegable para que coincida con números de al menos de 11 dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="e798b-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="e798b-118">**Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="e798b-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="e798b-119">Por ejemplo, escriba 1 para que se quite el + desde el principio del número.</span><span class="sxs-lookup"><span data-stu-id="e798b-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="e798b-120">**Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="e798b-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="e798b-121">Por ejemplo, escriba 011 si desea que se agregue 011 a los números convertidos cuando se aplique la regla.</span><span class="sxs-lookup"><span data-stu-id="e798b-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="e798b-p106">Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:</span><span class="sxs-lookup"><span data-stu-id="e798b-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="e798b-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="e798b-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="e798b-125">El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="e798b-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="e798b-126">Este patrón tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="e798b-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="e798b-127">Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón con el que hacer coincidir.</span><span class="sxs-lookup"><span data-stu-id="e798b-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="e798b-128">(Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.</span><span class="sxs-lookup"><span data-stu-id="e798b-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="e798b-129">Al usar los valores del ejemplo anterior, aparecerá 011$1 en el campo **Regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="e798b-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="e798b-130">Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e798b-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="e798b-131">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="e798b-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="e798b-132">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="e798b-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="e798b-133">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="e798b-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e798b-134">Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e798b-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e798b-135">Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="e798b-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="e798b-136">Para definir una regla de conversión de forma manual</span><span class="sxs-lookup"><span data-stu-id="e798b-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="e798b-137">Abra Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="e798b-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e798b-138">Para empezar a definir una regla de conversión, siga los pasos descritos en [Configure un tronco con medios de desvío en Skype para Business Server](configure-trunk-with-media-bypass.md) a través de paso 10 o [Configure un tronco sin medios desvío en Skype para Business Server](configure-trunk-without-media-bypass.md) hasta el paso 9.</span><span class="sxs-lookup"><span data-stu-id="e798b-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e798b-139">En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="e798b-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e798b-140">(Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo nos larga distancia internacional de marcado.</span><span class="sxs-lookup"><span data-stu-id="e798b-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e798b-141">Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="e798b-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="e798b-142">Especifique lo siguiente en **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="e798b-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e798b-143">En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="e798b-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="e798b-144">En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="e798b-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="e798b-145">Por ejemplo, si especifica ^\+(\d{9}\d+)$ en **este patrón de coincidencia** and011$ 1 en **regla de conversión**, la regla convertirá + 441235551010 a 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e798b-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="e798b-146">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="e798b-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="e798b-147">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="e798b-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="e798b-148">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="e798b-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e798b-149">Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e798b-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e798b-150">Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="e798b-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e798b-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="e798b-151">See also</span></span>

[<span data-ttu-id="e798b-152">Configurar un tronco con desvío de medios en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e798b-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="e798b-153">Configurar un tronco sin desvío de medios en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e798b-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="e798b-154">Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="e798b-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="e798b-155">Implementar el desvío de medios en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e798b-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

