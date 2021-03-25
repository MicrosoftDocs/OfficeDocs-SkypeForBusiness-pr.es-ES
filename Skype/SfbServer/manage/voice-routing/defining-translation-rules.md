---
title: Definición de reglas de traducción en Skype Empresarial Server
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
description: Skype Empresarial Server Telefonía IP empresarial llamadas basadas en números de teléfono normalizados al formato E.164. Esto significa que todas las cadenas marcados deben normalizarse al formato E.164 con el fin de realizar búsquedas de números inversos (RNL) para que se puedan traducir a su URI sip correspondiente. Skype Empresarial Server proporciona la capacidad de manipular el identificador llamado y la presentación del identificador de autor de la llamada.
ms.openlocfilehash: f3a37a48ec2e4497d644e2051a6e6d37ccef9707
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120912"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definición de reglas de traducción en Skype Empresarial Server

Skype Empresarial Server Telefonía IP empresarial llamadas basadas en números de teléfono normalizados al formato E.164. Esto significa que todas las cadenas marcados deben normalizarse al formato E.164 con el fin de realizar búsquedas de números inversos (RNL) para que se puedan traducir a su URI sip correspondiente. Skype Empresarial Server proporciona la capacidad de manipular el identificador llamado y la presentación del identificador de autor de la llamada.

Con Skype Empresarial Server, el número de teléfono de la parte llamada (es decir, el número de teléfono llamado) se puede traducir del formato E.164 al formato de marcado local que requiere el tronco del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación de sucursal privada (PBX) o el tronco SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

## <a name="caller-id-presentation"></a>Presentación del identificador de autor de la llamada

Skype Empresarial Server ofrece la opción de traducir también el número de teléfono de la persona que realiza la llamada (es decir, el número de teléfono desde el que llama el autor de la llamada) del formato E.164 al formato de marcado local que requiere el mismo nivel de tronco. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

**Para configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
4. En la página Configuración de tronco, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.
5. Para configurar la presentación del identificador de llamada:
    - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**. 
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.
    - Para copiar una regla de conversión existente que se usará como punto de partida para definir una nueva regla, haga clic en el nombre de la regla, haga clic en Copiar **y,** a continuación, en **Pegar**.
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

> [!Warning] 
> No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

## <a name="called-id-presentation"></a>Presentación de id. llamada

> [!Important]
> La capacidad de asociar una o más reglas de conversión con una configuración de tronco de Enterprise Voice sirve de *alternativa* para configurar reglas de conversión en la entidad del mismo nivel que el tronco. No asocie reglas de conversión a una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

Puede usar cualquiera de los métodos siguientes para crear o modificar una regla de conversión:

- [Use](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) la herramienta Crear una regla de traducción para especificar los valores de los dígitos iniciales, la longitud, los dígitos que se quitarán y los dígitos que se agregarán y, a continuación, deje que el Panel de control de Skype Empresarial Server genere el patrón de coincidencia y la regla de traducción correspondientes.
- [Escriba expresiones regulares manualmente](#create-or-modify-a-translation-rule-manually) para definir el patrón de coincidencia y la regla de traducción.

> [!Note]
> Para obtener información sobre cómo escribir expresiones regulares, [vea .NET Framework Regular Expressions](/dotnet/standard/base-types/regular-expressions). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Crear o modificar una regla de traducción mediante la herramienta Crear una regla de traducción

Siga estos pasos si desea definir una regla de traducción especificando un conjunto de valores en la herramienta Crear una regla de traducción y habilitando el Panel de control de Skype Empresarial Server para generar el patrón y la regla de traducción correspondientes. 

**Para definir una regla mediante la herramienta Crear una regla de traducción**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de traducción, siga los pasos descritos en [Configure a trunk with media bypass](GET LINK AFTER MIGRATION)through step 10 o Configure a trunk without media [bypass](GET LINK AFTER MIGRATION) through step 9.
4. En **Nombre** de la  página **Nueva regla de traducción** o Editar regla de traducción, escriba un nombre que describa el patrón de números que se va a traducir.
5. (Opcional) En **Descripción**, escriba una descripción de la regla de traducción, por ejemplo, marcación de larga distancia **internacional de EE. UU.**
6. En la **sección Crear una regla de traducción** del cuadro de diálogo, escriba valores en los siguientes campos:
    - **Dígitos iniciales**: (opcional) Especifique los dígitos iniciales de los números que desea que coincidan con el patrón. Por ejemplo, escriba + en este campo para que coincida con los números en formato E.164 (que comienzan por +).
    - **Length:** especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números que son exactamente de esta longitud, al menos esta longitud o cualquier longitud. Por ejemplo, escriba **11** y seleccione **Al** menos en la lista desplegable para que coincida con números de al menos 11 dígitos de longitud.
    - **Dígitos para quitar**: (opcional) Especifique el número de dígitos iniciales que se quitarán. Por ejemplo, escriba **1** para quitar el + desde el principio del número.
    - **Dígitos para agregar**: (opcional) Especifique los dígitos que se deben anteponer a los números traducidos. Por ejemplo, escriba **011** si desea que 011 se anteponer a los números traducidos cuando se aplique la regla.
    
    Los valores especificados en estos campos se reflejan en los campos **Patrón para** coincidir y **Regla** de traducción. Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante en el **campo Pattern to matc** h es:
    
    **^\+(\d {9} \d+)$** 

    El **campo Regla** de traducción especifica un patrón para el formato de los números traducidos. Este patrón tiene dos partes:
    - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón de coincidencia
    - (Opcional) Valor que puede anteponer entrando en el campo **Dígitos para agregar**

    Con los valores de ejemplo anteriores, **011$1** aparece en el **campo Regla de** traducción.
    
    Cuando se aplica esta regla de traducción, +441235551010 pasa a ser 01144123551010.
7. Haga clic en **Aceptar** para guardar la regla de conversión.
8. Haga clic en **Aceptar** para guardar la configuración de tronco.
9. En la **página Configuración de tronco** n, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**. 

> [!Note]
> Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [vea Publicar cambios pendientes en la configuración de enrutamiento de voz.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration) 

### <a name="create-or-modify-a-translation-rule-manually"></a>Crear o modificar una regla de traducción manualmente

Siga estos pasos si desea definir una regla de conversión escribiendo una expresión regular para el patrón de coincidencia y la regla de conversión. 

**Para definir una regla de conversión de forma manual**

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. Para empezar a definir una regla de traducción, siga los pasos descritos en [Configure a trunk with media bypass](GET LINK AFTER MIGRATION)through step 10 o Configure a trunk without media [bypass](GET LINK AFTER MIGRATION) through step 9.
4. En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.
5. (Opcional) En **Descripción**, escriba una descripción de la regla de traducción; por ejemplo, marcado de larga distancia **de EE. UU. Internacional**.
6. Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.
7. Escriba lo siguiente en Type a **Regular Expression**:
    - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.

    Por ejemplo, si escribe **^ \+ (\d {9} \d+)$** en Coincidir con este patrón y  **011$1** en la regla de traducción, la regla traducirá +441235551010 a 01144123551010. 
8. Haga clic en **Aceptar** para guardar la regla de conversión.
9. Haga clic en **Aceptar** para guardar la configuración de tronco.
10. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

> [!Note] 
> Siempre que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [vea Publicar cambios pendientes en la configuración de enrutamiento de voz.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration)