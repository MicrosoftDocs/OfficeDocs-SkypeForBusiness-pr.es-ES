---
title: Crear o modificar una regla de normalización en Skype Empresarial
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumen: aprenda a definir, crear y modificar una regla de normalización en Skype Empresarial Server.'
ms.openlocfilehash: f2f47859687a7c3919e59979c259f317ef6a3102
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387278"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Crear o modificar una regla de normalización en Skype Empresarial

**Resumen:** Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype Empresarial Server.

Defina, cree y modifique reglas de normalización en Skype Empresarial Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir una regla de normalización mediante Crear una regla de normalización

1. Abrir Skype Empresarial Server panel de control

2. (Opcional) Siga los pasos de [Crear o](dial-plans.md) modificar un plan de marcado en Skype Empresarial Server paso 11 o [Modificar un plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) de marcado a través del paso 10.

3. En **Nueva regla de normalización** o Editar regla de **normalización**, escriba un nombre que describa el patrón de números que se normaliza en **Name** (por ejemplo, 5DigitExtension).

4. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

5. En **Generar regla de normalización**, escriba valores en los siguientes campos:

   - **Dígitos iniciales** (opcional) Especifique los dígitos iniciales de los números marcados que desea que coincidan con el patrón. Por ejemplo, escriba425 si desea que el patrón coincida con los números marcados a partir de 425.

   - **Longitud** Especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincida con números marcados que sean al menos de esta longitud o que coincidan con los números marcados de cualquier longitud.

   - **Dígitos para quitar** (opcional) Especifique el número de dígitos iniciales que se quitarán de los números marcados que desea que coincida el patrón.

   - **Dígitos para agregar** (opcional) Especifique los dígitos que se agregarán a los números marcados que desee que coincidan con el patrón.

     Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si deja los  dígitos iniciales vacíos, escriba7 en el campo Longitud y seleccione **Exactamente y especifique** 0 en **Dígitos** para quitar, la expresión regular resultante en el **patrón** que se va a coincidir es:

     ^(\d{7})$

6. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:

   - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es ^(\d{7})$ , $1 en la regla de traducción representa números marcados de 7 dígitos.

   - (Opcional) Escriba un valor en el **campo Dígitos** para agregar para especificar los dígitos que se deben anteponer al número traducido (por ejemplo, +1425).

     Por ejemplo, si **pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.

7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

8. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para más información, vea [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

9. Haga clic en **Aceptar** para guardar la regla de normalización.

10. Haga clic en **Aceptar** para guardar el plan de marcado.

11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

### <a name="to-define-a-normalization-rule-manually"></a>Para definir una regla de normalización de forma manual

1. Abrir Skype Empresarial Server panel de control

2. (Opcional) Siga los pasos de [Crear o modificar un plan de marcado en Skype Empresarial Server](dial-plans.md).

3. En **Nueva regla de normalización** o Editar regla de **normalización**, escriba un nombre que describa el patrón de números que se normaliza en **Name** (por ejemplo, asigne un nombre a la regla de normalización5DigitExtension).

4. (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

5. En **Generar regla de normalización**, haga clic en **Editar**.

6. Especifique lo siguiente en **Escribir una expresión regular**:

   - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.

   - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

     Por ejemplo, si escribe ^(\d{7})$ en Coincidir  con este patrón y +1425$1 en la regla de **traducción, la** regla normalizará de 5550100 a +14255550100.

7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

8. (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

9. Haga clic en **Aceptar** para guardar la regla de normalización.

10. Haga clic en **Aceptar** para guardar el plan de marcado.

11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.