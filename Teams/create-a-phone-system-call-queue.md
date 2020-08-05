---
title: Crear una cola de llamada
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Aprenda a configurar el sistema telefónico para las colas de llamadas en nube con Microsoft Teams, que proporcionan un mensaje de saludo, mantener música, redirigir llamadas y otras características.
ms.openlocfilehash: f0631eece5b8f67cd93c46b34c56bb2283826c3f
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46556665"
---
# <a name="create-a-cloud-call-queue"></a>Crear una cola de llamadas en la nube

Las colas de llamadas en nube pueden proporcionar:

- Un mensaje de bienvenida.
- Música que se reproduce mientras los usuarios se mantienen a la espera.
- Redireccionamiento de llamadas a agentes de llamadas en listas de distribución habilitadas para correo electrónico y grupos de seguridad.
- Establecer distintos parámetros, como el tamaño máximo de la cola, el tiempo de espera y las opciones de administración de llamadas.
- Buzón de voz compartido para que las personas que llaman dejen un mensaje para una organización.

No asocia directamente un número de teléfono a una cola de llamadas, sino que el número de teléfono está asociado a una [cuenta de recursos](manage-resource-accounts.md). Una cola de llamadas puede marcarse directamente o tener acceso a la misma mediante una selección en un operador automático.

La persona que llama escucha la música mientras está en espera y la llamada se conecta a los agentes de llamadas con el orden FIFO ( *primero en salir* ).

Todas las llamadas de la cola se envían a los agentes mediante uno de los siguientes métodos:

- Con el enrutamiento del operador, la primera llamada de la cola suena a todos los agentes al mismo tiempo.
- Con el enrutamiento en serie, la primera llamada de la cola suena una por una por todos los agentes de llamadas.
- Con el enrutamiento más largo de inactividad, el agente de llamada que ha estado inactivo recibe la siguiente llamada disponible. El tiempo de inactividad se define como la cantidad de tiempo que el estado de presencia de un agente de llamada se establece en **disponible** o **ausente** (si hay menos de 10 minutos), en el momento de la llamada. Si la presencia de un agente de llamada está **ausente** durante más de 10 minutos, se restablecerá el temporizador de inactividad.
- Con la operación por turnos, el enrutamiento de las llamadas entrantes está equilibrado, de modo que cada agente de llamadas obtiene el mismo número de llamadas de la cola.

Puede configurar las opciones de administración de llamadas, como la participación en el agente, la opción de enrutamiento basado en la presencia, el tiempo de espera de llamada y las opciones de tiempo de espera de la llamada con cualquiera de los métodos anteriores.

Solo una notificación de llamada entrante (para la llamada al principio de la cola) a la vez va a los agentes de llamadas. Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.

> [!NOTE]
> Este artículo se aplica a Microsoft Teams y a Skype empresarial online.

## <a name="step-1--get-started"></a>Paso 1: introducción

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:

- Se necesita una cola de llamadas para tener una cuenta de recursos asociada. Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .
- Cuando asigne un número de teléfono a una cuenta de recursos, ahora puede usar la [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md)del sistema telefónico para el coste. El sistema telefónico permite números de teléfono en el nivel de la organización para su uso con los servicios de cola de llamadas y los operadores automáticos de bajo costo.

  > [!NOTE]
  > Los números del servicio de enrutamiento directo para colas de llamadas solo se admiten para usuarios y agentes de Microsoft Teams.

> [!NOTE]
> Para redirigir las llamadas a las personas de su organización que están conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas a Microsoft 365 o de Office 365. Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute: ' Set-CsUser-Identity "amos Marble"-EnterpriseVoiceEnabled $true.

- Para obtener más información sobre los planes de llamadas, consulte planes de llamadas y [sistemas telefónicos](calling-plan-landing-page.md) y [planes de llamadas para Microsoft 365 u Office 365](calling-plans-for-office-365.md).

- Solo puede asignar colas de llamadas en la nube números de teléfono de pago y gratuitos que recibió en el **centro de administración de Microsoft Teams** o transferidos desde otro proveedor de servicios. Para los números de servicio gratuitos se requieren créditos de comunicaciones.

    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.

