#### <a name="video-demonstration"></a>Demostración de vídeo

En este vídeo se muestra un ejemplo básico de cómo crear un operador automático en Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a>Antes de empezar

Obtenga los números de servicio (los números de servicio son un tipo especial de número de teléfono que usan los operadores automáticos) que necesita para los operadores automáticos a los que desea obtener acceso mediante la marcación directa desde fuera de su organización. Esto puede incluir [la transferencia de números de otro proveedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](../getting-service-phone-numbers.md)

A cada operador automático se le debe asignar una Sistema telefónico: licencia de usuario virtual. Al comprar Business Voice, también recibió una serie de Sistema telefónico: licencias de usuario virtual, por lo que probablemente no necesite solicitar más. Sin embargo, si necesita más en el futuro, puede obtenerlas siguiendo las instrucciones de [Sistema telefónico - Licencia de usuario virtual](../teams-add-on-licensing/virtual-user.md).

Si desea que la ruta de operador automático [](../set-up-holidays-in-teams.md) llame de forma diferente los días festivos, cree los días festivos que quiera usar antes de crear el operador automático.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estos pasos para configurar el operador automático

# <a name="step-1brphone-number"></a>[Paso 1 <br> Teléfono número](#tab/phone-number)

> [!NOTE]
> Si sigue los pasos para configurar Business Voice por primera vez y está en el paso **6:** Configurar un operador automático para el número de teléfono principal de su empresa, ya ha terminado los pasos de esta pestaña. Ir a la pestaña siguiente: [Información general del operador automático.](?tabs=general-info#steps)

Cada operador automático que cree requiere una cuenta de recursos. Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada con un operador automático o una cola de llamadas en lugar de una persona. En este paso, crearemos la cuenta, le asignaremos una licencia *Microsoft 365 Sistema telefónico usuario virtual* y, a continuación, asignaremos un número de servicio.

### <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Puede crear una cuenta de recursos en el centro Teams administración.

1. En el Teams de administración, expanda **Configuración de** toda la organización y, a continuación, haga clic en Cuentas **de recursos.**

2. Haga clic en **Agregar**.

3. En el **panel Agregar cuenta de** recursos, rellene **Nombre** para mostrar, Nombre de **usuario** y elija **Operador automático** para el tipo de **cuenta Recurso**

    ![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

4. Haga clic en **Guardar**.

    La nueva cuenta aparecerá en la lista de cuentas.

    ![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Asignar una licencia

Debe asignar una licencia *Microsoft 365 Sistema telefónico usuario virtual* a la cuenta de recursos.

1. En el Microsoft 365 de administración, haga clic en la cuenta de recursos a la que desea asignar una licencia.

2. En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**

3. Haga clic **en Guardar cambios.**

    ![Captura de pantalla de la interfaz de usuario asignar licencias en el Microsoft 365 de administración](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Asignar un número de servicio

Si necesita que este operador automático sea accesible mediante un número de teléfono, asigne ese número a la cuenta de recursos.

1. En el Teams de administración,  en la página Cuentas de recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en Asignar **o desasignación.**

2. En el **Teléfono de tipo de número,** elija el tipo de número que desea usar.

3. En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**

    ![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

4. Haga clic en **Guardar**.

> [!div class="nextstepaction"]
> [Paso 2: Información general del operador automático >](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Paso 2 <br> Información general del operador](#tab/general-info)

Para configurar un operador automático

1. En el Teams de administración, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic en **Agregar.**

2. Escriba un nombre para el operador automático en el cuadro de la parte superior.

3. Si desea designar un operador, especifique el destino de las llamadas al operador. Esto es opcional (pero recomendado). Puede establecer la opción **Operador** para permitir a los autores de llamadas salir de los menús y hablar con una persona designada.

4. Especifique la zona horaria para este operador automático. La zona horaria se usa para calcular el horario laboral si crea un flujo de llamadas independiente para horas posteriores.

5. Especifique un idioma para este operador automático. Este es el idioma que se usará para las solicitudes de voz generadas por el sistema.

6. Elija si desea habilitar las entradas de voz. Cuando se habilita, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".

    ![Captura de pantalla de la configuración del operador automático para el nombre, el operador, la zona horaria, el idioma y las entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. Haga clic en **Siguiente**.

> [!div class="nextstepaction"]
> [Paso 3: flujo de llamadas >](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Paso 3 <br> Flujo de llamadas](#tab/call-flow)

Elegir las opciones de flujo de llamadas

1. Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.

    Si selecciona **Reproducir un archivo de audio,** puede usar el botón **Upload** archivo para cargar un mensaje de saludo grabado guardado como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede ser superior a 5 MB.

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
    - **Correo de** voz: el buzón de voz asociado a Microsoft 365 grupo que especifique.
    - **Operador:** el operador definido para el operador automático. Definir un operador es opcional. El operador se puede definir como cualquiera de los otros destinos de esta lista.

    Se recomienda establecer 0 clave para el operador.

    Para cada opción de menú, especifique lo siguiente:

    - **Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.

    - **Comando de voz:** define el comando de voz que un autor de la llamada puede dar para obtener acceso a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras como "Servicio al cliente" o "Operaciones y motivos". 

    - **Redirigir a:** a dónde quiere que vaya la llamada cuando los autores de llamadas elijan esta opción. Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada.

    ![Captura de pantalla de las opciones de la tecla de marcado](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Si desea usar este operador automático como directorio de la empresa, en **Búsqueda** de directorios, **seleccione Marcar por nombre.** Al habilitar esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono. Cualquier usuario en línea con una Sistema telefónico es un usuario apto y se puede encontrar con Marcado por nombre. 

    (Puede elegir Marcar **por extensión,** pero la extensión debe configurarse en Azure Active Directory).

5. Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 4: flujo de llamadas después de horas >](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Paso 4 <br> Después de horas](#tab/after-hours)

El horario laboral se puede establecer para cada operador automático. Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada. El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral. Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para las horas adicionales.

Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas adicionales para los operadores automáticos con números de teléfono directos.

Si quiere un enrutamiento de llamadas independiente para las personas que llaman fuera del horario laboral, especifique su horario laboral para cada día. Haga **clic en Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar un descanso para el almuerzo.

![Captura de pantalla de la configuración de días y horas adicionales](../media/auto-attendant-business-hours.png)

Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para horas adicionales. Las mismas opciones están disponibles que para el enrutamiento de llamadas en horario laboral que especificó en **el paso 3 : flujo de llamadas.**

Haga **clic en** Siguiente cuando haya terminado.

> [!div class="nextstepaction"]
> [Paso 5: flujo de llamadas navideñas >](?tabs=holidays#steps)

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
> [Paso 6: elija quién está en el directorio >](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Paso 6 <br> Miembros del directorio](#tab/dial-scope)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de la llamada usa marcado por nombre o marcado por extensión. El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una Sistema telefónico licencia.

Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad.  Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado. (Si un usuario está en ambas listas, se excluirá del directorio).

![Captura de pantalla del ámbito de marcado para incluir y excluir opciones](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio.

Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**

> [!div class="nextstepaction"]
> [Paso 7: Asignar una cuenta de recursos >](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Paso 7 <br> Cuentas de recursos](#tab/resource-accounts)

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos que tenga un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.

Para agregar una cuenta de recursos

1. Haga **clic en** Agregar y busque la cuenta que desea agregar. Haga **clic en Agregar** y, a continuación, haga clic en **Agregar.**

    ![Captura de pantalla del panel agregar cuentas de la cuenta de recursos](../media/auto-attendant-add-resource-account.png)

2. Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**

    ![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado](../media/auto-attendant-resource-account-assigned.png)

    Esto completa la configuración del operador automático.

---
