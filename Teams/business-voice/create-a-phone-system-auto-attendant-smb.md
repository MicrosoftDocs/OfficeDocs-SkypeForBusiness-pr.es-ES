---
title: 'Configurar un operador automático para Microsoft Teams: tutorial para pequeñas empresas'
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Aprenda a configurar y probar operadores automáticos para Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909664"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurar un operador automático: tutorial para pequeñas empresas

Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento, la cola de llamadas, la persona o un operador adecuados. Puede crear operadores automáticos para su organización con el Centro de administración de Microsoft Teams.

#### <a name="before-you-begin"></a>Antes de comenzar

Obtenga los números de servicio que necesita para los operadores automáticos a los que desea obtener acceso mediante marcado directo desde fuera de su organización. Esto puede incluir [la transferencia de números de otro proveedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](../getting-service-phone-numbers.md)

Obtener un [sistema telefónico: licencia de usuario virtual](../teams-add-on-licensing/virtual-user.md) para cada operador automático que planea crear. Estas licencias son gratuitas, por lo que le recomendamos que le ofrecemos unas cuantas adicionales en caso de que decida realizar cambios en su configuración en el futuro.

Si quiere que el operador automático enruta [](../set-up-holidays-in-teams.md) las llamadas de forma diferente los días festivos, cree los días festivos que desee usar antes de crear el operador automático.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estos pasos para configurar el operador automático

# <a name="step-1brphone-number"></a>[Paso 1 <br> Número de teléfono](#tab/phone-number)

Cada operador automático que cree requiere una cuenta de recurso. Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada a un operador automático o a una cola de llamadas en lugar de a una persona. En este paso, crearemos la cuenta, le asignaremos una licencia de Sistema telefónico de *Microsoft 365:* licencia de usuario virtual y, a continuación, asignaremos un número de servicio.

### <a name="create-a-resource-account"></a>Crear una cuenta de recurso

Puede crear una cuenta de recurso en el Centro de administración de Teams.

1. En el Centro de administración de Teams, expanda **la configuración de toda la** organización y, a continuación, haga clic en Cuentas de **recursos.**

2. Haga clic en **Agregar**.

3. En el **panel Agregar cuenta de** recurso, rellene **Nombre** para **mostrar,** Nombre de usuario y elija **Operador automático** para el tipo de **cuenta Recurso**

    ![Captura de pantalla de la interfaz de usuario para agregar una cuenta de recurso](../media/resource-account-add.png)

4. Haga clic en **Guardar**.

La nueva cuenta aparecerá en la lista de cuentas.

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Asignar una licencia

Debe asignar una licencia *de Microsoft 365 Phone System - Virtual User* a la cuenta de recursos.

1. En el Centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.

2. En la **pestaña Licencias y aplicaciones,** en **Licencias,** seleccione Sistema telefónico de **Microsoft 365 - Usuario virtual.**

