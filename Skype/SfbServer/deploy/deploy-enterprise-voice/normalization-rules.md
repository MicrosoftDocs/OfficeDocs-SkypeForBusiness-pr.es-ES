---
title: Crear o modificar una regla de normalización en Skype Empresarial
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumen: obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype Empresarial Server.'
ms.openlocfilehash: 3550e27884d125f065c4688fec2ace797f9e8ce2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103396"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Crear o modificar una regla de normalización en Skype Empresarial

**Resumen:** Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype Empresarial Server.

Definir, crear y modificar reglas de normalización en Skype Empresarial Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir una regla de normalización mediante Crear una regla de normalización

1. Abrir el Panel de control de Skype Empresarial Server

2. (Opcional) Siga los pasos descritos en [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or Modify a Dial [Plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) through step 10.

3. En **Nueva regla de normalización** o Editar regla de **normalización**, escriba un nombre que describa el patrón de números que se normaliza en **Name** (por ejemplo, 5DigitExtension).

4. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

5. En **Generar regla de normalización**, escriba valores en los siguientes campos:

   - **Dígitos iniciales** (opcional) Especifique los dígitos iniciales de los números marcados que desea que coincidan con el patrón. Por ejemplo, escriba425 si desea que el patrón coincida con los números marcados a partir de 425.

   - **Longitud** Especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincida con números marcados que sean al menos de esta longitud o que coincidan con los números marcados de cualquier longitud.

   - **Dígitos para quitar** (opcional) Especifique el número de dígitos iniciales que se quitarán de los números marcados que desea que coincida el patrón.

   - **Dígitos para agregar** (opcional) Especifique los dígitos que se agregarán a los números marcados que desee que coincidan con el patrón.

     Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si  deja los dígitos  iniciales vacíos, escriba7 en el campo Longitud y seleccione Exactamente **y** especifique 0 en **Dígitos** para quitar , la expresión regular resultante en el patrón que se va a **coincidir** es:

     ^(\d {7} )$

6. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:

   - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es ^(\d )$ entonces$1 en la regla de traducción representa números {7} marcados de 7 dígitos.

   - (Opcional) Escriba un valor en el **campo Dígitos** para agregar para especificar los dígitos que se deben anteponer al número traducido (por ejemplo, +1425).

     Por ejemplo, si **Pattern to match** contiene^(\d )$ como el patrón para números marcados y la regla de traducción contiene +1425$1 como patrón para números de teléfono {7} E.164, la regla normaliza 5550100 a +1425550100. 

7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

8. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para más información, consulte [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

9. Haga clic en **Aceptar** para guardar la regla de normalización.

10. Haga clic en **Aceptar** para guardar el plan de marcado.

11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación sobre operaciones.

### <a name="to-define-a-normalization-rule-manually"></a>Para definir una regla de normalización de forma manual

1. Abrir el Panel de control de Skype Empresarial Server

2. (Opcional) Siga los pasos de [Crear o modificar un plan de marcado en Skype Empresarial Server](dial-plans.md).

3. En **Nueva regla de normalización** o Editar regla de **normalización**, escriba un nombre que describa el patrón de números que se normaliza en **Name** (por ejemplo, asigne un nombre a la regla de normalización5DigitExtension).

4. (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

5. En **Generar regla de normalización**, haga clic en **Editar**.

6. Especifique lo siguiente en **Escribir una expresión regular**:

   - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.

   - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

     Por ejemplo, si escribe ^(\d )$ en Coincidir con este patrón y+1425$1 en la regla de traducción, la regla {7} normaliza de 5550100 a +1425550100.  

7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

8. (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

9. Haga clic en **Aceptar** para guardar la regla de normalización.

10. Haga clic en **Aceptar** para guardar el plan de marcado.

11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación sobre operaciones.