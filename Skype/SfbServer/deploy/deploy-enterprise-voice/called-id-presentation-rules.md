---
title: Crear o modificar una regla de traducción para la presentación de identificador llamada en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumen: Aprenda a definir una regla de traducción con la herramienta crear una regla de traducción en Skype empresarial Server.'
ms.openlocfilehash: 13e89fd836c971085a3a1fc40b7e60793e10eb68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275874"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de traducción para la presentación de identificador llamada en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo definir una regla de traducción con la herramienta crear una regla de traducción en Skype empresarial Server.

Siga estos pasos si desea definir una regla de traducción escribiendo un conjunto de valores en la herramienta **generar una regla de traducción** y habilitando el panel de control de Skype empresarial Server para generar la regla de traducción y el patrón de coincidencia correspondiente. También tiene la opción de escribir una expresión regular manualmente para definir el patrón de correspondencia y la regla de conversión. Para obtener más información, consulte [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir una regla mediante el uso de la herramienta Crear una regla de conversión

1. Abra el panel de control de Skype empresarial Server.

2. Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Skype empresarial Server](configure-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin omitir los medios en Skype empresarial Server](configure-trunk-without-media-bypass.md) a través del paso 9.

3. En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.

4. Faculta En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, España internacional de llamadas de larga distancia.

5. En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:

   - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón. Por ejemplo, escriba + en este campo para que se cree una correspondencia con números en formato E.164 (que comienzan con +).

   - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba 11 y selectAt menos en la lista desplegable para buscar números que tengan una longitud mínima de 11 dígitos.

   - **Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar. Por ejemplo, escriba 1 para quitar el signo + del principio del número.

   - **Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba 011 si desea que se agregue 011 a los números convertidos cuando se aplique la regla.

     Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:

     ^\+(\d{9}\d +) $

     El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:

   - Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón con el que hacer coincidir.

   - (Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.

     Al usar los valores del ejemplo anterior, aparecerá 011$1 en el campo **Regla de conversión**.

     Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.

6. Haga clic en **Aceptar** para guardar la regla de conversión.

7. Haga clic en **Aceptar** para guardar la configuración de tronco.

8. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

   > [!NOTE]
   > Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.

### <a name="to-define-a-translation-rule-manually"></a>Para definir una regla de conversión de forma manual

1. Abrir el panel de control de Skype empresarial Server

2. Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Skype empresarial Server](configure-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin omitir los medios en Skype empresarial Server](configure-trunk-without-media-bypass.md) a través del paso 9.

3. En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.

4. Faculta En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, España internacional de llamadas de larga distancia.

5. Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.

6. Especifique lo siguiente en **Escribir una expresión regular**:

   - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.

   - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

     Por ejemplo,\+si escribe ^ (\d{9}\d +) $ y **coincide con este patrón** and011 $1 en la regla de **traducción**, la regla traducirá + 441235551010 a 011441235551010.

7. Haga clic en **Aceptar** para guardar la regla de conversión.

8. Haga clic en **Aceptar** para guardar la configuración de tronco.

9. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.

## <a name="see-also"></a>Vea también

[Configurar un tronco con la omisión de medios en Skype empresarial Server](configure-trunk-with-media-bypass.md)

[Configurar un tronco sin omisión de medios en Skype empresarial Server](configure-trunk-without-media-bypass.md)

[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype empresarial](voice-route-config-changes.md)

[Implementación de omisión de contenido multimedia en Skype empresarial Server](deploy-media-bypass.md)

