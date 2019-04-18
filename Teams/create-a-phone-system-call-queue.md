---
title: Crear una cola de llamada
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar el sistema telefónico para las colas de llamadas en la nube para dar un saludo, música en espera, organizativas y redirigir las llamadas para llamar a los agentes en las listas de distribución y grupos de seguridad. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: da178761658460812bc1d0330f3540be43c3e6e6
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914647"
---
# <a name="create-a-cloud-call-queue"></a>Crear una cola de llamada de nube

Colas de llamada de nube incluyen el saludo que se usa cuando alguien llama a un número de teléfono para su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponibles controlar la llamada mientras las personas que son de llamada escucha música en espera. Puede crear una o varias colas de llamadas para su organización.
  
Pueden proporcionar las colas de llamada de nube:
  
- Un mensaje de saludo empresarial.
- Música que se reproduce mientras los usuarios se mantienen a la espera.
- El redireccionamiento de llamadas para llamar a los agentes en las listas de distribución habilitados para correo y grupos de seguridad.
- Realizar la configuración de tamaño máximo de la cola de llamadas, tiempo de espera y las opciones de administración de llamadas.

Cuando alguien llama a un número de teléfono que está asociado con una cola de llamadas a través de una [cuenta de recurso](manage-resource-accounts.md), escuchará un saludo inicial (si se configura cualquiera) y, a continuación, se coloca en la cola y espere a que el siguiente agente de llamada disponibles. La persona que llama escuchará música mientras están en espera en espera y las llamadas se ofrecerán a los agentes de llamada en orden *Primero en ENTRAR, primero en salir* (FIFO).
  
Todas las llamadas en espera en la cola se distribuirá mediante uno de los métodos siguientes:
  
- Con el operador de enrutamiento, la primera llamada en la cola sonarán a todos los agentes al mismo tiempo.
- Con el enrutamiento en serie, la primera llamada de la cola llamará a todos los agentes uno a uno.
- Operación por turnos, el enrutamiento de las llamadas entrantes se equilibradas de modo que cada agente de llamada obtendrá el mismo número de llamadas de la cola.

    > [!NOTE]
    > No se llamará a los agentes de llamadas que están **Sin conexión**, han establecido su presencia en **No molestar** o han decidido quedar fuera de la cola de llamadas.
  
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.

> [!NOTE]
> En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.

## <a name="step-1---get-started"></a>Paso 1: Introducción

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
- Una cola de llamada es necesario tener una cuenta de recurso asociado. Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .
- Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).
- Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).
- Sólo debe obtener licencia para las cuentas de recursos con un número de teléfono que se les haya asignado. En una cola de llamada o de operador automático anidados, no es necesario para el resto de los operadores automáticos de licencia o colas de llamadas si no tienen números de teléfono asociados con ellos. 

> [!NOTE] 
> Operador automático de los números de servicio de enrutamiento directos para y colas de llamada se admiten para los agentes y los usuarios de Microsoft Teams sólo en el momento.

> [!NOTE] 
> Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.

> [!NOTE]
> Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365. Vea [Asignar Skype para licencias de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información acerca de planes de llamada de Office 365, vea [sistema telefónico y llamar a los planes](calling-plan-landing-page.md) y [Llamar a los planes de Office 365](calling-plans-for-office-365.md).

- Sólo se pueden asignar números de teléfono gratuito de servicio que se obtuvo en el **Centro de administración de equipos de Microsoft** o se transfiere desde otro proveedor de servicios a las colas de llamadas en la nube y de pago. Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.

    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos.
  
- Cuando se va a distribuir las llamadas entrantes de una cola de llamada en la nube, estos clientes son compatibles para agentes de llamada:

  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)

  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)

  - Todos los modelos de teléfono IP compatible con Microsoft Teams. Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)

  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)

  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)

  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)

  - Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)

  - Cliente de Microsoft Teams para Mac

  - Aplicación Microsoft Teams para iPhone

  - Aplicación Microsoft Teams para Android

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Paso 2: obtener o transferir números de servicio de pago o gratuitos

