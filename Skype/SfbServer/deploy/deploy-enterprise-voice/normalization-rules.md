---
title: Crear o modificar una regla de normalización en Skype para la empresa
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumen: Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype para Business Server.'
ms.openlocfilehash: ef796d1484ec3848d7c6488127009f97ccc565ee
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882158"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="cf114-103">Crear o modificar una regla de normalización en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="cf114-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="cf114-104">**Resumen:** Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf114-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="cf114-105">Definir, crear y modificar reglas de normalización en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf114-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="cf114-106">Para definir una regla de normalización con Crear regla de normalización</span><span class="sxs-lookup"><span data-stu-id="cf114-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="cf114-107">Abra Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="cf114-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cf114-108">(Opcional) Siga los pasos descritos en [crear o modificar un plan de marcado de Skype para Business Server](dial-plans.md) a través de paso 11 o [modificar un Plan de marcado](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) hasta el paso 10.</span><span class="sxs-lookup"><span data-stu-id="cf114-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="cf114-109">En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón de número que se normalizará en **nombre** (por ejemplo, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="cf114-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="cf114-110">(Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="cf114-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cf114-111">En **Generar regla de normalización**, escriba valores en los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="cf114-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="cf114-112">**Dígitos iniciales** (Opcional) Especificar los dígitos a la izquierda de los números marcados que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="cf114-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="cf114-113">Por ejemplo, type425 si desea que coincida el patrón marcado números que comienzan con 425.</span><span class="sxs-lookup"><span data-stu-id="cf114-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="cf114-114">**Longitud** Especificar el número de dígitos en el patrón coincidente y seleccione si desea que el patrón debe coincidir exactamente con este valor de longitud, coincidencia los números que tienen al menos esta longitud marcados con o números de cualquier longitud marcados de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="cf114-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="cf114-115">**Dígitos para quitar** (Opcional) Especifique el número de dígitos que se quitará de los números marcados iniciales que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="cf114-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="cf114-116">**Dígitos a agregar.** (Opcional) Especificar los dígitos que se agrega a los números marcados que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="cf114-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

    <span data-ttu-id="cf114-117">Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="cf114-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="cf114-118">Por ejemplo, si deja Tipo7 vacía, **dígitos de inicio** en el campo de **longitud** y seleccione **exactamente**y especificar 0 en **dígitos para quitar**, la expresión regular resultante en el **modelo de coincidencia** es:</span><span class="sxs-lookup"><span data-stu-id="cf114-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

    <span data-ttu-id="cf114-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="cf114-119">^(\d{7})$</span></span>

6. <span data-ttu-id="cf114-120">En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="cf114-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="cf114-121">Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="cf114-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="cf114-122">Por ejemplo, si el patrón coincidente es ^(\d{7})$, a continuación, $1 en la traducción de la regla representa los números marcados de 7 dígitos.</span><span class="sxs-lookup"><span data-stu-id="cf114-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="cf114-123">(Opcional) Escriba un valor en el campo **dígitos a agregar** para especificar los dígitos para ser antepone del número convertido (por ejemplo, + 1425).</span><span class="sxs-lookup"><span data-stu-id="cf114-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

    <span data-ttu-id="cf114-124">Por ejemplo, si el **modelo de coincidencia** contiene ^(\d{7})$ como el patrón para los números marcados con y contiene la **regla de conversión** + 1425$ 1 como el patrón para E.164 números de teléfono, la regla 5550100 en + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="cf114-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cf114-125">(Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.</span><span class="sxs-lookup"><span data-stu-id="cf114-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cf114-p104">(Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.</span><span class="sxs-lookup"><span data-stu-id="cf114-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf114-128">Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="cf114-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="cf114-129">Para obtener información detallada, vea [Probar enrutamiento de voz](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf114-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="cf114-130">Haga clic en **Aceptar** para guardar la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="cf114-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cf114-131">Haga clic en **Aceptar** para guardar el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="cf114-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cf114-132">En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="cf114-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf114-133">Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="cf114-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cf114-134">Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="cf114-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="cf114-135">Para definir una regla de normalización de forma manual</span><span class="sxs-lookup"><span data-stu-id="cf114-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="cf114-136">Abra Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="cf114-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cf114-137">(Opcional) Siga los pasos descritos en [crear o modificar un plan de marcado de Skype para Business Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cf114-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="cf114-138">En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón de número que se normalizará en **nombre** (por ejemplo, nombre de la rule5DigitExtension de normalización).</span><span class="sxs-lookup"><span data-stu-id="cf114-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="cf114-139">(Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="cf114-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cf114-140">En **Crear regla de normalización**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cf114-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="cf114-141">Especifique lo siguiente en **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="cf114-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="cf114-142">En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.</span><span class="sxs-lookup"><span data-stu-id="cf114-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="cf114-143">En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.</span><span class="sxs-lookup"><span data-stu-id="cf114-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

    <span data-ttu-id="cf114-144">Por ejemplo, si escribe ^(\d{7})$ en **este patrón de coincidencia** y + 1425$ 1 en **regla de conversión**, la regla 5550100 en + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="cf114-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cf114-145">(Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.</span><span class="sxs-lookup"><span data-stu-id="cf114-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cf114-p107">(Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.</span><span class="sxs-lookup"><span data-stu-id="cf114-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="cf114-148">Haga clic en **Aceptar** para guardar la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="cf114-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cf114-149">Haga clic en **Aceptar** para guardar el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="cf114-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cf114-150">En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="cf114-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf114-151">Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="cf114-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cf114-152">Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="cf114-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


