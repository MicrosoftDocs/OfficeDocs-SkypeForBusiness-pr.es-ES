---
title: Definición de reglas de traducción en Skype empresarial Server
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
description: Skype empresarial Server Enterprise Voice enruta las llamadas basadas en números de teléfono normalizados al formato E. 164. Esto significa que todas las cadenas marcadas deben normalizarse al formato E. 164 con el fin de realizar la búsqueda de números invertidas (RNL) para que puedan traducirse al URI SIP correspondiente. Skype empresarial Server proporciona la capacidad de manipular el identificador llamado y la presentación de identificación de llamadas.
ms.openlocfilehash: cdcfe3a847e148461b97abed33df070057dcd00b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816990"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definición de reglas de traducción en Skype empresarial Server

Skype empresarial Server Enterprise Voice enruta las llamadas basadas en números de teléfono normalizados al formato E. 164. Esto significa que todas las cadenas marcadas deben normalizarse al formato E. 164 con el fin de realizar la búsqueda de números invertidas (RNL) para que puedan traducirse al URI SIP correspondiente. Skype empresarial Server proporciona la capacidad de manipular el identificador llamado y la presentación de identificación de llamadas.

Con Skype empresarial Server, el número de teléfono de la persona que se llama (es decir, el número de teléfono llamado) se puede traducir desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el SIP troncal). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

## <a name="caller-id-presentation"></a>Presentación de identificación de llamadas

Skype empresarial Server también ofrece la opción de traducir el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

**Para configurar la identificación de llamadas con el panel de control de Skype empresarial Server**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración del delegado](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype para empresas, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.
4. En la página Configuración de tronco, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.
5. Para configurar la presentación del identificador de llamada:
    - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. 
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.
    - Para copiar una regla de traducción existente para usarla como punto de partida para definir una nueva regla, haga clic en el nombre de la regla, en **copiar**y, a continuación, en **pegar**.
    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

> [!Warning] 
> No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto. 

## <a name="called-id-presentation"></a>Llamada de presentación de identificador

> [!Important]
> La capacidad de asociar una o más reglas de traducción con una configuración de telefonía IP empresarial está pensada para su uso como *alternativa* a la configuración de reglas de traducción en el punto de conexión del mismo nivel. No asociar reglas de traducción con una configuración de telefonía IP empresarial si ha configurado reglas de traducción en el punto de conexión del mismo nivel porque las dos reglas podrían entrar en conflicto. 

Puede usar cualquiera de los siguientes métodos para crear o modificar una regla de traducción:

- [Use la herramienta generar una regla de traducción](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) para especificar valores para los dígitos de inicio, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, deje que el panel de control de Skype empresarial Server genere la regla de traducción y el patrón correspondiente.
- [Escriba de forma manual expresiones regulares](#create-or-modify-a-translation-rule-manually) para definir el patrón de coincidencia y la regla de traducción.

> [!Note]
> Para obtener información sobre cómo escribir expresiones regulares, vea [expresiones regulares de .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Crear o modificar una regla de traducción con la herramienta generar una regla de traducción

Siga estos pasos si desea definir una regla de traducción escribiendo un conjunto de valores en la herramienta generar una regla de traducción y habilitar el panel de control de Skype empresarial Server para generar la regla de traducción y el patrón de coincidencia correspondiente. 

**Para definir una regla mediante el uso de la herramienta Crear una regla de conversión**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración del delegado](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype para empresas, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con medios para omitir](GET LINK AFTER MIGRATION)el paso 10 o [configurar un tronco sin medios omitir](GET LINK AFTER MIGRATION) a través del paso 9.
4. En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.
5. Faculta En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, **llamadas internacionales de larga distancia de Estados Unidos**.
6. En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:
    - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón. Por ejemplo, escriba + en este campo para que se cree una correspondencia con números en formato E.164 (que comienzan con +).
    - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba **11** y seleccione **At least** en la lista desplegable para que haya coincidencias con números de al menos 11 dígitos de longitud.
    - **Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar. Por ejemplo, escriba **1** para quitar el + del comienzo del número.
    - **Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba **011** si desea que se agregue 011 a los números convertidos cuando se aplique la regla.
    
    Los valores que escriba en estos campos se reflejarán en los campos **trama para coincidir** y regla de **traducción** . Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **patrón para**el campo MATC h es:
    
    **^\+(\d{9}\d +) $** 

    El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:
    - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón con el que hacer coincidir.
    - (Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.

    Al usar los valores del ejemplo anterior, aparecerá **011$1** en el campo **Regla de conversión**.
    
    Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.
7. Haga clic en **Aceptar** para guardar la regla de conversión.
8. Haga clic en **Aceptar** para guardar la configuración de tronco.
9. En la página **troncal configuratio**n, haga clic en **confirmar**y, a continuación, haga clic en **confirmar todo**. 

> [!Note]
> Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración del enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Crear o modificar una regla de traducción de forma manual

Siga estos pasos si desea definir una regla de traducción escribiendo una expresión regular para el patrón y la regla de traducción coincidentes. 

**Para definir una regla de conversión de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración del delegado](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype para empresas, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con medios para omitir](GET LINK AFTER MIGRATION)el paso 10 o [configurar un tronco sin medios omitir](GET LINK AFTER MIGRATION) a través del paso 9.
4. En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.
5. Faculta En **Descripción**, escriba una descripción de la regla de traducción. por ejemplo, **EE. UU. Internacional de llamadas de larga distancia**.
6. Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.
7. Escriba lo siguiente en escriba una **expresión regular**:
    - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

    Por ejemplo, si escribe ** ^ \+{9}(\d \d +) $** **coincide con este patrón** y **011 $1** en la **regla de traducción**, la regla traducirá + 441235551010 a 011441235551010.
8. Haga clic en **Aceptar** para guardar la regla de conversión.
9. Haga clic en **Aceptar** para guardar la configuración de tronco.
10. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

> [!Note] 
> Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración del enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 
