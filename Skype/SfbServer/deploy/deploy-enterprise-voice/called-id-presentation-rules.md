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
description: 'Resumen: aprenda a definir una regla de traducción mediante la herramienta Crear una regla de traducción en Skype Empresarial Server.'
ms.openlocfilehash: 0f8f511996c8d3a578087c9f4252492fa03ef4237688bcaf68a04f09ed944116
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281293"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de traducción para la presentación de id. denominada en Skype Empresarial Server

**Resumen:** Aprenda a definir una regla de traducción mediante la herramienta Crear una regla de traducción en Skype Empresarial Server.

Siga estos pasos si desea definir una regla de traducción  especificando un conjunto de valores en la herramienta Crear una regla de traducción y habilitando Skype Empresarial Server Panel de control para generar el patrón y la regla de traducción correspondientes. Como alternativa, puede escribir una expresión regular manualmente para definir el patrón de coincidencia y la regla de traducción. Para obtener más información, [vea Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir una regla mediante la herramienta Crear una regla de traducción

1. Abra Skype Empresarial Server Panel de control.

2. Para empezar a definir una regla de traducción, siga los pasos descritos en Configure [a trunk with media bypass in Skype Empresarial Server](configure-trunk-with-media-bypass.md) through step 10 o Configure a trunk without media bypass in [Skype Empresarial Server](configure-trunk-without-media-bypass.md) through step 9.

3. En **Nombre** de la  página **Nueva regla de traducción** o Editar regla de traducción, escriba un nombre que describa el patrón de números que se va a traducir.

4. (Opcional) En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, marcado de larga distancia internacional de ESTADOS UNIDOS.

5. En la **sección Crear una regla de traducción** del cuadro de diálogo, escriba valores en los siguientes campos:

   - **Dígitos iniciales**: (opcional) Especifique los dígitos iniciales de los números que desea que coincidan con el patrón. Por ejemplo, escriba + en este campo para que coincida con los números en formato E.164 (que comienzan por +).

   - **Length:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números que son exactamente de esta longitud, al menos esta longitud o cualquier longitud. Por ejemplo, escriba 11 y selectAt least en la lista desplegable para que coincida con números de al menos 11 dígitos de longitud.

   - **Dígitos para quitar**: (opcional) Especifique el número de dígitos iniciales que se quitarán. Por ejemplo, escriba 1 para quitar el + desde el principio del número.

   - **Dígitos para agregar**: (opcional) Especifique los dígitos que se deben anteponer a los números traducidos. Por ejemplo, escriba 011 si desea que 011 se anteponer a los números traducidos cuando se aplique la regla.

     Los valores especificados en estos campos se reflejan en los campos **Patrón para** coincidir y Regla **de** traducción. Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **campo Patrón para** coincidir es:

     ^\+(\d {9} \d+)$

     El **campo Regla** de traducción especifica un patrón para el formato de los números traducidos. Este patrón tiene dos partes:

   - Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón de coincidencia

   - (Opcional) Valor que puede anteponer entrando en el campo **Dígitos para agregar**

     Con los valores de ejemplo anteriores, 011$1 aparece en el **campo Regla de** traducción.

     Cuando se aplica esta regla de traducción, +441235551010 pasa a 011441235551010.

6. Haga clic en **Aceptar** para guardar la regla de conversión.

7. Haga clic en **Aceptar** para guardar la configuración de tronco.

8. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

   > [!NOTE]
   > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [vea Publicar cambios pendientes](voice-route-config-changes.md) en la configuración de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

### <a name="to-define-a-translation-rule-manually"></a>Para definir una regla de conversión de forma manual

1. Abrir Skype Empresarial Server panel de control

2. Para empezar a definir una regla de traducción, siga los pasos descritos en Configure [a trunk with media bypass in Skype Empresarial Server](configure-trunk-with-media-bypass.md) through step 10 o Configure a trunk without media bypass in [Skype Empresarial Server](configure-trunk-without-media-bypass.md) through step 9.

3. En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.

4. (Opcional) En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, marcación de larga distancia de US International.

5. Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.

6. Especifique lo siguiente en  **Escribir una expresión regular**:

   - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.

   - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

     Por ejemplo, si escribe ^ (\d \d+)$ en Coincidir con este patrón \+ {9} y011$1  en la regla de traducción, la regla traducirá +441235551010 a 011441235551010.

7. Haga clic en **Aceptar** para guardar la regla de conversión.

8. Haga clic en **Aceptar** para guardar la configuración de tronco.

9. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [vea Publicar cambios pendientes](voice-route-config-changes.md) en la configuración de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

## <a name="see-also"></a>Consulte también

[Configurar un tronco con desvío de medios en Skype Empresarial Server](configure-trunk-with-media-bypass.md)

[Configurar un tronco sin desvío de medios en Skype Empresarial Server](configure-trunk-without-media-bypass.md)

[Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial](voice-route-config-changes.md)

[Implementar la omisión de medios en Skype Empresarial Server](deploy-media-bypass.md)