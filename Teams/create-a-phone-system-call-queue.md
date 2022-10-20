---
title: Crear una cola de llamadas en Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Obtenga información sobre cómo configurar colas de llamadas en Microsoft Teams. Las colas de llamadas proporcionan un mensaje de saludo, música en espera, redirección de llamadas y otras características.
ms.openlocfilehash: 6fe298a3054165a95f496f8c1178a7fa8457542d
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614233"
---
# <a name="create-a-call-queue"></a>Crear una cola de llamada

Las colas de llamadas redirigen a los autores de llamadas a personas de su organización que pueden ayudarles con un problema o pregunta concretos. Las llamadas se distribuyen de una en una a los usuarios de la cola, que se conocen como *agentes*.

Las colas de llamadas proporcionan:

- Un mensaje de saludo.
- Música que se reproduce mientras los usuarios se mantienen a la espera.
- Enrutamiento de llamadas *Primera en llegar, primera en salir* (FIFO),en la orden para los agentes.
- Opciones de gestión del desbordamiento de la cola y del tiempo de espera.

Antes de seguir los procedimientos de este artículo, asegúrese de que ha leído [Planear operadores automáticos y colas de llamadas de Teams](plan-auto-attendant-call-queue.md) y ha seguido los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started).

## <a name="whats-new-for-call-queues-in-the-past-6-months"></a>Novedades de las colas de llamadas en los últimos 6 meses

