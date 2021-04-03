---
title: 'Configurar un operador automático para Microsoft Teams: tutorial de pequeña empresa'
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
description: Obtenga información sobre cómo configurar y probar operadores automáticos para Microsoft 365 Business Voice.
ms.openlocfilehash: 7ee7dad833119778ceb64bd1e52bd30da4529ba8
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506657"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurar un operador automático : tutorial de pequeña empresa

Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento adecuado, la cola de llamadas, una persona o un operador. Puede crear operadores automáticos para su organización con el Centro de administración de Microsoft Teams.

#### <a name="before-you-begin"></a>Antes de empezar

Obtenga los números de servicio que necesita para los operadores automáticos a los que desea obtener acceso mediante el marcado directo desde fuera de su organización. Esto puede incluir [la transferencia de números de otro proveedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](../getting-service-phone-numbers.md)

Obtener un [sistema telefónico: licencia de usuario virtual](../teams-add-on-licensing/virtual-user.md) para cada operador automático que tiene previsto crear. Estas licencias son gratuitas, por lo que le recomendamos obtener algunas adicionales en caso de que decida realizar cambios en su configuración en el futuro.

Si desea que la ruta de operador automático [](../set-up-holidays-in-teams.md) llame de forma diferente los días festivos, cree los días festivos que quiera usar antes de crear el operador automático.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estos pasos para configurar el operador automático

# <a name="step-1brphone-number"></a>[Paso 1 <br> Número de teléfono](#tab/phone-number)

Cada operador automático que cree requiere una cuenta de recursos. Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada con un operador automático o una cola de llamadas en lugar de una persona. En este paso, crearemos la cuenta, le asignaremos una licencia de *Microsoft 365 Phone System - Virtual User* y, a continuación, asignaremos un número de servicio.

### <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Puede crear una cuenta de recursos en el Centro de administración de Teams.

1. En el Centro de administración de Teams, expanda **Configuración de toda la organización** y, a continuación, haga clic en Cuentas de **recursos.**

2. Haga clic en **Agregar**.

