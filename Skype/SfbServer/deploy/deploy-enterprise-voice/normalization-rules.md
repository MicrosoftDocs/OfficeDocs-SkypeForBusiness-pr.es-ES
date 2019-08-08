---
title: Crear o modificar una regla de normalización en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumen: Aprenda a definir, crear y modificar una regla de normalización en Skype empresarial Server.'
ms.openlocfilehash: af0f09710d427dc97a919468b5decfa9ef3d93fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240263"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Crear o modificar una regla de normalización en Skype empresarial

**Resumen:** Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype empresarial Server.

Definir, crear y modificar reglas de normalización en Skype empresarial Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir una regla de normalización con Crear regla de normalización

1. Abrir el panel de control de Skype empresarial Server

2. Faculta Siga los pasos que se indican en [crear o modificar un plan de marcado en Skype empresarial Server](dial-plans.md) por medio del paso 11 o [modificar un plan de marcado mediante el](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) paso 10.

3. En **nueva regla** de normalización o **Editar regla**de normalización, escriba un nombre que describa el patrón de números que se está normalizando en **nombre** (por ejemplo, 5DigitExtension).

4. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

5. En **Generar regla de normalización**, escriba valores en los siguientes campos:

   - **Dígitos iniciales** Faculta Especifique los dígitos iniciales de los números marcados que desea que coincidan con el patrón. Por ejemplo, type425 si desea que el patrón coincida con los números marcados que comienzan con 425.

   - **Duración** Especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincide con números marcados que tienen al menos esta longitud o que coinciden con números marcados de cualquier longitud.

   - **Dígitos para quitar** Faculta Especifique el número de dígitos iniciales que se van a quitar de los números marcados que desea que coincidan con el diseño.

   - **Dígitos para agregar** Faculta Especifique los dígitos que se van a agregar a los números marcados que desea que coincidan con el patrón.

     Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**. Por ejemplo, si deja los **dígitos iniciales** en blanco, Type7 en el campo **longitud** y selecciona **exactamente**, y especifica 0 en **dígitos para quitar**, la expresión regular resultante en el **patrón para coincidir** es:

     ^ (\d{7}) $

6. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:

   - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón correspondiente es ^ (\d{7}) $1, en la regla de traducción se representan los números marcados de 7 dígitos.

   - Faculta Escriba un valor en el campo **dígitos para agregar** para especificar los dígitos que se van a anteponer al número traducido (por ejemplo, + 1425).

     Por ejemplo, si el **modelo que coincide** contiene ^ ({7}\d) $ como el patrón para los números marcados y la **regla de traducción** contiene + 1425 $1 como patrón para E. 164 números de teléfono, la regla normaliza 5550100 a + 14255550100.

7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

8. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener información detallada, consulte [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Haga clic en **Aceptar** para guardar la regla de normalización.

10. Haga clic en **Aceptar** para guardar el plan de marcado.

11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.

### <a name="to-define-a-normalization-rule-manually"></a>Para definir una regla de normalización de forma manual

1. Abrir el panel de control de Skype empresarial Server

2. Faculta Siga los pasos que se indican en [crear o modificar un plan de marcado en Skype empresarial Server](dial-plans.md).

3. En **nueva regla** de normalización o **Editar regla**de normalización, escriba un nombre que describa el patrón de números que se está normalizando en **nombre** (por ejemplo, asigne un nombre a la rule5DigitExtension de normalización).

4. (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

5. En **Crear regla de normalización**, haga clic en **Editar**.

6. Especifique lo siguiente en **Escribir una expresión regular**:

   - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.

   - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.

     Por ejemplo, si escribe ^ (\d{7}) $ en **coincidencia con este patrón** y + 1425 $1 en la regla de **traducción**, la regla normaliza 5550100 a + 14255550100.

7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

8. (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.

9. Haga clic en **Aceptar** para guardar la regla de normalización.

10. Haga clic en **Aceptar** para guardar el plan de marcado.

11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.


