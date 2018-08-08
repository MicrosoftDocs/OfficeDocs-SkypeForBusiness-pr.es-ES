---
title: Crear o modificar una regla de normalización en Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumen: Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype para Business Server.'
ms.openlocfilehash: d9c56d96c0eb9069e4ec02b196a326ad8b599e75
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972551"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Crear o modificar una regla de normalización en Skype para la empresa
 
**Resumen:** Obtenga información sobre cómo definir, crear y modificar una regla de normalización en Skype para Business Server.
  
Definir, crear y modificar reglas de normalización en Skype para Business Server.
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir una regla de normalización con Crear regla de normalización

1. Abra Skype para el Panel de Control de servidor empresarial
    
2. (Opcional) Siga los pasos descritos en [crear o modificar un plan de marcado de Skype para Business Server](dial-plans.md) a través de paso 11 o [modificar un Plan de marcado](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) hasta el paso 10.
    
3. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón de número que se normalizará en **nombre** (por ejemplo, 5DigitExtension).
    
4. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
    
5. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    
   - **Dígitos iniciales** (Opcional) Especificar los dígitos a la izquierda de los números marcados que desea que coincida el patrón. Por ejemplo, type425 si desea que coincida el patrón marcado números que comienzan con 425.
    
   - **Longitud** Especificar el número de dígitos en el patrón coincidente y seleccione si desea que el patrón debe coincidir exactamente con este valor de longitud, coincidencia los números que tienen al menos esta longitud marcados con o números de cualquier longitud marcados de coincidencia.
    
   - **Dígitos para quitar** (Opcional) Especifique el número de dígitos que se quitará de los números marcados iniciales que desea que coincida el patrón.
    
   - **Dígitos a agregar.** (Opcional) Especificar los dígitos que se agrega a los números marcados que desea que coincida el patrón.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**. Por ejemplo, si deja Tipo7 vacía, **dígitos de inicio** en el campo de **longitud** y seleccione **exactamente**y especificar 0 en **dígitos para quitar**, la expresión regular resultante en el **modelo de coincidencia** es:
    
    ^(\d{7})$
    
6. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:
    
   - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón coincidente es ^(\d{7})$, a continuación, $1 en la traducción de la regla representa los números marcados de 7 dígitos.
    
   - (Opcional) Escriba un valor en el campo **dígitos a agregar** para especificar los dígitos para ser antepone del número convertido (por ejemplo, + 1425).
    
    Por ejemplo, si el **modelo de coincidencia** contiene ^(\d{7})$ como el patrón para los números marcados con y contiene la **regla de conversión** + 1425$ 1 como el patrón para E.164 números de teléfono, la regla 5550100 en + 14255550100.
    
7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
    
8. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener información detallada, vea [Probar enrutamiento de voz](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx). 
  
9. Haga clic en **Aceptar** para guardar la regla de normalización.
    
10. Haga clic en **Aceptar** para guardar el plan de marcado.
    
11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.
  
### <a name="to-define-a-normalization-rule-manually"></a>Para definir una regla de normalización de forma manual

1. Abra Skype para el Panel de Control de servidor empresarial
    
2. (Opcional) Siga los pasos descritos en [crear o modificar un plan de marcado de Skype para Business Server](dial-plans.md). 
    
3. En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón de número que se normalizará en **nombre** (por ejemplo, nombre de la rule5DigitExtension de normalización).
    
4. (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
    
5. En **Crear regla de normalización**, haga clic en **Editar**.
    
6. Especifique lo siguiente en **Escribir una expresión regular**:
    
   - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    
   - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.
    
    Por ejemplo, si escribe ^(\d{7})$ en **este patrón de coincidencia** y + 1425$ 1 en **regla de conversión**, la regla 5550100 en + 14255550100.
    
7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
    
8. (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
9. Haga clic en **Aceptar** para guardar la regla de normalización.
    
10. Haga clic en **Aceptar** para guardar el plan de marcado.
    
11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    > [!NOTE]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.
  