- Los siguientes clientes son compatibles con los agentes de llamadas asociados a una cola de llamadas en la nube:

  - Cliente de escritorio de Skype empresarial 2016 (versiones de 32 y 64 bits)
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
  - Todos los modelos de teléfono IP compatibles con Microsoft Teams. Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)
  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)
  - Cliente de Windows de Microsoft Teams (versiones de 32 y 64 bits)
  - Cliente de Microsoft Teams para Mac
  - Aplicación Microsoft Teams para iPhone
  - Aplicación Microsoft Teams para Android

    > [!NOTE]
    > Las colas de llamadas a las que se asigna un número de enrutamiento directo no son compatibles con clientes de Skype empresarial, clientes de Lync o teléfonos IP de Skype empresarial como agentes.

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>Paso 2: obtener o transferir números de teléfono de pago o gratuitos

Antes de crear y configurar las colas de llamadas, debes obtener o transferir tus números de teléfono de pago o gratuitos existentes. Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Después de recibir los números de teléfono de pago o gratuitos, aparecerán en **Microsoft Teams admin center**  >  **Voice**  >  **los números de teléfono**del centro de administración de Microsoft Teams. Los números gratuitos se mostrarán con un **tipo** de servicio de número **(gratuito)**.

> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio. En su lugar, vaya a [administrar números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver cómo hacerlo desde fuera de los Estados Unidos.

Cuando configure varios operadores automáticos, normalmente asignaría un número de teléfono a la cuenta de recursos del operador automático principal. Las cuentas de recursos asociadas a los operadores automáticos anidados o a las colas de llamadas a menudo no necesitan números de teléfono. Ese operador automático puede dirigir a las personas que llaman a las colas de llamadas o a los operadores automáticos anidados incluso si no tienen un número de teléfono. En esos casos, puede crear todos los operadores automáticos y colas de llamadas en el sistema sin asignar opciones de marcado y, después, editar la configuración más adelante. Debe existir una cola de llamadas o un operador automático para establecerla como una opción de menú.

## <a name="step-3--create-a-call-queue"></a>Paso 3: crear una cola de llamadas

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Cada cola de llamadas debe tener una cuenta de [recursos](manage-resource-accounts.md)asociada. Debe crear primero la cuenta de recursos y, a continuación, asociarla a la cola de llamadas.

### <a name="use-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

En el **centro de administración de Microsoft Teams**, colas de llamadas de **voz**  >  **Call queues**y, a continuación, haga clic en **+ Agregar nuevo**:

### <a name="set-the-display-name-and-resource-account"></a>Establecer el nombre para mostrar y la cuenta de recursos

![Captura de pantalla de una nueva cola de llamadas con llamadas numeradas](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![El icono del número 1 hace referencia a una llamada en el nombre de la captura de pantalla anterior ](media/teamscallout1.png)
 **Name** escriba un nombre descriptivo para la cola de llamadas. Este nombre es obligatorio y puede contener hasta 64 caracteres, incluidos los espacios.

 Este nombre se muestra en la notificación de la llamada entrante.

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior ](media/teamscallout2.png)
 **Agregar cuentas** Seleccione una cuenta de recursos. Todas las colas de llamadas deben tener una cuenta de recursos. No es necesario que las cuentas de recursos tengan un número de teléfono gratuito o gratuito.

Si no hay ninguna lista, obtenga números de servicio y asígnelos a una cuenta de recursos antes de crear la cola de llamadas, como se describe anteriormente. Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md). Consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) para obtener información específica sobre cómo asignar un número de teléfono.

> [!NOTE]
> Si quiere o necesita asignar un **dominio** , lo asignaría a la cuenta de recursos para la cola de llamadas.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![captura de pantalla de las opciones de saludo y música con llamadas numeradas](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![El icono del número 1, hace referencia a una llamada en la captura de pantalla anterior, ](media/teamscallout1.png)
 **saludo** el saludo opcional que se reproduce para las personas que llaman al número de la cola de llamadas.

Puede cargar un archivo de audio (en formato. wav,. mp3 o. WMA).

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior ](media/teamscallout2.png)
 **música en espera** puede usar la música predeterminada en espera con la cola de llamadas. También puede cargar un archivo de audio en formato. wav, MP3 o. WMA para usarlo como música personalizada en espera.

* * *

### <a name="select-the-call-answering-options"></a>Selecciona las opciones de contestador automático

![Captura de pantalla de las opciones de contestador automático](media/teams-cq-call-answering-options.png)