- Agosto
  - Ahora se admite **agregar un mensaje de saludo** (Texto a voz (TTS) para el saludo principal de la cola de llamadas.
  - **Los** controles de los mensajes del sistema de omitir correo de voz ahora se exponen al enrutamiento al correo de voz compartido, lo que también se aplica a las indicaciones **de Agregar un mensaje de saludo** .

## <a name="steps-to-create-a-call-queue"></a>Pasos para crear una cola de llamadas

Los pasos para configurar una cola de llamadas incluyen:

1. Configurar información general
1. Establecer el saludo y la música
1. Configurar el contestador
1. Elegir y asignar agentes
1. Establecer el control de desbordamiento de llamadas
1. Establecer la administración del tiempo de espera de llamadas

Los pasos descritos en el artículo crean colas de llamadas con el Centro de administración de Teams. Para obtener instrucciones para crear colas de llamadas con PowerShell, consulte [Creación de colas de llamadas con cmdlets de PowerShell](create-a-phone-system-call-queue-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>Siga estos pasos para configurar la cola de llamadas

# <a name="step-1-general-info"></a>[Paso 1: Información general](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>Paso 1: Configurar información general

Para configurar una cola de llamadas, en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851), expanda **Voz**, seleccione Colas de **llamadas** y, a continuación, seleccione **Agregar**.

Escriba un nombre para la cola de llamadas en el cuadro de la parte superior.

### <a name="add-a-resource-account"></a>Agregar una cuenta de recursos

Para agregar una cuenta de recursos existente:

1. En **Cuentas de recursos**, haga clic en el botón **Agregar** para agregar una cuenta de recursos para esta cola de llamadas.
1. En el panel **Agregar cuentas** , busque la cuenta de recursos que desea agregar.
1. Seleccione el botón **Agregar** junto a la cuenta de recursos que desea asignar a esta cola de llamadas.
1. En la parte inferior del panel, seleccione el botón **Agregar** .

Si necesita crear una cuenta de recursos:

1. En **Cuentas de recursos**, haga clic en el botón **Agregar** para agregar una cuenta de recursos para esta cola de llamadas.
1. En el panel **Agregar cuentas** , busque cualquier conjunto de letras para que aparezca la lista desplegable de resultados.
1. Seleccione el botón **+ Agregar una cuenta de recurso** en la parte inferior de los resultados.
1. En el panel **Agregar cuenta de recursos** :
    1. Escriba un **nombre para mostrar** descriptivo, que será visible para los agentes.
    1. Escriba un **nombre de usuario** descriptivo para la cuenta de recursos.
    1. Seleccione la lista desplegable **Tipo de cuenta de** recurso y seleccione **Cola de llamadas**.
1. En la parte inferior del panel, seleccione el botón **Guardar** .
1. En el panel **Cuentas de recursos** , seleccione el botón **Agregar** .

Los agentes verán el nombre de la cuenta del recurso cuando reciban una llamada entrante.

Para obtener más información, consulte [Administrar cuentas de recursos de Teams](manage-resource-accounts.md).

### <a name="assign-a-calling-id-optional"></a>Asignar un id. de llamada (opcional)

**Disponible para usuarios de escritorio de llamadas colaborativas o de canal de Teams y usuarios de clientes móviles de Teams con colas de llamadas estándar.**

Puede asignar números de identificación de llamadas salientes a los agentes especificando una o más cuentas de recursos con un número de teléfono. Los agentes pueden seleccionar el número de identificación de llamada saliente que se usará con cada llamada saliente que realicen. En la aplicación Llamadas, los agentes pueden usar su número de cola de llamadas o operador automático (AA) o su propio dial directo entrante (DID) personal.

> [!NOTE]
> La cuenta de recursos usada para fines de identificador de llamadas debe tener una licencia **de cuenta de recursos de Teléfono Microsoft Teams** y una de las siguientes asignadas:
>
> - Una licencia del plan de llamadas y un número de teléfono asignados
> - Un número de teléfono De conexión de operador asignado
> - Una directiva de enrutamiento de voz en línea (la asignación de números de teléfono es opcional al usar enrutamiento directo)

1. En **Asignar identificador de llamada**, seleccione el botón **Agregar** .
1. En el panel **Agregar cuentas** , busque las cuentas de recursos que desea permitir que los agentes usen con fines de identificación de llamadas salientes.
1. Seleccione el botón **Agregar** junto a la cuenta de recursos con un número de teléfono asignado.
1. Seleccione el botón **Agregar** en la parte inferior del panel.

Si no tiene una cuenta de recursos con un número de teléfono asignado:

1. En **Cuentas de recursos**, haga clic en el botón **Agregar** para agregar una cuenta de recursos.
1. En el panel **Agregar cuentas** , busque cualquier conjunto de letras para que aparezca la lista desplegable de resultados.
1. Seleccione el botón **+ Agregar una cuenta de recurso** en la parte inferior de los resultados.
1. En el panel **Agregar cuenta de recursos** :
    1. Escriba un **nombre para mostrar** descriptivo, que será visible para llamar a los destinatarios.
    1. Escriba un **nombre de usuario** descriptivo para la cuenta de recursos.
    1. Seleccione la lista desplegable **Tipo de cuenta de** recurso y seleccione **Cola de llamadas**.
1. En la parte inferior del panel, seleccione el botón **Guardar** .
1. En el panel **Cuentas de recursos** , seleccione el botón **Agregar** .

Después de crear esta nueva cuenta de recurso para el identificador de llamada, seguirá necesitando lo siguiente:

- Asignar una [licencia de cuenta de recursos telefónicos de Teams](manage-resource-accounts.md#assign-a-license)
- Asignar una licencia de Plan de llamadas de Microsoft, asignar un número de teléfono Conectar operador o asignar una directiva de enrutamiento de voz en línea para direct routing
- Asignar el [número de teléfono de servicio a la cuenta de recursos](manage-resource-accounts.md#assign-a-service-number), si usa Microsoft Calling Plan

### <a name="set-the-call-queue-language"></a>Establecer el idioma de la cola de llamadas

Elige un [idioma admitido](create-a-phone-system-call-queue-languages.md).

Este idioma se usará para mensajes de voz generados por el sistema y transcripción del correo de voz, si los habilita.

Una vez que haya seleccionado un idioma, seleccione el botón **Siguiente** en la parte inferior de la página **Agregar una cola de llamadas** .

# <a name="step-2-greeting-and-music"></a>[Paso 2: Saludo y música](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>Paso 2: Agregar un saludo y música en espera

*Nuevo: **agregar un mensaje de saludo** (texto a voz (TTS) ahora es compatible con el saludo principal de la cola de llamadas.*

Especifique si quiere reproducir un *saludo* a los autores de llamadas cuando lleguen a la cola.

- Si selecciona **Reproducir un archivo de audio**, debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir. La grabación cargada no puede ser superior a 5 MB.

- Si selecciona **Escribir un mensaje de saludo**, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando la cola de llamadas responda a una llamada.

Teams proporciona música predeterminada a los autores de llamadas mientras están *en espera en una cola*.

- La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar ningún pago de la organización.
- Si desea reproducir un archivo de audio específico, elija **Reproducir un archivo de audio en** y cargar un archivo MP3, WAV o WMA.

> [!NOTE]
> Usted es responsable de borrar y proteger de forma independiente todos los derechos y permisos necesarios para usar cualquier archivo de música o audio con su servicio de Microsoft Teams, que puede incluir propiedad intelectual y otros derechos en cualquier música, efectos de sonido, audio, marcas, nombres y otro contenido en el archivo de audio de todos los titulares de derechos pertinentes, que pueden incluir artistas,  actores, artistas intérpretes o ejecutantes, músicos, compositores, compositores, sellos discográficos, editores musicales, sindicatos, sindicatos, sociedades de derechos, organizaciones de gestión colectiva y cualquier otra parte que posea, controle o licencia los derechos de autor de música, efectos sonoros, audio y otros derechos de propiedad intelectual.

Una vez que haya seleccionado un saludo y música en espera, seleccione el botón **Siguiente** en la parte inferior de la página **Agregar una cola de llamadas** .

# <a name="step-3-call-answering"></a>[Paso 3: Responder llamadas](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>Paso 3: Configurar quién responderá a las llamadas entrantes

Revise los [requisitos previos para agregar agentes a una cola de llamadas](plan-auto-attendant-call-queue.md#prerequisites).

### <a name="teams-channel"></a>Canal de Teams

Puede agregar hasta 200 agentes a través de un canal de Teams. Debe ser miembro del equipo o el creador o propietario del canal para agregar un canal a la cola.

Si desea [usar un canal de Teams para administrar la cola](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e):

1. Seleccione el botón de radio **Elegir un equipo** y seleccione **Agregar un canal**.
1. Busque el equipo que desea usar, selecciónelo y seleccione **Agregar**.
1. Seleccione el canal que quiera usar (solo se admiten canales estándar) y seleccione **Aplicar**.

Los siguientes clientes son compatibles al usar un canal de Teams para colas de llamadas:

- Cliente de Windows de Microsoft Teams
- Cliente de Microsoft Teams para Mac

> [!NOTE]
> Si utiliza esta opción, la cola de llamadas puede tardar hasta 24 horas en funcionar por completo.
>
> Si hay más de 200 miembros en el equipo, solo se agregarán los primeros 200 miembros, en orden alfabético, como agentes a la cola de llamadas.

### <a name="users-and-groups"></a>Usuarios y grupos

Puede agregar hasta 20 agentes individualmente y hasta 200 agentes a través de grupos.

Si desea agregar usuarios o grupos individuales a la cola:

1. Seleccione el botón de radio **Elegir usuarios y grupos** .

Para **agregar un usuario** a la cola:

1. Seleccione **Agregar usuarios**, busque el usuario, haga clic en **Agregar** y, a continuación, haga clic en **Agregar**.

Para **agregar un grupo** a la cola:

1. Seleccione **Agregar grupos**, busque el grupo, haga clic en **Agregar** y, a continuación, haga clic en **Agregar**. 
    1. Puede usar listas de distribución, grupos de seguridad, grupos de seguridad, grupos de Microsoft 365 o equipos de Microsoft Teams.

> [!NOTE]
> Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.
>
> Si hay más de 200 miembros en el grupo, solo se agregarán los primeros 200 miembros, en orden alfabético, como agentes a la cola de llamadas.

### <a name="conference-mode"></a>Modo de conferencia

**El modo de conferencia** reduce la cantidad de tiempo que tarda el autor de la llamada en conectarse a un agente después de que el agente acepte la llamada. Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:

- Última versión del cliente de escritorio de Microsoft Teams, la aplicación de Android o la aplicación de iOS
- Teléfono Microsoft Teams versión 1449/1.0.94.2020051601 o posterior
  
Las cuentas de Teams de los agentes deben establecerse en el modo TeamsOnly. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas. Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

> [!TIP]
> Establecer **el modo de conferencia** **en Activado** es la opción recomendada.

> [!NOTE]
> El modo de conferencia no es compatible si las llamadas de teléfono se redirigen a la cola desde una puerta de enlace de enrutamiento directo habilitada para el enrutamiento basado en ubicación.
>
> El modo de conferencia no es compatible si las llamadas telefónicas se enrutan a la cola desde Skype Empresarial Server.
> 
> El modo de conferencia es necesario si los usuarios de Teams necesitan consultar o transferir llamadas con colas de llamadas.
>
> Los agentes pueden oír la música configurada en espera en cola durante un máximo de 2 segundos al unirse por primera vez a la llamada.


Una vez que haya seleccionado las opciones de respuesta de llamadas, seleccione el botón **Siguiente** en la parte inferior de la página **Agregar una cola de llamadas** .

# <a name="step-4-agent-selection"></a>[Paso 4: Selección de agente](#tab/agent-selection)

## <a name="step-4-select-your-agent-routing-options"></a>Paso 4: Seleccionar las opciones de enrutamiento del agente

**El método de enrutamiento** determina el orden en que los agentes reciben llamadas de la cola.

Elija una de estas opciones:

- **El enrutamiento de operador** hace una llamada a todos los agentes en la cola al mismo tiempo. El primer agente de llamada que tome la llamada la recibe.

- **El enrutamiento de serie** a todos los agentes de llamada uno por uno en el orden especificado en la **Llamar a** lista. Si un agente descarta o no realiza una llamada, la llamada llamará al siguiente agente. Esto se repetirá hasta que se recoja la llamada o se agota el tiempo de espera.

- **Distribución equilibrada** equilibra el enrutamiento de llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola. Este método de enrutamiento puede ser deseable en un entorno de ventas de entrada para garantizar la igualdad de oportunidades entre todos los agentes de llamadas.

- **Inactividad mayor** dirige cada llamada al agente que ha estado inactivo por más tiempo. Un agente se considera inactivo si su estado de presencia es Disponible. Los agentes cuyo estado de presencia no es Disponible no podrán recibir llamadas hasta que cambien su presencia a Disponible.

> [!TIP]
> Se recomienda establecer el **Método de enrutamiento** para **redondear robin** o **La inactividad más larga** .

> [!NOTE]
> Si la [grabación de cumplimiento](teams-recording-policy.md) está habilitada en los agentes, no se admite la combinación del **modo de conferencia** y el **enrutamiento de Attendant** . Si necesita usar el **modo conferencia**, seleccione **Enrutamiento en serie**, **Round robin** o **Longest idle** como **método de enrutamiento**. Si necesita usar el **enrutamiento de Attendant**, establezca **el modo de conferencia** en **Desactivado**.
>
> Cuando se usa La **más larga inactiva** y cuando hay menos llamadas en cola que los agentes disponibles, solo se presentan las llamadas de la cola a los dos primeros agentes inactivos más largos.
>
> Cuando se usa La **más larga inactiva**, puede haber ocasiones en que un agente recibe una llamada de la cola poco después de dejar de estar disponible, o un breve retraso en la recepción de una llamada de la cola después de estar disponible.
>
> La presentación de llamadas de la cola de llamadas a agentes puede entrar en conflicto con las restricciones de enrutamiento basado en ubicación. En este caso, el agente recibirá una llamada del sistema, pero no podrá responder a la llamada. Esta condición continuará hasta que otro agente esté disponible para responder a la llamada, el autor de la llamada cuelgue o se produzca la condición de tiempo de espera de la cola de llamadas.  

### <a name="presence-based-call-routing"></a>Enrutamiento de llamadas basado en presencia

**El enrutamiento de llamadas basado en** presencia usa el estado de disponibilidad de los agentes de llamadas para determinar si un agente debe incluirse en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado.

Los agentes de llamadas cuyo estado de disponibilidad está establecido en **Disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas. Los agentes cuyo estado de disponibilidad se establezca en cualquier otro estado se excluyen de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que el estado de disponibilidad vuelva a cambiar a **Disponible**.

Puede habilitar el **enrutamiento de llamadas basado en presencia** con cualquiera de los métodos de enrutamiento.

Si un agente opta por no recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas independientemente de cómo esté configurado su estado de disponibilidad.

> [!TIP]
> La configuración recomendada es establecer el **enrutamiento basado en** presencia **en activado** .

> [!NOTE]
> Cuando se selecciona **La inactividad más larga** como método de enrutamiento, se requiere un enrutamiento basado en presencia y se habilita automáticamente aunque el botón de alternancia de enrutamiento basado en presencia esté **Desactivado** y atenuado.
>
> Si el enrutamiento basado en presencia no está habilitado y hay varias llamadas en la cola, el sistema presentará estas llamadas simultáneamente a los agentes independientemente de su estado de presencia. Esta acción dará como resultado varias notificaciones de llamada a los agentes, especialmente si algunos agentes no responden a la llamada inicial que se les ha presentado.
>
> Al usar **el enrutamiento basado en** presencia, puede haber ocasiones en que un agente recibe una llamada de la cola poco después de dejar de estar disponible o un breve retraso en la recepción de una llamada de la cola después de estar disponible.
>
> Los agentes que usan el cliente de Skype Empresarial no se incluyen en la lista de enrutamiento de llamadas cuando está habilitado el enrutamiento basado en presencia. Si tiene agentes que usan Skype Empresarial, no habilite el enrutamiento de llamadas basado en presencia.

### <a name="call-agents-can-opt-out-of-taking-calls"></a>Los agentes de llamadas pueden dejar de realizar llamadas

Puede especificar si los agentes de llamadas pueden optar por no recibir llamadas o no.

Se recomienda activar **los agentes de llamadas para que no puedan realizar llamadas**.

### <a name="agent-alert-time"></a>Hora de alerta del agente

**Tiempo de alerta de agente** especifica qué tanto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.

> [!TIP]
> La configuración recomendada es establecer la **hora de alerta del agente** en un mínimo de **20 segundos** .

Una vez que haya seleccionado las opciones de enrutamiento de llamadas de su agente, seleccione el botón **Siguiente** en la parte inferior de la página **Agregar una cola de llamadas** .

# <a name="step-5-call-overflow"></a>[Paso 5: Desbordamiento de llamadas](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>Paso 5: Establecer cómo controlar el desbordamiento de llamadas

**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.

El valor predeterminado es 50, pero puede elegir un valor entre 0 y 200.

Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.

Puede elegir **desconectar** la llamada o **redirigirla** a cualquiera de los destinos de enrutamiento de llamadas.

Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola.

*Nuevo: los controles de **mensajes del sistema de omitir** correo de voz se exponen ahora al enrutamiento al correo de voz compartido, lo que también se aplica a las indicaciones **de Agregar un mensaje de saludo** .*

Para las transferencias externas, consulte [Requisitos previos](./plan-auto-attendant-call-queue.md#prerequisites) y [las transferencias de números de teléfono externos: detalles técnicos](create-a-phone-system-auto-attendant.md?tabs=additional-resources) para el formato de números.

> [!NOTE]
> Si el número máximo de llamadas se establece en 0, el mensaje de saludo no se reproducirá.

Una vez que haya seleccionado las opciones de administración de desbordamiento de llamadas, seleccione el botón **Siguiente** en la parte inferior de la página **Agregar una cola de llamadas** .

# <a name="step-6-call-timeout"></a>[Paso 6: Tiempo de espera de llamadas](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>Paso 6: Establecer cómo controlar los tiempos de espera de llamada

**Tiempo de espera de la llamada: tiempo máximo** especifica el tiempo máximo en que una llamada puede estar en espera en la cola antes de que se redirija o se desconecta.

Puede establecer un intervalo de entre 0 y 45 minutos.

Puede elegir **desconectar** la llamada o **redirigirla** a uno de los destinos de enrutamiento de llamadas.

Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola.

*Nuevo: los controles de **mensajes del sistema de omitir** correo de voz se exponen ahora al enrutamiento al correo de voz compartido, lo que también se aplica a las indicaciones **de Agregar un mensaje de saludo** .*

Para las transferencias externas, consulte [Requisitos previos](./plan-auto-attendant-call-queue.md#prerequisites) y [las transferencias de números de teléfono externos: detalles técnicos](create-a-phone-system-auto-attendant.md?tabs=additional-resources) para el formato de números.

Una vez que haya seleccionado las opciones de administración del tiempo de espera de llamadas, seleccione el botón **Enviar** en la parte inferior de la página **Agregar una cola de llamadas** .

---

## <a name="resources-for-complex-scenarios"></a>Recursos para escenarios complejos

### <a name="summary-of-recommended-call-queue-settings"></a>Resumen de la configuración recomendada de la cola de llamadas

Se recomienda la siguiente configuración:

- **Modo de conferencia** a **Activado**
- **Método de enrutamiento** a **distribución equilibrada** o **inactividad mayor**
- **Enrutamiento basado en presencia** a **Activado**
- **Tiempo de alerta del agente:** a un mínimo de **20 segundos**

### <a name="call-queue-feature-compatibility"></a>Compatibilidad de características de la cola de llamadas

|Característica                          |Teams Desktop<sup>1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Skype Empresarial |Teléfonos IP | Colas de llamadas estándar |Colas de llamadas basadas en canales | Comentario |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**Métodos de enrutamiento de agente**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |v                         |v         |v               |v    |v         |v                     |v                         |*Predeterminado*     |
|`Longest Idle`<sup>3</sup>       |v                         |v         |v               |N    |v         |v                     |v                         |*Recomendado* |
|`Round Robin`                    |v                         |v         |v               |v    |v         |v                     |v                         |*Recomendado* |
|`Serial`                         |v                         |v         |v               |v    |v         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**Opciones de enrutamiento de agente**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|v                      |v         |v               |N    |v         |v                     |v                         |*Predeterminado* |
|`Agents can Opt-out`<sup>10</sup> |v                       |v         |v               |Y<sup>7</sup>|Y<sup>7</sup>|v          |v                         |*Predeterminado*     |
|**Modos de transferencia**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |v                         |v         |v               |N    |Y<sup>6</sup>|v                  |v                         |*Predeterminado* |
|`Transfer Mode`                  |v                         |v         |v               |v    |v         |v                     |v                         |   |
|**Llamadas colaborativas**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |v                       |N         |N               |N    |N         |n/a                   |Y<sup>8</sup>             |   |
|**Identificador dinámico de llamadas**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |v                         |v         |v               |N    |N         |Y                     |n/a                       |   |
|`Channel based call queue`       |v                         |n/a       |n/a             |n/a  |n/a       |n/a                   |v                         |   |
|**Métodos de conectividad RTC**    |                          |          |                |     |          |                      |                          |Vea la Nota 9   |
|`Calling Plans`                  |v                         |v         |v               |v    |v         |v                     |v                         |   |
|`Direct Routing`                 |v                         |v         |v               |N    |Y         |Y<sup>6</sup>         |v                         |   |
|`Operator Connect`               |v                         |v         |v               |     |v         |Y<sup>6</sup>         |v                         |   |
|**Misceláneos**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |v                 |N         |v               |v    |          |v                     |v                         |              |

#### <a name="notes"></a>Notas

1. Cliente de Microsoft Teams windows, cliente de Microsoft Teams para Mac, Microsoft Teams en infraestructura de escritorio virtualizada.
2. Aplicación de Microsoft Teams para iPhone, aplicación de Microsoft Teams para Android.
3. Si selecciona Longest Idle para el método de enrutamiento del agente, se habilitará automáticamente el enrutamiento basado en presencia.
4. Solo puede establecer el orden al agregar usuarios individuales como parte de las colas de llamadas estándar. Cuando se usa una lista de distribución o un canal de Teams, el orden será alfabético.
5. El modo de conferencia no es compatible si las llamadas de teléfono se redirigen a la cola desde una puerta de enlace de enrutamiento directo habilitada para el enrutamiento basado en ubicación.
6. solo Teléfono Microsoft Teams.
7. A través de la página del Portal de configuración de usuario en [https://aka.ms/vmsettings](https://aka.ms/vmsettings).
8. Solo se admiten canales públicos.
9. Los operadores automáticos y las colas de llamadas no pueden transferir llamadas entre métodos de conectividad RTC.
10. Para GCCH/DOD, solo disponible a través del Portal de configuración de usuario en:
- GCCH: [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)
- DOD: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)

### <a name="supported-clients"></a>Clientes compatibles

Los siguientes clientes son compatibles con agentes de llamada en una cola de llamadas:

- Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
- Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
- Todos los modelos de teléfonos IP compatibles con Microsoft Teams. Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
- Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)
- Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
- Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
- Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)
- Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
- Cliente de Microsoft Teams para Mac
- Microsoft Teams en [infraestructura de escritorio virtualizada](teams-for-vdi.md) (Windows Virtual Desktop, Citrix y VMware)
- Aplicación Microsoft Teams para iPhone
- Aplicación Microsoft Teams para Android

  > [!NOTE]
  > Las colas de llamadas a las que se les asigna un número de enrutamiento directo no admiten clientes de Skype Empresarial, clientes Lync o teléfonos IP de Skype Empresarial como agentes. El cliente de Teams solo es compatible con un [modo de existencia única de Teams](setting-your-coexistence-and-upgrade-settings.md).

### <a name="call-queue-diagnostic-tool"></a>Herramienta de diagnóstico de cola de llamadas

Si es administrador, puede usar la siguiente herramienta de diagnóstico para validar que una cola de llamadas pueda recibir llamadas:

1. Seleccione **Ejecutar pruebas** a continuación. Esto rellenará el diagnóstico en el Centro de administración de Microsoft 365.

   > [!div class="nextstepaction"]
   > [Ejecutar pruebas: Cola de llamadas de Teams](https://aka.ms/TeamsCallQueueDiag)

2. En el panel Ejecutar diagnóstico, escriba la cuenta de recurso en el campo **Nombre de usuario o Email** y, después, seleccione **Ejecutar pruebas**.

3. Las pruebas devolverán los mejores pasos siguientes para abordar cualquier inquilino, directiva y configuración de cuenta de recursos para validar que la cola de llamadas pueda recibir llamadas.

### <a name="related-topics"></a>Temas relacionados

[Esto es lo que obtienes con Teléfono Microsoft Teams](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
