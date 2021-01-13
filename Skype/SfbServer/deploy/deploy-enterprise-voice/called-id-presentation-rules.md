---
title: Crear o modificar una regla de conversión para la presentación de id. llamada en Skype Empresarial Server
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
description: 'Resumen: obtenga información sobre cómo definir una regla de conversión mediante la herramienta Crear una regla de conversión en Skype Empresarial Server.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804201"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de conversión para la presentación de id. llamada en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo definir una regla de conversión mediante la herramienta Crear una regla de conversión en Skype Empresarial Server.

Siga estos pasos si desea definir una regla de conversión  especificando un conjunto de valores en la herramienta Crear una regla de conversión y habilitando el Panel de control de Skype Empresarial Server para generar el patrón de coincidencia y la regla de conversión correspondientes. Como alternativa, puede escribir una expresión regular manualmente para definir el patrón de coincidencia y la regla de conversión. Para obtener más información, [vea Crear o modificar una regla de conversión manualmente.](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir una regla mediante la herramienta Crear una regla de conversión

1. Abra el Panel de control de Skype Empresarial Server.

2. To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or Configure a trunk without media bypass in Skype for Business [Server](configure-trunk-without-media-bypass.md) through step 9.

3. En **Nombre** de la  página **Nueva regla de conversión** o Editar regla de conversión, escriba un nombre que describa el patrón de número que se va a traducir.

4. (Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, marcación de larga distancia internacional de EE. UU.

5. En la **sección Generar una regla de conversión** del cuadro de diálogo, escriba valores en los siguientes campos:

   - **Dígitos iniciales:**(opcional) Especifique los dígitos iniciales de los números que desea que coincidan con el patrón. Por ejemplo, escriba + en este campo para que coincida con los números en formato E.164 (que comienzan por +).

   - **Longitud:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números que sean exactamente de esta longitud, al menos esta longitud o cualquier longitud. Por ejemplo, escriba 11 y seleccione Al menos en la lista desplegable para que coincida con números de al menos 11 dígitos de longitud.

   - **Dígitos para quitar:**(opcional) Especifique el número de dígitos iniciales que se quitarán. Por ejemplo, escriba 1 para quitar el signo + del principio del número.

   - **Dígitos para agregar:**(opcional) Especifique los dígitos que se deben anteponer a los números traducidos. Por ejemplo, escriba 011 si desea que se antepone 011 a los números traducidos cuando se aplica la regla.

     Los valores especificados en estos campos se reflejan en los campos **Patrón** para coincidir y Regla **de** conversión. Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **campo Patrón** para que coincida es:

     ^\+(\d {9} \d+)$

     El **campo de regla** de conversión especifica un patrón para el formato de los números traducidos. Este patrón tiene dos partes:

   - Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón de coincidencia

   - (Opcional) Un valor que puede anteponer si lo escribe en el campo **Dígitos para agregar**

     Con los valores de ejemplo anteriores, aparece 011$1 en el **campo de regla de** conversión.

     Cuando se aplica esta regla de conversión, +441235551010 pasa a ser 011441235551010.

6. Haga clic en **Aceptar** para guardar la regla de conversión.

7. Haga clic en **Aceptar** para guardar la configuración de tronco.

8. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

   > [!NOTE]
   > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

### <a name="to-define-a-translation-rule-manually"></a>Para definir una regla de conversión de forma manual

1. Abrir el Panel de control de Skype Empresarial Server

2. To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or Configure a trunk without media bypass in Skype for Business [Server](configure-trunk-without-media-bypass.md) through step 9.

3. En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.

4. (Opcional) En **Descripción,** escriba una descripción de la regla de conversión, por ejemplo, marcación de larga distancia internacional de EE. UU.

5. Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.

6. Especifique lo siguiente en  **Escribir una expresión regular**:

   - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.

   - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

     Por ejemplo, si escribe ^ (\d \d+)$ en Coincidir con este patrón y 011$1 en la regla de conversión, la regla traducirá \+ {9} +441235551010 a 011441235551010.  

7. Haga clic en **Aceptar** para guardar la regla de conversión.

8. Haga clic en **Aceptar** para guardar la configuración de tronco.

9. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

## <a name="see-also"></a>Ver también

[Configurar un tronco con desvío de medios en Skype Empresarial Server](configure-trunk-with-media-bypass.md)

[Configurar un tronco sin desvío de medios en Skype Empresarial Server](configure-trunk-without-media-bypass.md)

[Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial](voice-route-config-changes.md)

[Implementar la omisión de medios en Skype Empresarial Server](deploy-media-bypass.md)

