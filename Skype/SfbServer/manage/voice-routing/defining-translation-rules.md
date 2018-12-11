---
title: Definición de reglas de conversión en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Enterprise Voice Business Server enruta las llamadas en función de los números de teléfono normalizados al formato E.164. Esto significa que se deben normalizar todas las cadenas de marcado al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL) por lo que se pueden traducir a sus URI de SIP coincidente. Skype para Business Server proporciona la capacidad de manipular el identificador de llamada y la presentación del identificador de autor de la llamada.
ms.openlocfilehash: e3feda41a3057ea6f0ae6d7946f3e21e75ba7f81
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223006"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definición de reglas de conversión en Skype para Business Server

Skype para Enterprise Voice Business Server enruta las llamadas en función de los números de teléfono normalizados al formato E.164. Esto significa que se deben normalizar todas las cadenas de marcado al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL) por lo que se pueden traducir a sus URI de SIP coincidente. Skype para Business Server proporciona la capacidad de manipular el identificador de llamada y la presentación del identificador de autor de la llamada.

Con Skype para Business Server, número de teléfono del receptor (es decir, el número de teléfono denominado) se puede traducir del formato E.164 para el formato de marcado local que se requiere el elemento del mismo nivel de tronco (es decir, la puerta de enlace asociada, central de conmutación (PBX) o SIP tronco). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

## <a name="caller-id-presentation"></a>Presentación del identificador de autor de la llamada

Skype para Business Server ofrece la opción de traducir también el número de teléfono de la persona que llama (es decir, el número de teléfono que el autor de la llamada está llamando desde) del formato E.164 para el formato de marcado local que se requiere el elemento del mismo nivel de tronco. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

**Para configurar el identificador de autor de la llamada mediante la Skype para el Panel de Control de servidor empresarial**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener información detallada, vea [delegar permisos de instalación](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
4. En la página Configuración de tronco, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.
5. Para configurar la presentación del identificador de llamada:
    - Para elegir una o varias reglas de una lista de todas las reglas de conversión disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. 
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.
    - Para copiar una regla de conversión existente para usar como punto de partida para definir una nueva regla, haga clic en el nombre de la regla, haga clic en **Copiar**y, a continuación, haga clic en **Pegar**.
    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Quitar**.

> [!Warning] 
> No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto. 

## <a name="called-id-presentation"></a>Presentación del identificador llamado

> [!Important]
> La capacidad para asociar una o varias reglas de traducción con una configuración de tronco de Enterprise Voice está destinada a ser utilizado como una *alternativa* a la configuración de reglas de conversión en el mismo nivel de tronco. No asocie reglas de conversión con una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en el mismo nivel de tronco debido a que las dos reglas entran en conflicto. 

Puede usar cualquiera de los métodos siguientes para crear o modificar una regla de conversión:

- [Use la compilación de una herramienta de la regla de conversión](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) para especificar valores de partida dígitos, longitud, dígitos para quitar y dígitos para agregar y, a continuación, permitir que el Skype para el Panel de Control de servidor empresarial generar la regla de traducción y el patrón de coincidencia correspondiente para.
- [Escribir manualmente las expresiones regulares](#create-or-modify-a-translation-rule-manually) para definir la regla de coincidencia de patrón y traducción.

> [!Note]
> Para obtener información sobre cómo escribir expresiones regulares, vea [Expresiones regulares de .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Crear o modificar una regla de conversión mediante una herramienta de regla de conversión de la compilación

Siga estos pasos si desea definir una regla de conversión especificando un conjunto de valores en la compilación de una herramienta de la regla de conversión y habilitar la Skype para Panel de Control de servidor empresarial generar el patrón coincidente correspondiente y la regla de conversión para usted. 

**Para definir una regla mediante el uso de la herramienta Crear una regla de conversión**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener información detallada, vea [delegar permisos de instalación](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de conversión, siga los pasos de [desvío de configurar un tronco con medios](GET LINK AFTER MIGRATION)a través de paso 10 o [Configure un tronco sin medios desvío](GET LINK AFTER MIGRATION) hasta el paso 9.
4. En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.
5. (Opcional) En **Descripción**, escriba una descripción de la regla de conversión - por ejemplo, **de marcado a larga distancia internacional de Estados Unidos**.
6. En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:
    - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón. Por ejemplo, escriba + en este campo para que se cree una correspondencia con números en formato E.164 (que comienzan con +).
    - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba **11** y seleccione **At least** en la lista desplegable para que haya coincidencias con números de al menos 11 dígitos de longitud.
    - **Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar. Por ejemplo, escriba **1** para quitar el + del comienzo del número.
    - **Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba **011** si desea que se agregue 011 a los números convertidos cuando se aplique la regla.
    
    Los valores que especifique en estos campos se reflejan en los campos de regla **coincida patrón** y **traducción** . Por ejemplo, si especifica los valores del ejemplo anterior, la expresión regular resultante en el campo h de **trama a CO**es:
    
    **^\+(\d{9}\d+)$** 

    El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:
    - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón con el que hacer coincidir.
    - (Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.

    Al usar los valores del ejemplo anterior, aparecerá **011$1** en el campo **Regla de conversión**.
    
    Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.
7. Haga clic en **Aceptar** para guardar la regla de conversión.
8. Haga clic en **Aceptar** para guardar la configuración de tronco.
9. En la página **Configuración de tronco**n, haga clic en **Confirmar**y, a continuación, haga clic en **Confirmar todo**. 

> [!Note]
> Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Crear o modificar una regla de conversión manualmente

Siga estos pasos si desea definir una regla de conversión mediante la escritura de una expresión regular para el patrón coincidente y una regla de conversión. 

**Para definir una regla de conversión de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener información detallada, vea [delegar permisos de instalación](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de conversión, siga los pasos de [desvío de configurar un tronco con medios](GET LINK AFTER MIGRATION)a través de paso 10 o [Configure un tronco sin medios desvío](GET LINK AFTER MIGRATION) hasta el paso 9.
4. En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.
5. (Opcional) En **Descripción**, escriba una descripción de la regla de conversión; Por ejemplo, **de marcado a larga distancia internacional de Estados Unidos**.
6. Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.
7. Escriba lo siguiente en el tipo de una **Expresión Regular**:
    - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

    Por ejemplo, si escribe ** ^ \+(\d{9}\d+)$** en **este patrón de coincidencia** y **011$ 1** en la **regla de conversión**, la regla convertirá + 441235551010 a 011441235551010.
8. Haga clic en **Aceptar** para guardar la regla de conversión.
9. Haga clic en **Aceptar** para guardar la configuración de tronco.
10. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

> [!Note] 
> Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 