3. Haga clic **en Guardar cambios.**

    ![Captura de pantalla de la interfaz de usuario de asignación de licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Asignar un número de servicio

Si necesita que un número de teléfono le haga llegar a este operador automático, asígnelo a la cuenta del recurso.

1. En el Centro de  administración de Teams, en la página Cuentas de recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en Asignar **o desasignir.**

2. En la **lista desplegable Tipo de** número de teléfono, elija el tipo de número que desea usar.

3. En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**

    ![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

4. Haga clic en **Guardar**.

> [!div class="nextstepaction"]
> [Paso 2: Información general del operador automático >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Información general del operador del paso 2 <br>](#tab/general-info)

Para configurar un operador automático

1. En el Centro de administración de Teams, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic **en Agregar.**

2. Escriba un nombre para el operador automático en el cuadro de la parte superior.

3. Si desea designar un operador, especifique el destino de las llamadas al operador. Esto es opcional (pero recomendado). Puede establecer la opción **Operador para** permitir que los autores de llamadas salgan de los menús y hablen con la persona designada.

4. Especifique la zona horaria de este operador automático. La zona horaria se usa para calcular el horario laboral si crea otro flujo de llamadas para horas fuera del horario laboral.

5. Especifique un idioma para este operador automático. Este es el idioma que se usará para los mensajes de voz generados por el sistema.

6. Elija si desea habilitar las entradas de voz. Cuando está habilitada, el nombre de todas las opciones de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, las personas que llaman pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".

    ![Captura de pantalla de la configuración del operador automático para entradas de nombre, operador, zona horaria, idioma y voz](../media/auto-attendant-general-info-page-new.png)

7. Haga clic en **Siguiente**.

> [!div class="nextstepaction"]
> [Paso 3: Flujo de llamadas >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Paso <br> 3: Flujo de llamadas](#tab/call-flow)

Elegir las opciones de flujo de llamadas

1. Elija si desea reproducir un saludo cuando el operador automático responda una llamada.

    Si selecciona Reproducir un archivo de  **audio,** puede usar el botón Cargar archivo para cargar un mensaje de saludo grabado guardado como audio en. WAV, . MP3 o . Formato WMA. La grabación no puede ser superior a 5 MB.

    Si selecciona **Escribir** un mensaje de saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda una llamada.

    ![Captura de pantalla de la configuración del mensaje de saludo](../media/auto-attendant-call-flow-greeting-message.png)

2. Elige cómo quieres enrutar la llamada.

    Si selecciona **Desconectar,** el operador automático colgará la llamada.

    Si selecciona Redirigir **llamada, puede** elegir uno de los destinos de enrutamiento de llamadas.

    Si selecciona las **opciones del** menú Reproducir, puede elegir reproducir un archivo de **audio** o escribir un mensaje de saludo y, **después,** elegir entre las opciones de menú y la búsqueda en directorios.

    ![Captura de pantalla de la configuración de enrutamiento de llamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. Si quiere que los autores de las llamadas usen las teclas de marcado para navegar, en Establecer las opciones del **menú,** elija lo que quiere que suceda cuando las personas que llaman presionen una tecla de marcado. (Si va a crear este operador automático como directorio de la empresa, deje en blanco las opciones de la tecla de marcado).

    Puede establecer cualquiera de las teclas de marcado en los siguientes destinos:

    - **Persona de la organización:** una persona de la organización que puede recibir llamadas de voz.
    - **Aplicación de voz:** otro operador automático o una cola de llamadas.
    - **Número de teléfono externo:** cualquier número de teléfono. Use este formato: +[código de país][código de área][número de teléfono]
    - **Correo** de voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.
    - **Operador** ( operador definido para el operador automático). La definición de un operador es opcional. El operador se puede definir como cualquiera de los otros destinos de esta lista.

    Se recomienda establecer la tecla 0 para el operador.

    Para cada opción de menú, especifique lo siguiente:

    - **Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.

    - **Comando de** voz: define el comando de voz que puede dar un autor de llamada para obtener acceso a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras como "Atención al cliente" u "Operaciones y campos". 

    - **Redirigir a:** dónde quiere que vaya la llamada cuando las personas que llaman elijan esta opción. Si redirige a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada con él.

    ![Captura de pantalla de las opciones de tecla de marcado](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Si desea usar este operador automático como directorio de la empresa, en Búsqueda **del** directorio, seleccione **Marcado por nombre.** Al habilitar esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono. Cualquier usuario en línea con una licencia de Sistema telefónico es un usuario apto y se puede encontrar con Marcado por nombre. 

    (Puede elegir **Marcar por extensión,** pero la extensión debe configurarse en Azure Active Directory).

5. Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 4: flujo de llamadas no laboral >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Paso <br> 4: No laboral](#tab/after-hours)

El horario laboral se puede establecer para cada operador automático. Si no se establecen los horarios laborales, todos los días y todas las horas del día se considerarán laborables, ya que se establece una programación las 24 horas. El horario laboral se puede establecer con saltos en el tiempo durante el día y todas las horas que no se establecen como horas de trabajo se tienen en cuenta fuera del horario laboral. Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para después del horario laboral.

Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas no laborales para los operadores automáticos con números de teléfono directos.

Si desea enrutamiento de llamada independiente para los autores de llamadas fuera del horario laboral, especifique su horario laboral para cada día. Haga **clic en Agregar nueva** hora para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una hora de almuerzo.

![Captura de pantalla de la configuración de días y horas fuera del horario laboral](../media/auto-attendant-business-hours.png)

Una vez que haya especificado su horario laboral, elija las opciones de enrutamiento de llamada para horas adicionales. Están disponibles las mismas opciones que para el enrutamiento de llamadas en horario laboral que ha especificado en el **paso 3 - Flujo de llamadas.**

Haga **clic en** Siguiente cuando haya terminado.

> [!div class="nextstepaction"]
> [Paso 5: Flujo de llamadas navideña >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Paso 5, días <br> festivos](#tab/holidays)

Puede hacer que las llamadas al operador automático se desrutar de manera diferente en días festivos que en otros días. (Si no quiere tener un flujo de llamadas diferente para los días festivos, puede omitir este paso).



El operador automático puede tener un flujo de llamadas para cada día festivo que haya configurado. Puede agregar un máximo de 20 días festivos programados a cada operador automático.

1. En la página configuración de la llamada navideña, haga clic **en Agregar.**

2. Escriba un nombre para esta configuración navideña.

3. En el **menú** desplegable Vacaciones, elija las vacaciones que desea usar.

4. Elija el tipo de saludo que quiere usar.

    ![Captura de pantalla de la configuración de saludos navideñas y navideñas](../media/auto-attendant-holiday-greeting.png)

5. Elija si desea desconectar **o** **redirigir** la llamada.

6. Si decide redirigir, elija el destino de enrutamiento de llamada para la llamada.

    ![Captura de pantalla de la configuración de la acción de llamada navideña](../media/auto-attendant-holiday-actions.png)

7. Haga clic en **Guardar**.

Repita el procedimiento según sea necesario para cada día festivo adicional.

![Captura de pantalla de la configuración de días festivos con la lista de días festivos](../media/auto-attendant-holiday-call-settings.png)

Cuando haya agregado todos los días festivos, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 6: elegir quién está en el directorio >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Paso 6: <br> Miembros del directorio](#tab/dial-scope)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de llamada usa marcado por nombre o marcado por extensión. El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una licencia de Sistema telefónico.

Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad.  Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcación. (Si un usuario está en ambas listas, se excluirá del directorio).

![Captura de pantalla del ámbito de marcado con opciones de incluir y excluir](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Los nombres de los nuevos usuarios pueden tardar hasta 36 horas en aparecer en el directorio.

Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 7: Asignar una cuenta de recurso >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Paso 7: <br> Cuentas de recursos](#tab/resource-accounts)

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recurso que tenga un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.

Para agregar una cuenta de recurso

1. Haga **clic en Agregar** cuenta y busque la cuenta que desea agregar. Haga **clic en Agregar** y, a continuación, en **Agregar.**

    ![Captura de pantalla del panel Agregar cuentas de la cuenta de recursos](../media/auto-attendant-add-resource-account.png)

2. Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**

    ![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recurso con el número de servicio asignado](../media/auto-attendant-resource-account-assigned.png)

Esto completa la configuración del operador automático.

---


