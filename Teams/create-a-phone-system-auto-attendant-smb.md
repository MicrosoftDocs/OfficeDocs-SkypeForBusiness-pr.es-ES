---
title: Configurar un operador automático para Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
ms.localizationpriority: medium
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar y administrar operadores automáticos en Microsoft Teams.
ms.openlocfilehash: b783f268fa60b5212d50962dbb78988e6158390d
ms.sourcegitcommit: 850038f2248c1ea412f7b5daca26c0598baffa3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2022
ms.locfileid: "67443497"
---
# <a name="set-up-an-auto-attendant"></a>Configurar un operador automático

Los operadores automáticos permiten que las personas llamen a su organización y naveguen por un sistema de menús para hablar con el departamento, la cola de llamadas, la persona o un operador adecuados. Puede crear operadores automáticos para su organización con el Centro de administración de Microsoft Teams o con PowerShell.

Asegúrese de que ha leído [Plan para operadores automáticos y colas de llamadas de Teams](plan-auto-attendant-call-queue.md) y ha seguido los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de este artículo.

Los operadores automáticos pueden redirigir las llamadas, en función de la entrada de los autores de llamadas, a uno de los siguientes destinos:

- **Operador:** el operador definido para el operador automático. Definir un operador es opcional. El operador puede definirse como cualquiera de los otros destinos de esta lista.
- **Persona de la organización** : una persona de la organización que puede recibir llamadas de voz. Esta persona puede ser un usuario en línea o un usuario hospedado localmente mediante Skype Empresarial Server.
- **Aplicación de voz** : otro operador automático o una cola de llamadas. (Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).
- **Correo de voz** : el buzón de voz asociado a un grupo de Microsoft 365 que especifique. Puede elegir si quiere las transcripciones del correo de voz y "Deje un mensaje después del tono". símbolo del sistema.
  - En el Centro de Administración de M365, habilite "Permitir que personas que no pertenezcan a la organización envíe un correo electrónico a este equipo" para el grupo de Microsoft 365 que especifique