![El icono del número 1, hace referencia a una llamada en la captura de pantalla anterior de los ](media/teamscallout1.png)
 **agentes y grupos** para agregar agentes individuales directamente, sin agregarlos a un grupo, haga clic en **Agregar usuarios**. Coloca agentes individuales en el orden en que quieras que reciban la llamada. Puedes añadir hasta 20 agentes individuales (para añadir más de 20, ponerlos en un grupo).

Las llamadas se enrutan primero a los agentes individuales y luego a los agentes en grupos. 

Puede seleccionar hasta 200 agentes de llamadas que pertenecen a cualquiera de las siguientes listas o grupos de correo:

- Grupo de Microsoft 365
- Grupo de seguridad
- Lista de distribución

Los agentes de llamadas seleccionados deben ser uno de los siguientes: 

- Usuarios en línea con una licencia de sistema telefónico y la telefonía IP empresarial habilitada
- Usuarios en línea con un plan de llamadas
- Usuarios locales de Skype empresarial Server

  > [!NOTE]
  > Esto también se aplica si desea redirigir las llamadas a las personas de su organización que están conectadas. Estas personas deben tener una licencia de sistema telefónico y la telefonía IP empresarial habilitada *o* tener un plan de llamadas. Para obtener más información, vea [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [asignar licencias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)o [el plan de llamadas es adecuado para usted](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) .

   Para habilitar un agente para telefonía IP empresarial, puede usar Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Usuarios con una licencia de sistema telefónico o un plan de llamadas que se agregan a un grupo de Microsoft 365, una lista de distribución habilitada para correo o un grupo de seguridad. Al agregar un agente en una lista de distribución o un grupo de seguridad como agente de la cola de llamadas, puede demorar hasta tres horas en llegar a la primera llamada. Una lista de distribución o un grupo de seguridad recién creados puede demorar 48 horas en estar disponible para usarse con las colas de llamadas. Los grupos de Microsoft 365 recién creados están disponibles casi de inmediato.

- Si los agentes usan la aplicación Microsoft Teams para las llamadas de la cola de llamadas, deben estar en modo TeamsOnly.

![El icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior en el modo de conferencia en ](media/teamscallout2.png)
 **modo** de conferencia, reduce significativamente la cantidad de tiempo que tarda una persona que se conecte a un agente, después de que el agente acepte la llamada. Si tiene más de una cola de llamadas, puede habilitar el modo de conferencia en algunas o en todas las colas de llamadas. habilitar o deshabilitar el modo de conferencia en una cola de llamadas no afecta a las demás colas de llamadas.

El modo de conferencia está deshabilitado de forma predeterminada, pero se puede habilitar en cualquier momento si se cumplen los siguientes requisitos:

- Los agentes añadidos a la cola de llamadas deben usar uno de los siguientes clientes:
  - La versión más reciente del cliente de escritorio de Microsoft Teams, la aplicación Android o la aplicación iOS
  - Microsoft Teams Phone versión 1449/1.0.94.2020051601 o posterior
- Las cuentas de los agentes de Teams deben establecerse en modo de solo Teams

> [!IMPORTANT]
> Si los requisitos del agente anteriores no se cumplen y el modo de conferencia está habilitado en una cola de llamadas, los agentes que no cumplan con los requisitos no se incluyen en la lista de enrutamiento de llamadas. Los agentes que no se encuentren en la lista de enrutamiento de llamadas no recibirán llamadas. Si tiene agentes que no cumplen con los requisitos del agente anteriores, no habilite el modo de conferencia en la cola de llamadas.

Después de habilitar el modo de conferencia en una cola de llamadas, las llamadas se beneficiarán del tiempo de conexión más rápido si se reciben mediante uno de los siguientes métodos:

- Llamadas VoIP desde otro cliente de escritorio de Microsoft Teams
- Plan de llamadas RTC
- Enrutamiento directo de llamadas RTC

La mayoría de las llamadas se reciben a través de uno de los métodos mencionados anteriormente. Si se recibe una llamada a través de otro método (como una llamada de VoIP desde un cliente de Skype empresarial), la llamada se agregará a la cola de llamadas, pero no se beneficiará de la conexión más rápida.

> [!NOTE]
> El modo de conferencia no admite el uso ocupado en ocupado. Es posible que los agentes de las llamadas a colas que no sean de llamadas sigan apareciendo con una llamada en la cola de llamadas si el enrutamiento basado en presencia no está habilitado.


![Icono del número 3, que hace referencia a una llamada en el método de enrutamiento de captura de pantalla anterior, ](media/teamscallout3.png)
 **Routing method** puede elegir entre **operador**, **serie**, más **tiempo de inactividad**o por **turnos** como método de distribución. Todas las colas de llamadas nuevas y existentes tienen el enrutamiento de operador seleccionado de forma predeterminada. Cuando se usa el enrutamiento del operador, la primera llamada en la cola llama a todos los agentes de llamadas al mismo tiempo. El primer agente de llamadas que atiende la llamada recibe la llamada.

- El **enrutamiento del operador** hace que la primera llamada de la cola suene a todos los agentes de llamadas al mismo tiempo. El primer agente de llamadas que atiende la llamada recibe la llamada.
- El **enrutamiento serie** llama a todos los agentes de llamadas de uno en uno, desde el principio de la lista de agentes de llamadas. Los agentes no se pueden pedir dentro de la lista de agentes de llamadas. Si un agente descarta o no atiende una llamada, la llamada sonará al próximo agente y probará con todos los agentes hasta que se seleccione o agote el tiempo de espera.
- Rutas **inactivas más largas** la siguiente llamada disponible al agente de llamada que ha estado inactiva el tiempo más largo. El tiempo de inactividad se define como la cantidad de tiempo que el estado de presencia de un agente de llamada se establece en **disponible** o **ausente** (si hay menos de 10 minutos), en el momento de la llamada. Si la presencia de un agente de llamada se establece en **ausente** durante más de 10 minutos, se restablecerá el temporizador de inactividad. Los Estados de presencia de los usuarios se consultan cada minuto.

    Es importante saber que habilitar esta configuración obliga a habilitar el **enrutamiento basado en presencia** .

    > [!IMPORTANT]
    > Los agentes que usen el cliente de Skype empresarial no recibirán llamadas cuando la configuración de inactividad más larga esté habilitada. Si tienes agentes que usan Skype o Business, no habilites esta configuración.
- El enrutamiento **Round Robin** de equilibra las llamadas entrantes para que cada agente de llamadas obtenga el mismo número de llamadas de la cola. Esto puede ser conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.

![El icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior, el enrutamiento basado en presencia ](media/teamscallout4.png)
 **Presence-based routing** usa el estado de disponibilidad de los agentes de llamadas para determinar si un agente debería estar incluido en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado. Los agentes de llamadas cuyo estado de disponibilidad esté establecido en **disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas. Los agentes cuyo estado de disponibilidad esté establecido en cualquier otro Estado se excluyan de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que su estado de disponibilidad cambie de nuevo a **disponible**.  

Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.

Si un agente opta por recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas, independientemente del valor de su estado de disponibilidad en. 

> [!IMPORTANT]
> Los agentes que usan el cliente de Skype empresarial no se incluyen en la lista de enrutamiento de llamadas cuando el enrutamiento basado en presencia está habilitado, independientemente de su estado de disponibilidad. Los agentes que no se encuentren en la lista de enrutamiento de llamadas no recibirán llamadas. Si tiene agentes que usan Skype empresarial, no habilite el enrutamiento de llamadas basado en presencia.

### <a name="select-an-agent-opt-out-option"></a>Seleccionar una opción de cancelación de la suscripción

![Captura de pantalla de las opciones de cancelación del agente, con llamadas numeradas](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![El icono del número 1 hace referencia a una llamada en el agente de captura de pantalla anterior que ](media/teamscallout1.png)
 **puede optar por recibir llamadas** puede optar por permitir que los agentes de la cola de llamadas no puedan tomar llamadas de una cola determinada habilitando esta opción.

Al habilitar esta opción, todos los agentes de esta cola iniciarán o dejarán de recibir llamadas de esta cola de llamadas. Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).

Para acceder a la opción de cancelación de la suscripción, los agentes pueden:

 1. Abra **Opciones** en el cliente de Skype for Business de su escritorio.
 2. En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.
 3. En la página Configuración de usuario, haga clic en **colas de llamadas**y, a continuación, desactive las casillas para anular las colas.

    > [!NOTE]
    > Los agentes que usen aplicaciones o extremos que no sean de Skype empresarial pueden acceder a la opción de cancelación de la suscripción en el portal de configuración de usuario [https://aka.ms/cqsettings](https://aka.ms/cqsettings) .
    >
    > Si los agentes se encuentran en clientes de escritorio de Microsoft Teams, pueden dejar de participar usando la configuración de la llamada. 

![Icono del número 2, que hace referencia a una llamada en la ](media/teamscallout2.png)
 **configuración de alerta del agente** de captura de pantalla anterior

Esto define la duración de un agente de notificación de una llamada antes de que los métodos de enrutamiento de serie o de turnos pasen al siguiente agente.

La configuración predeterminada es de 30 segundos, pero se puede establecer hasta 3 minutos.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Establecer las opciones de desbordamiento de llamadas y administración de tiempo de espera

![Captura de pantalla de las opciones de control de desbordamiento con llamadas numeradas](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior ](media/teamscallout1.png)
 **llamadas máximas en la cola** use esta configuración para establecer las llamadas máximas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200. Cuando se alcanza este límite, la llamada se maneja de la forma que estableces en la configuración **cuando se alcanza el número máximo de llamadas** , a continuación.

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior ](media/teamscallout2.png)
 **cuando se alcanza el número máximo de llamadas** cuando la cola de llamadas alcanza su tamaño máximo (establecido mediante las **llamadas máximas en la configuración de la cola** ), puede elegir qué sucede con las llamadas entrantes nuevas.

- **Desconectar** La llamada se desconectará.
- **Redirigir a** Si elige esta opción, seleccione una de las siguientes opciones:

  - **Persona en la organización** Un usuario en línea con una licencia de sistema telefónico y está habilitado para telefonía IP empresarial o tiene un plan de llamadas.

  - **Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.

  - **Número de teléfono externo** Elija esta opción para transferir a la persona que llama a un número de teléfono externo que especifique. Tenga en cuenta lo siguiente:

    - La cuenta de recursos asociada a la aplicación que hace que la transferencia de RTC destaque debe tener un número de teléfono y se le debe asignar una licencia de sistema de teléfono virtual. No se admiten licencias de sistema telefónico. Además, la cuenta de recursos debe tener uno de los siguientes elementos:
        - Para una cuenta de recursos con un número de plan de llamadas, asigne una licencia de [plan de llamadas](calling-plans-for-office-365.md) .
        - Para una cuenta de recursos con un número de enrutamiento directo, asigne una [Directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md).
    - El número de teléfono saliente que se muestra se determina de la siguiente manera:
        - Para los números de planes de llamadas, se muestra el número de teléfono de la persona que llama original.
        - Para los números de enrutamiento directos, el número enviado se basa en la configuración P-asserted-Identity (PAI) en SBC, de la siguiente manera:
            - Si se establece en deshabilitado, se muestra el número de teléfono de la persona que llama original. Esta es la configuración predeterminada y recomendada.
            - Si se establece en habilitado, se muestra el número de teléfono de la cuenta del recurso.
    - No se admiten las transferencias entre los troncos del plan de llamadas y los troncos de enrutamiento directos.
  - **Buzón de voz** Seleccione el grupo de Microsoft 365 que contiene los usuarios de su organización que necesitan obtener acceso al buzón de voz recibido por esta cola de llamadas y, a continuación, seleccione una de las siguientes opciones:
      - **Reproducir un archivo de audio** Si elige esta opción, seleccione **Cargar archivo** para cargar un mensaje de bienvenida grabado. La grabación no puede tener más de 5 MB. 
      - **Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que el sistema Lea (hasta 1000 caracteres). Por ejemplo, puedes escribir "Lamentamos que no podamos hacer tu llamada en este momento. Deja el nombre, el número de teléfono y el motivo de la llamada después del pitido.

      Active la transcripción si quiere habilitar la transcripción de voz a texto de los mensajes de voz.

      Los mensajes de voz se envían al grupo de Microsoft 365 que especifique. Para acceder a los mensajes de voz, los miembros del grupo pueden abrirlos desplazándose al grupo en Outlook.

* * *

![El icono del número 3 hace referencia a una llamada en la captura de pantalla anterior ](media/teamscallout3.png)
 **tiempo de espera de llamada: tiempo de espera máximo** también puede decidir cuánto tiempo puede estar en espera una llamada en la cola antes de que se agote el tiempo de espera y que deba redirigirse o desconectarse. El lugar donde se redirige se basa en el modo en que se establece la configuración **cuando la llamada supera el tiempo de espera** . Puede establecer un intervalo de entre 0 y 45 minutos.

El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos. Esto permite manipular el flujo de llamadas con una granularidad más fina. Por ejemplo, puede especificar que las llamadas no contestadas por un agente en un plazo de 30 segundos vayan a un operador automático de búsqueda de directorios.

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior ](media/teamscallout4.png)
 **cuando la llamada supera el tiempo** de espera cuando la llamada alcanza el límite establecido en el valor de **tiempo de espera de una llamada en la cola** , puede elegir qué sucede con la llamada:

