---
title: Crear o modificar una regla de conversión para presentación del identificador del destinatario de la llamada en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumen: Conozca cómo definir una regla de traducción con una herramienta de traducción regla de la generación en Skype para Business Server 2015.'
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="bc179-103">Crear o modificar una regla de conversión para presentación del identificador del destinatario de la llamada en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc179-103">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bc179-104">**Resumen:** Obtenga información sobre cómo definir una regla de traducción con una herramienta de traducción regla de la generación en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bc179-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bc179-105">Si desea definir una regla de conversión especificando un conjunto de valores en la herramienta de **compilación de una regla de traducción** y habilitar Skype para Panel de Control de servidor empresarial generar el correspondiente modelo coincidente y regla de conversión para, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="bc179-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="bc179-106">También tiene la opción de escribir una expresión regular manualmente para definir el patrón de correspondencia y la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="bc179-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="bc179-107">Para obtener información detallada, vea [creación o modificación de una regla de traducción de forma manual](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc179-107">For details, see [Create or Modify a Translation Rule Manually](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="bc179-108">Para definir una regla mediante el uso de la herramienta Crear una regla de conversión</span><span class="sxs-lookup"><span data-stu-id="bc179-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="bc179-109">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="bc179-109">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="bc179-110">Para empezar a definir una regla de traducción, siga los pasos en [configurar un tronco con medios de derivación en Skype para Business Server 2015](configure-trunk-with-media-bypass.md) paso 10 o [configurar un tronco sin medios de derivación en Skype para Business Server 2015](configure-trunk-without-media-bypass.md) al paso 9.</span><span class="sxs-lookup"><span data-stu-id="bc179-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="bc179-111">En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="bc179-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="bc179-112">(Opcional) En **Descripción**, escriba una descripción de la regla de traducción para llamadas de larga distancia de ejemplo nos internacional.</span><span class="sxs-lookup"><span data-stu-id="bc179-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="bc179-113">En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc179-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="bc179-114">**Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón.</span><span class="sxs-lookup"><span data-stu-id="bc179-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="bc179-115">Por ejemplo, escriba + en este campo para hacer coincidir los números E.164 format (que empiezan por +).</span><span class="sxs-lookup"><span data-stu-id="bc179-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>
    
   - <span data-ttu-id="bc179-116">**Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud.</span><span class="sxs-lookup"><span data-stu-id="bc179-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="bc179-117">Por ejemplo, escriba 11 y selectAt menos en la lista desplegable para que coincida con los números que están por lo menos de 11 dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="bc179-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
   - <span data-ttu-id="bc179-118">**Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="bc179-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="bc179-119">Por ejemplo, escriba 1 para limpiar el + desde el principio del número.</span><span class="sxs-lookup"><span data-stu-id="bc179-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>
    
   - <span data-ttu-id="bc179-120">**Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="bc179-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="bc179-121">Por ejemplo, escriba 011 si desea 011 anteponer a los números traducidos cuando se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="bc179-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="bc179-p106">Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:</span><span class="sxs-lookup"><span data-stu-id="bc179-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="bc179-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="bc179-124">^\+(\d{9}\d+)$</span></span>
    
    <span data-ttu-id="bc179-p107">El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="bc179-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
   - <span data-ttu-id="bc179-127">Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón de coincidencia</span><span class="sxs-lookup"><span data-stu-id="bc179-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>
    
   - <span data-ttu-id="bc179-128">(Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.</span><span class="sxs-lookup"><span data-stu-id="bc179-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="bc179-129">Usando el anterior ejemplo valores 011$ 1 aparece en el campo **regla de traducción** .</span><span class="sxs-lookup"><span data-stu-id="bc179-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="bc179-130">Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="bc179-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>
    
6. <span data-ttu-id="bc179-131">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="bc179-131">Click **OK** to save the translation rule.</span></span>
    
7. <span data-ttu-id="bc179-132">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="bc179-132">Click **OK** to save the trunk configuration.</span></span>
    
8. <span data-ttu-id="bc179-133">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="bc179-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="bc179-134">Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="bc179-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bc179-135">Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="bc179-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="bc179-136">Para definir una regla de conversión de forma manual</span><span class="sxs-lookup"><span data-stu-id="bc179-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="bc179-137">Abre Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="bc179-137">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="bc179-138">Para empezar a definir una regla de traducción, siga los pasos en [configurar un tronco con medios de derivación en Skype para Business Server 2015](configure-trunk-with-media-bypass.md) paso 10 o [configurar un tronco sin medios de derivación en Skype para Business Server 2015](configure-trunk-without-media-bypass.md) al paso 9.</span><span class="sxs-lookup"><span data-stu-id="bc179-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="bc179-139">En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="bc179-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="bc179-140">(Opcional) En **Descripción**, escriba una descripción de la regla de la traducción, por ejemplo nos internacional a larga distancia para marcar.</span><span class="sxs-lookup"><span data-stu-id="bc179-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="bc179-141">Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="bc179-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>
    
6. <span data-ttu-id="bc179-142">Especifique lo siguiente en **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="bc179-142">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="bc179-143">En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="bc179-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
   - <span data-ttu-id="bc179-144">En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="bc179-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="bc179-145">Por ejemplo, si escribe ^\+(\d{9}\d+)$ en **este patrón de coincidencia** and011$ 1 en la **regla de conversión**, la regla se traducirá +441235551010 a 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="bc179-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>
    
7. <span data-ttu-id="bc179-146">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="bc179-146">Click **OK** to save the translation rule.</span></span>
    
8. <span data-ttu-id="bc179-147">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="bc179-147">Click **OK** to save the trunk configuration.</span></span>
    
9. <span data-ttu-id="bc179-148">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="bc179-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bc179-149">Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="bc179-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bc179-150">Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="bc179-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bc179-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc179-151">See also</span></span>

#### 

[<span data-ttu-id="bc179-152">Configurar un tronco con omisión de medios en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc179-152">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](configure-trunk-with-media-bypass.md)
  
[<span data-ttu-id="bc179-153">Configurar un tronco sin medios de derivación en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc179-153">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](configure-trunk-without-media-bypass.md)
  
[<span data-ttu-id="bc179-154">Publicar los cambios pendientes a la configuración de enrutamiento de voz de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="bc179-154">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
#### 

[<span data-ttu-id="bc179-155">Implementar la omisión de medios en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc179-155">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

