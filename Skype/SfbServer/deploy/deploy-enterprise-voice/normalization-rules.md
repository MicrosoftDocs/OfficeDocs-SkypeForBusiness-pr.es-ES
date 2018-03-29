---
title: Crear o modificar una regla de normalización en Skype Empresarial 2015
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumen: Aprender a definir, crear y modificar una regla de normalización en Skype para Business Server 2015.'
ms.openlocfilehash: 5b55e5e930680d3c51908b77d44a80e2e74ef89c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business-2015"></a>Crear o modificar una regla de normalización en Skype Empresarial 2015
 
**Resumen:** Aprenda a definir, crear y modificar una regla de normalización en Skype para Business Server 2015.
  
Definir, crear y modificar reglas de normalización en Skype para Business Server.
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir una regla de normalización con Crear regla de normalización

1. Abre Skype para Panel de Control de servidor empresarial
    
2. (Opcional) Siga los pasos del [crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md) a través de paso 11 o [modificar un Plan de marcado](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) en el paso 10.
    
3. En la **Regla de normalización de nuevo** o **Editar regla de normalización**, escriba un nombre que describa el patrón del número que se está normalizando en **nombre** (por ejemplo, 5DigitExtension).
    
4. (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
    
5. En **Generar regla de normalización**, escriba valores en los siguientes campos:
    
   - **A partir de dígitos** (Opcional) Especificar los dígitos de los números marcados que desee el modelo de coincidencia. Por ejemplo, type425 si desea que el modelo de coincidencia marcar números que comienzan con 425.
    
   - **Longitud** Especificar el número de dígitos en el modelo correspondiente y seleccione si desea que el modelo debe coincidir exactamente con la longitud de esta, coincidencia marcaba números que están por lo menos esta longitud o coincidencia marcaba números de cualquier longitud.
    
   - **Dígitos para quitar** (Opcional) Especificar el número de dígitos que se quitará de los números marcados de inicio que desee el modelo de coincidencia.
    
   - **Dígitos para agregar** (Opcional) Especificar dígitos que se agrega a los números marcados y que desea que el modelo de coincidencia.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que coincidir** y **Regla de conversión**. Por ejemplo, si deja Tipo7 vacío, **dígitos de inicio** en el campo **longitud** , seleccione **exactamente**y especifique 0 en **dígitos para quitar**, la expresión regular resultante en el **modelo de coincidencia** es:
    
    ^(\d{7})$
    
6. En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos como se indica a continuación:
    
   - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el modelo coincidente es ^ (\d{7})$ $1, a continuación, en la regla de traducción representa números marcados de 7 dígitos.
    
   - (Opcional) Escriba un valor en el campo de **dígitos que se deben agregar** para especificar dígitos anteponer al número traducido (por ejemplo, +1425).
    
    Por ejemplo, si el **modelo de coincidencia** contains^(\d{7})$ como modelo para los números marcados y **regla de traducción** contiene + 1425$ 1 como modelo para E.164 números de teléfono, la regla normaliza 5550100 a +14255550100.
    
7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
    
8. (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, vea [Enrutamiento de voz de prueba](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx). 
  
9. Haga clic en **Aceptar** para guardar la regla de normalización.
    
10. Haga clic en **Aceptar** para guardar el plan de marcado.
    
11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  
### <a name="to-define-a-normalization-rule-manually"></a>Para definir una regla de normalización de forma manual

1. Abre Skype para Panel de Control de servidor empresarial
    
2. (Opcional) Siga los pasos del [crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md). 
    
3. En la **Regla de normalización de nuevo** o **Editar regla de normalización**, escriba un nombre que describa el patrón del número que se está normalizando en **nombre** (por ejemplo, el nombre de la rule5DigitExtension de normalización).
    
4. (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").
    
5. En **Crear regla de normalización**, haga clic en **Editar**.
    
6. Especifique lo siguiente en **Escribir una expresión regular**:
    
   - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    
   - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.
    
    Por ejemplo, si escribe ^ (\d{7})$ en **este patrón de coincidencia** y + 1425$ 1 en la **regla de conversión**, la regla se normaliza 5550100 a +14255550100.
    
7. (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.
    
8. (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
9. Haga clic en **Aceptar** para guardar la regla de normalización.
    
10. Haga clic en **Aceptar** para guardar el plan de marcado.
    
11. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    > [!NOTE]
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  

