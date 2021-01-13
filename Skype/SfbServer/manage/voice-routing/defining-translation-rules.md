---
title: Definición de reglas de conversión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype Empresarial Server Telefonía IP empresarial llamadas basadas en números de teléfono normalizados al formato E.164. Esto significa que todas las cadenas marcados deben normalizarse al formato E.164 con el fin de realizar búsquedas inversas de números (RNL) para que se puedan traducir a su URI de SIP correspondiente. Skype Empresarial Server proporciona la capacidad de manipular el identificador de llamada y la presentación del identificador de llamada.
ms.openlocfilehash: f4d0ab4fc30507fb5d247e072b3fdff8904f2ff3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823370"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definición de reglas de conversión en Skype Empresarial Server

Skype Empresarial Server Telefonía IP empresarial llamadas basadas en números de teléfono normalizados al formato E.164. Esto significa que todas las cadenas marcados deben normalizarse al formato E.164 con el fin de realizar búsquedas inversas de números (RNL) para que se puedan traducir a su URI de SIP correspondiente. Skype Empresarial Server proporciona la capacidad de manipular el identificador de llamada y la presentación del identificador de llamada.

Con Skype Empresarial Server, el número de teléfono de la parte a la que se llama (es decir, el número de teléfono al que se llama) se puede traducir del formato E.164 al formato de marcado local que requiere el tronco del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP. Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

## <a name="caller-id-presentation"></a>Presentación del identificador de llamada

Skype Empresarial Server ofrece la opción de traducir también el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) del formato E.164 al formato de marcado local que requiere el tronco del mismo nivel. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

**Para configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegar permisos de configuración.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, consulte Instalar y [abrir herramientas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
4. En la página Configuración de tronco, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.
5. Para configurar la presentación del identificador de llamada:
    - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**. 
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.
    - Para copiar una regla de conversión existente para usarla como punto de partida para definir una regla nueva, haga clic en el nombre de la regla, en Copiar y, a continuación, en **Pegar**.
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

> [!Warning] 
> No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

## <a name="called-id-presentation"></a>Presentación de identificador de llamada

> [!Important]
> La capacidad de asociar una o más reglas de conversión con una configuración de tronco de Enterprise Voice sirve de *alternativa* para configurar reglas de conversión en la entidad del mismo nivel que el tronco. No asocie reglas de conversión a una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

Puede usar cualquiera de los métodos siguientes para crear o modificar una regla de conversión:

- [Use](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) la herramienta Crear una regla de conversión para especificar los valores de los dígitos iniciales, la longitud, los dígitos que se quitarán y los dígitos que se agregarán y, a continuación, deje que el Panel de control de Skype Empresarial Server genere automáticamente el patrón de coincidencia y la regla de conversión correspondientes.
- [Escribir expresiones regulares manualmente para](#create-or-modify-a-translation-rule-manually) definir el patrón de coincidencia y la regla de conversión.

> [!Note]
> Para obtener información acerca de cómo escribir expresiones regulares, vea [expresiones regulares de .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Crear o modificar una regla de conversión mediante la herramienta Crear una regla de conversión

Siga estos pasos si desea definir una regla de conversión especificando un conjunto de valores en la herramienta Crear una regla de conversión y habilitando el Panel de control de Skype Empresarial Server para generar el patrón de coincidencia y la regla de conversión correspondientes. 

**Para definir una regla mediante la herramienta Crear una regla de conversión**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegar permisos de configuración.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, consulte Instalar y [abrir herramientas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Para empezar a definir una regla de conversión, siga los pasos [](GET LINK AFTER MIGRATION) descritos en [Configurar](GET LINK AFTER MIGRATION)un tronco con desvío de medios a través del paso 10 o Configurar un tronco sin desvío de medios en el paso 9.
4. En **Nombre** de la  página **Nueva regla de conversión** o Editar regla de conversión, escriba un nombre que describa el patrón de número que se va a traducir.
5. (Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, marcación de larga distancia **internacional de EE. UU.**
6. En la **sección Generar una regla de conversión** del cuadro de diálogo, escriba valores en los siguientes campos:
    - **Dígitos iniciales:**(opcional) Especifique los dígitos iniciales de los números que desea que coincidan con el patrón. Por ejemplo, escriba + en este campo para que coincida con los números en formato E.164 (que comienzan por +).
    - **Longitud:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números que sean exactamente de esta longitud, al menos esta longitud o cualquier longitud. Por ejemplo, escriba **11** y seleccione **Al** menos en la lista desplegable para que coincida con números de al menos 11 dígitos de longitud.
    - **Dígitos para quitar:**(opcional) Especifique el número de dígitos iniciales que se quitarán. Por ejemplo, escriba **1** para quitar el signo + del principio del número.
    - **Dígitos para agregar:**(opcional) Especifique los dígitos que se deben anteponer a los números traducidos. Por ejemplo, escriba **011** si desea que se antepone 011 a los números traducidos cuando se aplica la regla.
    
    Los valores especificados en estos campos se reflejan en los campos **Patrón** para coincidir y **Regla** de conversión. Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el campo **Pattern to matc** h es:
    
    **^\+(\d {9} \d+)$** 

    El **campo de regla** de conversión especifica un patrón para el formato de los números traducidos. Este patrón tiene dos partes:
    - Un valor (por ejemplo, **$1)** que representa el número de dígitos en el patrón de coincidencia
    - (Opcional) Un valor que puede anteponer si lo escribe en el campo **Dígitos para agregar**

    Con los valores de ejemplo anteriores, **aparece 011$1** en el **campo de regla de** conversión.
    
    Cuando se aplica esta regla de conversión, +441235551010 pasa a ser 011441235551010.
7. Haga clic en **Aceptar** para guardar la regla de conversión.
8. Haga clic en **Aceptar** para guardar la configuración de tronco.
9. En la página **Configuración de tronco** n, haga clic en **Confirmar** y, a continuación, en **Confirmar todo.** 

> [!Note]
> Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar cambios pendientes en la configuración de enrutamiento de voz.](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 

### <a name="create-or-modify-a-translation-rule-manually"></a>Crear o modificar una regla de conversión manualmente

Siga estos pasos si desea definir una regla de conversión escribiendo una expresión regular para el patrón de coincidencia y la regla de conversión. 

**Para definir una regla de conversión de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegar permisos de configuración.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, consulte Instalar y [abrir herramientas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Para empezar a definir una regla de conversión, siga los pasos [](GET LINK AFTER MIGRATION) descritos en [Configurar](GET LINK AFTER MIGRATION)un tronco con desvío de medios a través del paso 10 o Configurar un tronco sin desvío de medios en el paso 9.
4. En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.
5. (Opcional) En **Descripción,** escriba una descripción de la regla de conversión; por ejemplo, marcación de larga distancia internacional **de EE. UU.**
6. Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.
7. Escriba lo siguiente en Escribir una **expresión regular:**
    - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

    Por ejemplo, si escribe **^ \+ (\d {9} \d+)$** en Coincidir con este patrón y  **011$1** en la regla de conversión, la regla traducirá +441235551010 a 011441235551010. 
8. Haga clic en **Aceptar** para guardar la regla de conversión.
9. Haga clic en **Aceptar** para guardar la configuración de tronco.
10. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

> [!Note] 
> Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar cambios pendientes en la configuración de enrutamiento de voz.](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 