- **Desconectar** La llamada se desconectará.
- **Redirigir esta llamada a** Si elige esta opción, tiene estas opciones:
  - **Persona en la organización** Un usuario en línea con una licencia de sistema telefónico y habilitado para telefonía IP empresarial o para tener planes de llamadas.

  - **Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada con una cola de llamadas o un operador automático que ya haya creado.

  - **Número de teléfono externo** Elija esta opción para transferir a la persona que llama a un número de teléfono externo que especifique. Tenga en cuenta lo siguiente:

    - La cuenta de recursos asociada a la aplicación que hace que la transferencia de RTC destaque debe tener un número de teléfono y se le debe asignar una licencia de sistema de teléfono virtual. No se admiten licencias de sistema telefónico. Además, la cuenta de recursos debe tener uno de los siguientes elementos:
        - Para una cuenta de recursos con un número de plan de llamadas, asigne una licencia de [plan de llamadas](calling-plans-for-office-365.md) .
        - Para una cuenta de recursos con un número de enrutamiento directo, asigne una [Directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md).
    - El número de teléfono saliente que se muestra se determina de la siguiente manera:
        - Para los números de planes de llamadas, se muestra el número de teléfono de la persona que llama original.
        - Para los números de enrutamiento directos, el número enviado se basa en la configuración P-asserted-Identity (PAI) en SBC, de la siguiente manera:
            - Si se establece en deshabilitado, se muestra el número de teléfono de la persona que llama original. Esta es la configuración predeterminada y recomendada.
            - Si se establece en habilitado, se muestra el número de teléfono de la cuenta del recurso.
    - No se admiten las transferencias entre los troncos del plan de llamadas y los troncos de enrutamiento directos.
    - **Buzón de voz** Seleccione el grupo de Microsoft 365 que contiene los usuarios de su organización que necesitan obtener acceso al buzón de voz recibido por esta cola de llamadas y, a continuación, seleccione una de las siguientes opciones:
      - **Reproducir un archivo de audio** Si elige esta opción, seleccione **Cargar archivo** para cargar un mensaje de bienvenida grabado. La grabación no puede tener más de 5 MB.
      - **Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que el sistema Lea (hasta 1000 caracteres). Por ejemplo, puedes escribir "Lamentamos que no podamos hacer tu llamada en este momento. Deja el nombre, el número de teléfono y el motivo de la llamada después del pitido.

      Active la transcripción si quiere habilitar la transcripción de voz a texto de los mensajes de voz.

      Los mensajes de voz se envían al grupo de Microsoft 365 que especifique. Para acceder a los mensajes de voz, los miembros del grupo pueden abrirlos desplazándose al grupo en Outlook.

## <a name="change-caller-id-for-outbound-calls"></a>Cambiar la identificación de llamadas para llamadas salientes

Para proteger la identidad de un agente de llamada, cambie la identificación de llamadas para llamadas salientes a una cola de llamadas, operador automático o cualquier número de servicio con el cmdlet **New-CsCallingLineIdentity** como en el siguiente ejemplo:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplique la Directiva al usuario con el cmdlet **Grant-CallingLineIdentity** como en el siguiente ejemplo: 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Para obtener más información, consulte [cómo se puede usar la identificación de llamadas en su organización](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

También puede usar Windows PowerShell para crear y configurar colas de llamadas. Estos son los cmdlets que usas para administrar una cola de llamadas.

- [Nuevo: CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Microsoft Teams con un único punto de administración. Puede simplificar su trabajo diario cuando tenga que hacer varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en el centro de administración de Microsoft Teams cuando realiza cambios para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Administrar Microsoft 365 u Office 365 con Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nuevo: CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
