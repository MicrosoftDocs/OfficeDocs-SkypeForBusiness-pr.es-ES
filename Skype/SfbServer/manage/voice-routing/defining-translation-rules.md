---
title: Definición de reglas de conversión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype empresarial Server Enterprise Voice enruta las llamadas en función de los números de teléfono normalizados al formato E. 164. Esto significa que todas las cadenas marcadas deben normalizarse al formato E. 164 para realizar búsquedas inversas de números (RNL), de modo que se puedan traducir al URI del SIP correspondiente. Skype empresarial Server proporciona la capacidad de manipular el identificador llamado y la presentación del identificador de llamada.
ms.openlocfilehash: 49598c2ef6b1a145c206bece3e06068067b0a0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151210"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definición de reglas de conversión en Skype empresarial Server

Skype empresarial Server Enterprise Voice enruta las llamadas en función de los números de teléfono normalizados al formato E. 164. Esto significa que todas las cadenas marcadas deben normalizarse al formato E. 164 para realizar búsquedas inversas de números (RNL), de modo que se puedan traducir al URI del SIP correspondiente. Skype empresarial Server proporciona la capacidad de manipular el identificador llamado y la presentación del identificador de llamada.

Con Skype empresarial Server, el número de teléfono de la persona que ha llamado (es decir, el número de teléfono llamado) se puede traducir del formato E. 164 al formato de marcado local necesario para el tronco del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el SIP tronco). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

## <a name="caller-id-presentation"></a>Presentación del identificador de llamada

Skype empresarial Server ofrece también la opción de traducir el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) desde el formato E. 164 al formato de marcado local necesario para el tronco del mismo nivel. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

**Para configurar el identificador de llamada mediante el panel de control de Skype empresarial Server**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial, consulte [instalar y abrir las herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
4. En la página Configuración de tronco, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.
5. Para configurar la presentación del identificador de llamada:
    - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**. 
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.
    - Para copiar una regla de conversión existente para usarla como punto de partida para definir una nueva regla, haga clic en el nombre de la regla, haga clic en **copiar**y, a continuación, haga clic en **pegar**.
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

> [!Warning] 
> No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

## <a name="called-id-presentation"></a>Presentación de identificador llamada

> [!Important]
> La capacidad de asociar una o más reglas de conversión con una configuración de tronco de Enterprise Voice sirve de *alternativa* para configurar reglas de conversión en la entidad del mismo nivel que el tronco. No asocie reglas de conversión a una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

Puede usar cualquiera de los métodos siguientes para crear o modificar una regla de conversión:

- [Use la herramienta generar una regla de conversión](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, deje que el panel de control de Skype empresarial Server genere el patrón de coincidencia y la regla de conversión correspondientes.
- [Escriba manualmente las expresiones regulares](#create-or-modify-a-translation-rule-manually) para definir el patrón de coincidencia y la regla de conversión.

> [!Note]
> Para obtener información sobre cómo escribir expresiones regulares, vea [expresiones regulares de .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Creación o modificación de una regla de conversión mediante la herramienta generar una regla de conversión

Siga estos pasos si desea definir una regla de conversión escribiendo un conjunto de valores en la herramienta generar una regla de conversión y habilitando el panel de control de Skype empresarial Server para generar el patrón de coincidencia y la regla de conversión correspondientes. 

**Para definir una regla mediante la herramienta generar una regla de conversión**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial, consulte [instalar y abrir las herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de conversión, siga los pasos que se indican en [configurar un tronco con desvío de medios](GET LINK AFTER MIGRATION)mediante el paso 10 o [configurar un tronco sin omisión de medios](GET LINK AFTER MIGRATION) mediante el paso 9.
4. En **nombre** en la página **nueva regla de conversión** o **Editar regla de conversión** , escriba un nombre que describa el patrón de número que se va a traducir.
5. Opcional En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International Long-Distance dialing**.
6. En la sección **crear una regla de conversión** del cuadro de diálogo, escriba los valores en los campos siguientes:
    - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números con los que desea que se ajuste la trama. Por ejemplo, escriba + en este campo para hacer coincidir números en formato E. 164 (que comienzan con +).
    - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con los números que tengan esta longitud, como mínimo, esta longitud o cualquier longitud. Por ejemplo, escriba **11** y seleccione **al menos** en la lista desplegable para hacer coincidir los números con una longitud de al menos 11 dígitos.
    - **Dígitos que se quitarán**: (opcional) especifique el número de dígitos iniciales que se quitarán. Por ejemplo, escriba **1** para descartar el + desde el principio del número.
    - **Dígitos que se agregarán**: (opcional) especifique los dígitos que se van a anteponer a los números convertidos. Por ejemplo, escriba **011** si desea anteponer 011 a los números convertidos cuando se aplica la regla.
    
    Los valores que escriba en estos campos se reflejarán en los campos **patrón para coincidir** y regla de **conversión** . Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **patrón para**el campo MATC h es:
    
    **^\+(\d{9}\d +) $** 

    El campo **regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón consta de dos partes:
    - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón de coincidencia.
    - Opcional Un valor que puede anteponer si lo especifica en el campo **dígitos que se agregarán**

    Con los valores del ejemplo anterior, se muestra **011 $1** en el campo **regla de conversión** .
    
    Cuando se aplica esta regla de conversión, + 441235551010 se convierte en 011441235551010.
7. Haga clic en **Aceptar** para guardar la regla de conversión.
8. Haga clic en **Aceptar** para guardar la configuración de tronco.
9. En la página configuratio n de **tronco**, haga clic en **confirmar**y, a continuación, en **confirmar todo**. 

> [!Note]
> Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener información detallada, consulte [Publish Pending changes to the Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Crear o modificar una regla de conversión de forma manual

Siga estos pasos si desea definir una regla de conversión escribiendo una expresión regular para el patrón de coincidencia y la regla de conversión. 

**Para definir una regla de conversión de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial, consulte [instalar y abrir las herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de conversión, siga los pasos que se indican en [configurar un tronco con desvío de medios](GET LINK AFTER MIGRATION)mediante el paso 10 o [configurar un tronco sin omisión de medios](GET LINK AFTER MIGRATION) mediante el paso 9.
4. En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.
5. Opcional En **Descripción**, escriba una descripción de la regla de conversión; por ejemplo, **US International dialing de larga distancia**.
6. Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.
7. Escriba lo siguiente en escribir una **expresión regular**:
    - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

    Por ejemplo, si escribe ** ^ \+(\d{9}\d +) $** en **coincidir con este patrón** y **011 $1** en **regla de conversión**, la regla se traducirá + 441235551010 a 011441235551010.
8. Haga clic en **Aceptar** para guardar la regla de conversión.
9. Haga clic en **Aceptar** para guardar la configuración de tronco.
10. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

> [!Note] 
> Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener información detallada, consulte [Publish Pending changes to the Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 
