---
title: Crear o modificar una regla de traducción para la presentación de id. denominada en Skype Empresarial Server
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
description: 'Summary: Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.'
ms.openlocfilehash: 3f4754184e69e7b574709d0272afc9989553cfe5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103646"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="a9183-103">Crear o modificar una regla de traducción para la presentación de id. denominada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a9183-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="a9183-104">**Resumen:** Obtenga información sobre cómo definir una regla de traducción mediante la herramienta Crear una regla de traducción en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a9183-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="a9183-105">Siga estos pasos si desea definir una regla de traducción  especificando un conjunto de valores en la herramienta Crear una regla de traducción y habilitando el Panel de control de Skype Empresarial Server para generar el patrón y la regla de traducción correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a9183-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="a9183-106">Como alternativa, puede escribir una expresión regular manualmente para definir el patrón de coincidencia y la regla de traducción.</span><span class="sxs-lookup"><span data-stu-id="a9183-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="a9183-107">Para obtener más información, [vea Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span><span class="sxs-lookup"><span data-stu-id="a9183-107">For details, see [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="a9183-108">Para definir una regla mediante la herramienta Crear una regla de traducción</span><span class="sxs-lookup"><span data-stu-id="a9183-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="a9183-109">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a9183-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a9183-110">Para empezar a definir una regla de traducción, siga los pasos descritos en Configure [a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 o Configure a trunk without media bypass in Skype for Business [Server](configure-trunk-without-media-bypass.md) through step 9.</span><span class="sxs-lookup"><span data-stu-id="a9183-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="a9183-111">En **Nombre** de la  página **Nueva regla de traducción** o Editar regla de traducción, escriba un nombre que describa el patrón de números que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="a9183-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="a9183-112">(Opcional) En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, marcado de larga distancia internacional de ESTADOS UNIDOS.</span><span class="sxs-lookup"><span data-stu-id="a9183-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="a9183-113">En la **sección Crear una regla de traducción** del cuadro de diálogo, escriba valores en los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a9183-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="a9183-114">**Dígitos iniciales**: (opcional) Especifique los dígitos iniciales de los números que desea que coincidan con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a9183-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="a9183-115">Por ejemplo, escriba + en este campo para que coincida con los números en formato E.164 (que comienzan por +).</span><span class="sxs-lookup"><span data-stu-id="a9183-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="a9183-116">**Length:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números que son exactamente de esta longitud, al menos esta longitud o cualquier longitud.</span><span class="sxs-lookup"><span data-stu-id="a9183-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="a9183-117">Por ejemplo, escriba 11 y selectAt least en la lista desplegable para que coincida con números de al menos 11 dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="a9183-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="a9183-118">**Dígitos para quitar**: (opcional) Especifique el número de dígitos iniciales que se quitarán.</span><span class="sxs-lookup"><span data-stu-id="a9183-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="a9183-119">Por ejemplo, escriba 1 para quitar el + desde el principio del número.</span><span class="sxs-lookup"><span data-stu-id="a9183-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="a9183-120">**Dígitos para agregar**: (opcional) Especifique los dígitos que se deben anteponer a los números traducidos.</span><span class="sxs-lookup"><span data-stu-id="a9183-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="a9183-121">Por ejemplo, escriba 011 si desea que 011 se anteponer a los números traducidos cuando se aplique la regla.</span><span class="sxs-lookup"><span data-stu-id="a9183-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="a9183-122">Los valores especificados en estos campos se reflejan en los campos **Patrón para** coincidir y Regla **de** traducción.</span><span class="sxs-lookup"><span data-stu-id="a9183-122">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="a9183-123">Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **campo Patrón para** coincidir es:</span><span class="sxs-lookup"><span data-stu-id="a9183-123">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="a9183-124">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="a9183-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="a9183-125">El **campo Regla** de traducción especifica un patrón para el formato de los números traducidos.</span><span class="sxs-lookup"><span data-stu-id="a9183-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="a9183-126">Este patrón tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="a9183-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="a9183-127">Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón de coincidencia</span><span class="sxs-lookup"><span data-stu-id="a9183-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="a9183-128">(Opcional) Valor que puede anteponer entrando en el campo **Dígitos para agregar**</span><span class="sxs-lookup"><span data-stu-id="a9183-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="a9183-129">Con los valores de ejemplo anteriores, 011$1 aparece en el **campo Regla de** traducción.</span><span class="sxs-lookup"><span data-stu-id="a9183-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="a9183-130">Cuando se aplica esta regla de traducción, +441235551010 pasa a ser 01144123551010.</span><span class="sxs-lookup"><span data-stu-id="a9183-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="a9183-131">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="a9183-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="a9183-132">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="a9183-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="a9183-133">En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="a9183-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a9183-134">Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="a9183-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a9183-135">Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="a9183-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="a9183-136">Para definir una regla de conversión de forma manual</span><span class="sxs-lookup"><span data-stu-id="a9183-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="a9183-137">Abrir el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a9183-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="a9183-138">Para empezar a definir una regla de traducción, siga los pasos descritos en Configure [a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 o Configure a trunk without media bypass in Skype for Business [Server](configure-trunk-without-media-bypass.md) through step 9.</span><span class="sxs-lookup"><span data-stu-id="a9183-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="a9183-139">En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="a9183-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="a9183-140">(Opcional) En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, marcación de larga distancia de US International.</span><span class="sxs-lookup"><span data-stu-id="a9183-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="a9183-141">Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="a9183-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="a9183-142">Especifique lo siguiente en  **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="a9183-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="a9183-143">En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="a9183-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="a9183-144">En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="a9183-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="a9183-145">Por ejemplo, si escribe ^ (\d \d+)$ en Coincidir con este patrón y011$1 en la regla de traducción, la regla traducirá \+ {9} +441235551010 a 01144123551010.  </span><span class="sxs-lookup"><span data-stu-id="a9183-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="a9183-146">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="a9183-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="a9183-147">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="a9183-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="a9183-148">En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="a9183-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a9183-149">Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="a9183-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a9183-150">Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="a9183-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9183-151">Ver también</span><span class="sxs-lookup"><span data-stu-id="a9183-151">See also</span></span>

[<span data-ttu-id="a9183-152">Configurar un tronco con desvío de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a9183-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="a9183-153">Configurar un tronco sin desvío de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a9183-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="a9183-154">Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a9183-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="a9183-155">Implementar la omisión de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a9183-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)