3. En el **panel Agregar cuenta de** recursos, rellene **Nombre** para mostrar, Nombre de **usuario** y elija **Operador automático** para el tipo de **cuenta Recurso**

    ![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

4. Haga clic en **Guardar**.

La nueva cuenta aparecerá en la lista de cuentas.

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Asignar una licencia

Debe asignar una licencia de Usuario virtual de *Microsoft 365 Phone System* a la cuenta de recursos.

1. En el Centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.

2. En la **pestaña Licencias y aplicaciones,** en **Licencias,** seleccione **Microsoft 365 Phone System - Usuario virtual.**

3. Haga clic **en Guardar cambios.**

    ![Captura de pantalla de la interfaz de usuario asignar licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Asignar un número de servicio

Si necesita que este operador automático sea accesible mediante un número de teléfono, asigne ese número a la cuenta de recursos.

1. En el Centro de  administración de Teams, en la página Cuentas de recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en Asignar **o desasignación.**

2. En la **lista desplegable Tipo de número de** teléfono, elija el tipo de número que desea usar.

3. En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**

    ![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

4. Haga clic en **Guardar**.

> [!div class="nextstepaction"]
> [Paso 2: Información general del operador automático >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Paso 2 <br> Información general del operador](#tab/general-info)

Para configurar un operador automático

1. En el Centro de administración de Teams, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic **en Agregar.**

2. Escriba un nombre para el operador automático en el cuadro de la parte superior.

3. Si desea designar un operador, especifique el destino de las llamadas al operador. Esto es opcional (pero recomendado). Puede establecer la opción **Operador** para permitir a los autores de llamadas salir de los menús y hablar con una persona designada.

4. Especifique la zona horaria para este operador automático. La zona horaria se usa para calcular el horario laboral si crea un flujo de llamadas independiente para horas posteriores.

5. Especifique un idioma para este operador automático. Este es el idioma que se usará para las solicitudes de voz generadas por el sistema.

6. Elija si desea habilitar las entradas de voz. Cuando se habilita, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".

    ![Captura de pantalla de la configuración del operador automático para el nombre, el operador, la zona horaria, el idioma y las entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. Haga clic en **Siguiente**.

> [!div class="nextstepaction"]
> [Paso 3: flujo de llamadas >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Paso 3 <br> Flujo de llamadas](#tab/call-flow)

Elegir las opciones de flujo de llamadas

1. Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.

    Si selecciona Reproducir un archivo de  **audio,** puede usar el botón Cargar archivo para cargar un mensaje de saludo grabado guardado como audio en . WAV, . MP3 o . Formato WMA. La grabación no puede ser superior a 5 MB.

    Si selecciona Escribir un mensaje **de** saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.

    ![Captura de pantalla de la configuración del mensaje de saludo](../media/auto-attendant-call-flow-greeting-message.png)

2. Elija cómo desea enrutar la llamada.

    Si selecciona **Desconectar,** el operador automático colgará la llamada.

    Si selecciona **Redirigir llamada,** puede elegir uno de los destinos de enrutamiento de llamadas.

    Si selecciona Opciones **de menú** Reproducir, puede elegir Reproducir un archivo de **audio** o Escribir en un mensaje de saludo y, **a** continuación, elegir entre las opciones de menú y la búsqueda de directorio.

    ![Captura de pantalla de la configuración de enrutamiento de llamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. Si desea que los autores de llamadas usen teclas de marcado para navegar, en Establecer opciones de **menú,** elija lo que quiere que suceda cuando los autores de llamadas presionen una tecla de marcado. (Si va a crear este operador automático como directorio de la empresa, deje las opciones de la tecla de marcado en blanco).

    Puede establecer cualquiera de las teclas de marcado en los siguientes destinos:

    - **Persona de la organización:** una persona de su organización que puede recibir llamadas de voz.
    - **Aplicación de voz:** otro operador automático o una cola de llamadas.
    - **Número de teléfono externo:** cualquier número de teléfono. Use este formato: +[código de país][código de área][número de teléfono]
    - **Correo de** voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.
    - **Operador:** el operador definido para el operador automático. Definir un operador es opcional. El operador se puede definir como cualquiera de los otros destinos de esta lista.

    Se recomienda establecer 0 clave para el operador.

    Para cada opción de menú, especifique lo siguiente:

    - **Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.

    - **Comando de voz:** define el comando de voz que un autor de la llamada puede dar para obtener acceso a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras como "Servicio al cliente" o "Operaciones y motivos". 

    - **Redirigir a:** a dónde quiere que vaya la llamada cuando los autores de llamadas elijan esta opción. Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada.

    ![Captura de pantalla de las opciones de la tecla de marcado](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Si desea usar este operador automático como directorio de la empresa, en **Búsqueda** de directorios, **seleccione Marcar por nombre.** Al habilitar esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono. Cualquier usuario en línea con una licencia del sistema telefónico es un usuario apto y se puede encontrar con Marcado por nombre. 

    (Puede elegir **Marcar por extensión,** pero la extensión debe configurarse en Azure Active Directory).

5. Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 4: flujo de llamadas después de horas >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Paso 4 <br> Después de horas](#tab/after-hours)

El horario laboral se puede establecer para cada operador automático. Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada. El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral. Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para las horas adicionales.

Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas adicionales para los operadores automáticos con números de teléfono directos.

Si quiere un enrutamiento de llamadas independiente para las personas que llaman fuera del horario laboral, especifique su horario laboral para cada día. Haga **clic en Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar un descanso para el almuerzo.

![Captura de pantalla de la configuración de días y horas adicionales](../media/auto-attendant-business-hours.png)

Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para horas adicionales. Las mismas opciones están disponibles que para el enrutamiento de llamadas en horario laboral que especificó en **el paso 3 : flujo de llamadas.**

Haga **clic en** Siguiente cuando haya terminado.

> [!div class="nextstepaction"]
> [Paso 5: flujo de llamadas navideñas >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Paso 5 <br> Días festivos](#tab/holidays)

Puede hacer que las llamadas a su operador automático se enrute de forma diferente en días festivos que en otros días. (Si no desea tener un flujo de llamadas diferente para días festivos, puede omitir este paso).



El operador automático puede tener un flujo de llamadas para cada día festivo que haya configurado. Puede agregar un máximo de 20 días festivos programados a cada operador automático.

1. En la página Configuración de llamadas navideñas, haga clic **en Agregar.**

2. Escriba un nombre para esta configuración navideña.

3. En la **lista desplegable** Vacaciones, elija los días festivos que quiera usar.

4. Elija el tipo de saludo que desea usar.

    ![Captura de pantalla de la configuración de saludo navideña y navideña](../media/auto-attendant-holiday-greeting.png)

5. Elija si desea desconectar **o** **redirigir** la llamada.

6. Si elige redirigir, elija el destino de enrutamiento de llamadas para la llamada.

    ![Captura de pantalla de la configuración de acción de llamada navideña](../media/auto-attendant-holiday-actions.png)

7. Haga clic en **Guardar**.

Repita el procedimiento según sea necesario para cada vacaciones adicionales.

![Captura de pantalla de la configuración de vacaciones con días festivos en la lista](../media/auto-attendant-holiday-call-settings.png)

Cuando haya agregado todos los días festivos, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 6: elija quién está en el directorio >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Paso 6 <br> Miembros del directorio](#tab/dial-scope)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de la llamada usa marcado por nombre o marcado por extensión. El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una licencia del sistema telefónico.

Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad.  Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado. (Si un usuario está en ambas listas, se excluirá del directorio).

![Captura de pantalla del ámbito de marcado para incluir y excluir opciones](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio.

Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 7: Asignar una cuenta de recursos >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Paso 7 <br> Cuentas de recursos](#tab/resource-accounts)

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos que tenga un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.

Para agregar una cuenta de recursos

1. Haga **clic en Agregar** cuenta y busque la cuenta que desea agregar. Haga **clic en Agregar** y, a continuación, haga clic en **Agregar.**

    ![Captura de pantalla del panel agregar cuentas de la cuenta de recursos](../media/auto-attendant-add-resource-account.png)

2. Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**

    ![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado](../media/auto-attendant-resource-account-assigned.png)

Esto completa la configuración del operador automático.

---