- **Número de teléfono externo** : cualquier número de teléfono. Consulta [los detalles técnicos de las transferencias externas](create-a-phone-system-auto-attendant.md?tabs=general-info#external-phone-number-transfers---technical-details).
- **Anuncio (archivo de audio):** reproducir un archivo de audio. Un mensaje de anuncio grabado que carga y que se guarda como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede tener más de 5 MB. El sistema reproduce el anuncio y, a continuación, vuelve al menú del operador automático.
- **Anuncio (escrito):** escriba un mensaje. Texto que quiere que lea el sistema. Puede escribir hasta 1000 caracteres. El sistema reproduce el anuncio y, a continuación, vuelve al menú del operador automático.

> [!NOTE]
> Al redirigir llamadas a una **persona de la organización**, esa persona debe tener habilitada la voz. Para obtener más información sobre cómo habilitar la voz, consulte [Asignar licencias de complementos de Teams a usuarios](teams-add-on-licensing/assign-teams-add-on-licenses.md).
>
> Al definir un **operador** es opcional, se recomienda.  Los operadores automáticos redirigen las llamadas al operador si el autor de la llamada no realiza una selección en los menús, selecciona repetidamente opciones no válidas o marca repetidamente por nombre o número.  Si no se define un operador, el operador automático anulará la llamada.

## <a name="whats-new-for-auto-attendants-in-the-past-6-months"></a>Novedades para los operadores automáticos en los últimos 6 meses
 
 - Agosto: las **opciones del menú Reproducir** en Flujo de llamadas, Flujo de llamadas fuera del horario laboral y Flujo de llamadas durante los días festivos ahora admiten \* las teclas (asterisco) y \# (almohadilla).
 - Julio: el flujo de llamadas durante los días festivos ahora admite **las opciones del menú Reproducir**.
 
## <a name="steps-to-create-an-auto-attendant"></a>Pasos para crear un operador automático
Los pasos para agregar un operador automático son:

1. Configurar información general.
1. Configure un flujo de llamadas básico.
1. Configure un flujo de llamadas fuera del horario laboral.
1. Configurar flujos de llamadas navideñas.
1. Configurar el ámbito de marcado.
1. Configurar cuentas de recursos.

Los pasos descritos en el artículo crean operadores automáticos con el Centro de administración de Teams. Para obtener instrucciones para **crear operadores automáticos con PowerShell**, consulte [Creación de operadores automáticos con cmdlets de PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estos pasos para configurar su operador automático

# <a name="step-1-general-info"></a>[Paso 1: Información general](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>Paso 1: Establecer la información general del operador automático

Para configurar un operador automático, en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851), expanda **Voz**, seleccione **Operadores automáticos** y, a continuación, seleccione **Agregar**.

1. Escriba un nombre para el operador automático en el cuadro de la parte superior.

2. Para designar un operador, especifique el destino de las llamadas al operador. Esta designación es opcional, pero se recomienda. Establezca la opción **Operador** para permitir que los autores de llamadas salgan de los menús y hablen con una persona designada.

3. Especifique la zona horaria de este operador automático. La zona horaria se utiliza para calcular el horario laboral si [crea un flujo de llamada independiente para fuera del horario laboral](?tabs=after-hours).

4. Especifique un [idioma admitido](create-a-phone-system-auto-attendant-languages.md) para este operador automático. Este es el idioma que se usará para los mensajes de voz generados por el sistema.

5. Elija si desea habilitar las entradas de voz. Cuando está habilitada, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".

   > [!NOTE]
   > Si elige un idioma en el paso 4 que no admite entradas de voz, esta opción se deshabilitará.

Una vez que haya configurado la información general del operador automático, seleccione **Siguiente**.

# <a name="step-2-basic-call-flow"></a>[Paso 2: Flujo de llamadas básico](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>Paso 2: Configurar el flujo de llamadas básico

### <a name="set-a-greeting"></a>Establecer un saludo

- Si selecciona **Reproducir un archivo de audio** , puede usar el botón **Cargar archivo** para cargar un mensaje de saludo grabado guardado como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede tener más de 5 MB.

- Si selecciona **Escribir un mensaje de saludo** , el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.

### <a name="route-the-call"></a>Enrutar la llamada

- Si selecciona **Desconectar**, el operador automático colgará la llamada.
- Si selecciona **Redirigir llamada**, puede elegir uno de los destinos de enrutamiento de llamadas.
- Si selecciona **las opciones del menú Reproducir**, puede elegir **entre Reproducir un archivo de audio** o **Escribir un mensaje de saludo** y, después, elegir entre las opciones de menú y la búsqueda en directorio.

#### <a name="play-menu-options"></a>Reproducir opciones de menú

*Las teclas Nuevo - \* (asterisco) y \# (almohadilla) ahora se pueden usar en las opciones de menú*.

Para las opciones de marcación, asigne las teclas 0-9 del teclado del teléfono a uno de los destinos de enrutamiento de llamadas. Las teclas \* (asterisco) y \# (almohadilla) están reservadas por el sistema y no se pueden reasignar. Al presionar cualquiera de estas teclas, se repetirá el menú actual.

> [!NOTE]
> La tecla # solo realiza copias de seguridad del operador automático más reciente. Una vez que se cruza el límite con un nuevo operador automático, la tecla # no podrá llevarte al anterior.

Las asignaciones clave no tienen por qué ser continuas. Es posible crear un menú con las teclas 0, 1 y 3 asignadas a opciones, mientras que la tecla número 2 no se usa.

Se recomienda asignar la clave cero al operador si ha configurado una. Si el operador no está establecido en ninguna tecla, el comando de voz "Operador" también está deshabilitado.

Para cada opción de menú, especifique la siguiente configuración:

- **Tecla de marcado** : la tecla del teclado del teléfono para acceder a esta opción. Si hay entradas de voz disponibles, los autores de llamadas también pueden decir este número para acceder a la opción.

- **Comando de voz** : define el comando de voz que puede dar el autor de la llamada para acceder a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras, como "Atención al cliente" o "Operaciones y motivos". Por ejemplo, el autor de la llamada puede presionar 2, decir "dos" o decir "Ventas" para seleccionar la opción asignada a las dos teclas. Este texto también se representa mediante texto a voz para el aviso de confirmación del servicio, que podría ser algo como "Transferir la llamada a ventas".

- **Redirigir a** : el destino de enrutamiento de llamadas que se usa cuando los autores de llamadas eligen esta opción. Si está redirigiendo a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada con él.

##### <a name="directory-search"></a>Búsqueda en directorios

Si asigna claves de marcado a destinos, le recomendamos que elija **Ninguno** para **búsqueda en el directorio**. Si el autor de la llamada intenta marcar un nombre o una extensión mediante claves asignadas a destinos específicos, es posible que se rediriban inesperadamente a un destino antes de terminar de escribir el nombre o la extensión. Le recomendamos que cree un operador automático independiente para la búsqueda en directorios y que el operador automático principal le vincule con una clave de marcado.

Si no ha asignado claves de marcado, elija una opción para **Búsqueda en el directorio**.

**Marcar por nombre** : si habilita esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono. Cualquier usuario en línea o cualquier usuario hospedado localmente mediante Skype Empresarial Server, es un usuario apto y puede encontrarse con Marcado por nombre.

**Marcar por extensión** : si habilita esta opción, los autores de llamadas pueden conectarse con los usuarios de su organización marcando su extensión de teléfono. Cualquier usuario en línea o cualquier usuario hospedado localmente mediante Skype Empresarial Server, es un usuario apto y puede encontrarse con **Marcado por extensión**. (Puede establecer quién está y quién no está incluido en el directorio en la página [Ámbito de marcado](?tabs=dial-scope) ).

> [!NOTE]
> Si desea usar las características **Marcado por nombre** y **Marcado por extensión** , puede asignar una tecla de marcado a su operador automático principal para que llegue a un operador automático habilitado para **Marcado por nombre**. Dentro de ese operador automático, puede asignar la tecla 1 (que no tiene letras asociadas con él) para alcanzar el **Dial por operador automático de extensión** .

Para obtener más información, consulte [el dial y la referencia de voz](dial-voice-reference.md).

Una vez que haya establecido las opciones básicas de flujo de llamadas, seleccione **Siguiente**.

# <a name="step-3-after-hours-call-flow"></a>[Paso 3: Flujo de llamadas fuera del horario laboral](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>Paso 3: Configurar el flujo de llamadas para fuera del horario laboral (opcional)

El horario laboral se puede establecer para cada operador automático.

- Si no se establece el horario laboral, todos los días y todas las horas del día se consideran horas laborables porque se establece una programación 24/7 de forma predeterminada.
- El horario laboral se puede establecer con descansos temporales durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral.
- Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para fuera del horario laboral.

Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo deba especificar el enrutamiento de llamadas fuera del horario laboral para los operadores automáticos con números de teléfono directos.

Si desea un enrutamiento de llamadas independiente para los autores de llamadas fuera del horario laboral, especifique el horario laboral de cada día.

1. Junto al día de la semana en la tabla, ajuste **las opciones Iniciar en** y **Finalizar a** veces.
1. Si es necesario, seleccione **Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una pausa para el almuerzo.
1. Elija las opciones de enrutamiento de llamadas para después de horas. También están disponibles las mismas opciones generales de flujo de llamadas fuera del horario laboral.

Una vez que haya agregado el flujo de llamadas fuera del horario laboral, seleccione **Siguiente**.

# <a name="step-4-holiday-call-flow"></a>[Paso 4: Flujo de llamadas navideñas](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>Paso 4: Configurar flujos de llamadas para días festivos (opcional)

El operador automático puede tener un flujo de llamadas para cada [día festivo que haya configurado](set-up-holidays-in-teams.md). Puede agregar un máximo de 20 días festivos programados a cada operador automático.

*Nuevo: las **opciones del menú Reproducir** ya están disponibles en los flujos de llamadas navideñas*.

1. En la página Configuración de llamadas navideñas, seleccione **Agregar**.

1. Escriba un nombre para esta configuración navideña.

1. En la lista desplegable **Días festivos** , elija los días festivos que quiera usar.

1. Elija el tipo de saludo que desea usar.

1. Elija si desea **Desconectar** o **Redirigir** la llamada.

    1. Si decide redirigir, elija el destino del enrutamiento de llamadas para la llamada.
    1. Si elige reproducir las opciones de menú, configure las **opciones del menú Reproducir**.

1. Seleccione **Guardar**.

Repita el procedimiento según sea necesario para cada día festivo adicional.

Una vez que haya agregado todas las horas de vacaciones, seleccione **Siguiente**.

# <a name="step-5-dial-scope"></a>[Paso 5: Ámbito de marcado](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>Paso 5: Configurar el ámbito de marcado (opcional)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando el autor de la llamada usa el marcado por nombre o marcado por extensión. El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de la organización que sean usuarios en línea o que se hospeden localmente con Skype Empresarial Server.

Puede incluir o excluir usuarios específicos seleccionando Grupo de **usuarios personalizados** en **Incluir** o **Excluir** y eligiendo uno o más grupos de Microsoft 365, listas de distribución o grupos de seguridad. Por ejemplo, es posible que desee excluir a los ejecutivos de su organización del directorio de marcado.

Si un usuario está en ambas listas, se excluirá del directorio.

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer su nombre en el directorio.

Una vez que haya seleccionado las opciones de **Ámbito de marcado** , seleccione **Siguiente**.

# <a name="step-6-resource-accounts"></a>[Paso 6: Cuentas de recursos](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>Paso 6: Configurar cuentas de recursos (opcional)

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recurso que tenga un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.

Para agregar una cuenta de recursos, seleccione **Agregar cuenta** y busque la cuenta que desea agregar. Selecciona **Agregar** y, a continuación, **Agregar**.

Una vez que haya agregado cuentas de recursos, seleccione **Siguiente**.

Consulte [Administrar cuentas de recursos de Teams](manage-resource-accounts.md) para obtener más información.

---

## <a name="resources-for-complex-scenarios"></a>Recursos para escenarios complejos

### <a name="external-phone-number-transfers---technical-details"></a>Transferencias de números de teléfono externos: detalles técnicos

Consulte los [Requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas externamente.  Además:

- Para una cuenta de recursos con una [licencia de Plan de llamadas](calling-plans-for-office-365.md) o un número De conexión de [operador](operator-connect-plan.md) , el número de teléfono de transferencia externa debe especificarse en formato E.164 (+[código de país][código de área][número de teléfono]).

- Para una cuenta de recursos con una licencia de Teléfono Microsoft Teams y una directiva de enrutamiento de voz en línea de enrutamiento directo, el formato de número de teléfono de transferencia externa depende de la configuración del [controlador de borde de sesión (SBC](direct-routing-connect-the-sbc.md)).

El número de teléfono saliente que se muestra se determina de la siguiente manera:

- Para los números Plan de llamadas y Conectar operador, se muestra el número de teléfono del autor de la llamada original.
- Para los números de enrutamiento directo, el número enviado se basa en la configuración de P-Asserted-Identity (PAI) en el SBC, como se indica a continuación:
  - Si se establece en Deshabilitado, se muestra el número de teléfono del autor de la llamada original. Esta es la configuración predeterminada y recomendada.
  - Si se establece en Habilitado, se muestra el número de teléfono de la cuenta de recursos.

En un entorno Skype Empresarial híbrido, para transferir una llamada de operador automático a rtc, cree un nuevo usuario local con el desvío de llamadas establecido en el número de RTC. El usuario debe estar habilitado para Telefonía IP empresarial y tener asignada una directiva de voz. Para obtener más información, consulte [Transferencia automática de llamadas de operador a RTC](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="auto-attendant-diagnostic-tool"></a>Herramienta de diagnóstico de Operador automático

Si es administrador, puede usar la siguiente herramienta de diagnóstico para validar que un operador automático pueda recibir llamadas:

1. Seleccione **Ejecutar pruebas** a continuación. Esto rellenará el diagnóstico en el Centro de administración de Microsoft 365.

   > [!div class="nextstepaction"]
   > [Ejecutar pruebas: Operador automático de Teams](https://aka.ms/TeamsAADiag)

2. En el panel Ejecutar diagnóstico, escriba la cuenta de recurso en el campo **Nombre de usuario o Email** y, después, seleccione **Ejecutar pruebas**.

3. Las pruebas identificarán las configuraciones de cuenta de recursos, directivas o inquilinos que impiden que el operador automático pueda recibir llamadas y proporcionarán pasos para corregir los problemas identificados.

### <a name="related-topics"></a>Temas relacionados

[Esto es lo que obtiene con Teams Phone](./here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](./getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