Antes de crear o configurar una cola, tendrá que obtener sus números de servicio de pago o gratuitos, o transferir unos existentes. Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**. Para obtener sus números de servicio, vea [los números de teléfono del servicio de obtención](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) o si desea transferir un número de servicio existente, vea [los números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio. Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.

Si también está configurando operadores automáticos, es posible que sólo debe asignar a un número de teléfono a la cuenta del recurso del operador automático principal, y, a continuación, hacer que los autores de llamadas directas a la cola de llamada. Si ese es el caso, la cola de llamadas se debe crearse antes de poder crear una opción en el operador automático de que selecciona la cola de llamada.
  
## <a name="step-3---create-a-new-call-queue"></a>Paso 3: crear una nueva cola de llamada

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Cada cola de llamada es necesario tener asociado a una [cuenta del recurso](manage-resource-accounts.md). Debe crear la cuenta del recurso en primer lugar, a continuación, se puede asociar a la cola de llamada.

### <a name="using-the-microsoft-teams-admin-center"></a>Desde el centro de administración de Microsoft Teams

En el **Centro de administración de equipos de Microsoft**, **voz** >  **colas de llamadas**, a continuación, haga clic en **+ Agregar nuevo**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Establecer la llamada de cola para mostrar recursos y nombre de cuenta

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Número 1](media/sfbcallout1.png)
**nombre** escriba un nombre para mostrar descriptivo para la cola de llamada. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.

 Este nombre se mostrará en la notificación de la llamada entrante.

* * *

![Número 2](media/sfbcallout2.png)

**Agregar cuentas** Seleccione una cuenta de recurso. La cuenta del recurso puede o no puede estar asociada con un teléfono de pago de servicio o el número de teléfono gratuito de la cola de llamadas, pero cada cola llamada requiere una cuenta de recurso asociado.

Si no existe ninguno en la lista, debe obtener los números de servicio y asignarlos a una cuenta de recursos con el para poder crear esta cola de llamadas, tal y como se ha descrito anteriormente. Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Debe crear una cuenta de recurso tal como se describe en [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) , si desea que la cola de llamada tiene un número de teléfono asociado.

> [!NOTE]
> Si desea o necesita asignar un **dominio** sería hacerlo mediante la asignación a la cuenta del recurso de la cola de llamada.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

**Saludo**: este campo es opcional. Este es el saludo que se reproduce para las personas que llamar el número de llamada de cola.

Puede cargar un archivo de audio (formatos .wav,. mp3 o .wma).

![Número 2](media/sfbcallout2.png)

**Música en espera** Puede usar el valor predeterminado de música en espera que se proporcionan con la cola de llamadas, o puede cargar un archivo de audio en los formatos WAV, mp3 o .wma que se utilizará como su personalizado de música en espera.

* * *

### <a name="select-the-call-answering-options"></a>Seleccione el contestador automático opciones

![Muestra las opciones del método de distribución de la llamadas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

Puede seleccionar a un máximo de 200 agentes de llamada que pertenecen a grupos o listas de correo especificadas. Los agentes de llamada deben ser:

- Un usuario en línea con una licencia de **Sistema telefónico** y habilitado para Enterprise Voice o con un Plan de llamada.

  > [!NOTE]
  > Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o disponer de un Plan de llamada. Vea [Asignar Skype para licencias de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).

 Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Usuarios en línea con una licencia de **Sistema telefónico** y un Plan de llamadas que se agregan a un grupo de Office 365, una lista de distribución habilitada para correo o un grupo de seguridad. El nuevo agente agregado a una lista de distribución o a un grupo de seguridad podría tardar hasta 30 minutos en recibir llamadas de una cola de llamadas. Un grupo de seguridad o lista de distribución recién creado puede tardar hasta 48 horas para que estén disponibles para usarse con colas de llamadas. Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata.

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

**Método de enrutamiento** Puede elegir ya sea **operador**, **en serie**o **Round Robin** para el método de distribución de la cola de llamada. De manera predeterminada, todas las colas de llamadas nuevas y existentes tienen un enrutamiento a operador seleccionado. Cuando se usa el operador de enrutamiento, la primera llamada en la cola sonarán todos los agentes de la llamada al mismo tiempo. El primer agente de llamada para atender la llamada, obtiene la llamada.

- **Enrutamiento de operador** hace que la primera llamada en la cola para llamar a todos los agentes de la llamada al mismo tiempo. El primer agente de llamada para atender la llamada, obtiene la llamada.
- **Enrutamiento en serie** , hace que las llamadas entrantes llamar a los agentes de llamada uno a uno, comenzando por el principio de la lista de agentes de la llamada. Si un agente omite o no contesta una llamada, se realizará una llamada al siguiente agente de la lista y se probará con todos los agentes, de uno a uno, hasta que se responda la llamada o se agote el tiempo de espera en la cola.
  > [!NOTE]
  > El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola.
- **Operación por turnos** equilibra el enrutamiento de las llamadas entrantes de manera que cada agente de llamada obtendrá el mismo número de llamadas de la cola. Esto puede resultar muy deseable en un entorno de venta entrante para garantizar la igualdad de oportunidades entre todos los agentes de la llamada.

### <a name="select-an-agent-opt-out-option"></a>Seleccionar una opción de no participación de agente

![Muestra la casilla de verificación de no participación de agente](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

**Opción de no participación de agente** Puede elegir esta opción para permitir a los agentes de la cola de llamadas no participar en la recepción de llamadas procedentes de una cola determinada mediante la selección de **Opción de no participación de agente**.

Si habilita esta opción permite que va todos los agentes en esta cola para iniciar o detener la recepción de llamadas desde esta cola de llamada en. Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).

Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:

 1. Abra **Opciones** en el cliente de Skype for Business de su escritorio.
 2. En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.
 3. En la página de configuración del usuario, haga clic en **Colas de llamadas**y, a continuación, desactive las casillas de verificación de las colas en las que no desee participar.

    > [!NOTE]
    > Los agentes con aplicaciones o extremos distinto de Skype para escritorio de negocio puede tener acceso a la opción de descarte desde el portal de la configuración de usuario [https://aka.ms/cqsettings](https://aka.ms/cqsettings).

![Número 2](media/sfbcallout2.png)
**configuración de alerta del agente**

Esto define la duración de un agente se notifique de una llamada antes de la serie o métodos de enrutamiento Round Robin mover al siguiente agente.

El valor predeterminado es 30 segundos, pero se puede establecer para hasta 3 minutos.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Establecer el desbordamiento de la llamada y el tiempo de espera de las opciones de control

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede oscilar entre 0 y 200. Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.

* * *

![Número 2](media/sfbcallout2.png)

**Cuando se alcanza el número máximo de llamadas** Cuando la cola llamada alcanza su tamaño máximo (establecido con el valor **máximo de llamadas en la cola** ), puede elegir lo que ocurre con las nuevas llamadas recibidas.

- **Desconectar**: la llamada se desconectará.
- **Redirigir a** Cuando se selecciona esta opción, seleccione una de las siguientes opciones:

  - **Persona de la empresa** Un usuario con una licencia de **Sistema telefónico** en línea y estar habilitados para Enterprise Voice o disponer de un Plan de llamada. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.

  Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz en la nube](set-up-phone-system-voicemail.md).

  - **Aplicación de voz** Seleccione el nombre de uno de ellos en una cola de llamada u operadores automáticos que ya se ha creado.

* * *

![Número 3](media/sfbcallout3.png)

**Llamar a tiempo de espera: tiempo de espera máximo** También puede decidir cuánto tiempo una llamada puede ser en espera en la cola antes de que se agota el tiempo y se debe redirigir o desconectado. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos.

El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos. Esto permite manipular el flujo de llamadas con una granularidad más fina. Por ejemplo, podría especificar que todas las llamadas que un agente no responde dentro de 30 segundos vaya a un operador automático de búsqueda en el directorio.

![Número 4](media/sfbcallout4.png)

**Cuando se agota el tiempo de espera de llamada** Cuando la llamada alcanza el límite establecido en la configuración de **cuánto tiempo puede esperar una llamada en la cola** , puede elegir lo que ocurre con esta llamada:

- **Desconectar**: la llamada se desconectará.
- **Redirigir esta llamada a** Cuando se selecciona esta opción, tendrá estas opciones:
  - **Persona de la empresa** Un usuario con una licencia de **Sistema telefónico** en línea y estar habilitados para Enterprise Voice o tienen planes de llamada. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.

  Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz en la nube](set-up-phone-system-voicemail.md).

  - **Aplicación de voz** Seleccione el nombre de uno de ellos en una cola de llamada u operadores automáticos que ya se ha creado.

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>Cambiar el identificador de autor de la llamada de un usuario para las llamadas salientes 

Puede proteger la identidad del usuario cambiando su identificador de autor de la llamada para llamadas salientes a una cola de llamadas, operador automático o cualquier número de servicio en su lugar mediante la creación de una directiva con el cmdlet **New-CsCallingLineIdentity** .

Para ello, ejecute:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**. Para ello, ejecute:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información acerca de cómo realizar cambios en la configuración de identificador de autor de la llamada de la organización en el artículo [cómo se puede usar el identificador de autor de la llamada de la organización](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar colas de llamadas.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

Estos son los cmdlets que necesita para administrar una cola de llamadas.
  
- [Nueva CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Teams Microsoft mediante un único punto de administración que puede simplificar su trabajo diario, cuando haya varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre sólo desde el centro de administración de Microsoft Teams como cuando desea realizar cambios en la configuración de muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Administración de Office 365 con Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico de Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nueva CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
