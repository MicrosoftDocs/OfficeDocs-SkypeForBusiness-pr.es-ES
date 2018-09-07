---
title: Crear una cola de llamadas de Sistema telefónico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el sistema telefónico para colas de llamadas de Office 365 (PBX en la nube) para que le proporcionen un saludo organizativo, música en espera y redireccionamiento de llamadas a los agentes de llamadas en las listas de distribución y grupos de seguridad. También puede establecer las opciones de tamaño máximo de cola, tiempo de espera y administración de llamadas. '
ms.openlocfilehash: bb9812eb880ce7451c2fd30f93fa080d6ec84c87
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854451"
---
# <a name="create-a-phone-system-call-queue"></a>Crear una cola de llamadas de Sistema telefónico

Las colas de llamadas del Sistema telefónico incluyen el saludo que se usa cuando alguien llama a un número de teléfono de su organización, la capacidad de poner llamadas en espera y la de localizar a un agente disponible para responder a la llamada mientras quien llama escucha una música durante la espera. Puede crear una o varias colas de llamadas para su organización.
  
Las colas de llamadas del Sistema telefónico pueden proporcionar:
  
- Un mensaje de saludo empresarial.
    
- Música que se reproduce mientras los usuarios se mantienen a la espera.
    
- Redireccionamiento de llamadas a agentes de llamada en listas de distribución habilitadas para correo electrónico y grupos de seguridad.
    
- Posibilidad de realizar la configuración de opciones de tamaño máximo de la cola de llamadas, tiempo de espera y administración de llamadas.
    
Cuando alguien llama a un número de teléfono que tiene configurada una cola de llamadas, el autor de la llamada oye primero un mensaje de saludo (si se ha configurado uno) y después la llamada se pone en la cola, donde esperará hasta que un agente de llamadas esté disponible. El autor de la llamada escuchará música mientras está en espera, y las llamadas se ofrecerán a los agentes de llamadas según el principio de  *primero en entrar, primero en salir*  (FIFO).
  
Todas las llamadas que se encuentren en espera en la cola se distribuirán usando un modo de enrutamiento a operador o enrutamiento en serie:
  
- Con enrutamiento a operador, la primera llamada de la cola llamará simultáneamente a todos los agentes.
    
- Con el enrutamiento en serie, la primera llamada de la cola llamará a todos los agentes uno a uno.
    
    > [!NOTE]
    > No se llamará a los agentes de llamadas que están **Sin conexión**, han establecido su presencia en **No molestar** o han decidido quedar fuera de la cola de llamadas.
  
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
    
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.
    
## <a name="step-1---getting-started"></a>Paso 1: tareas iniciales

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
- Su organización debe tener (como mínimo) una licencia de **Sistema telefónico** Enterprise E3 plus o una licencia Enterprise E5. El número de licencias de usuario de **Sistema telefónico** que se asignan afecta a la cantidad de números de servicio que están disponibles para usarse para las colas de llamadas. La cantidad de colas de llamadas que puede tener depende del número de licencias de **Sistema telefónico** y **Audioconferencia** asignadas en la organización. Para obtener más información acerca de las licencias, consulte [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para redirigir las llamadas a personas de la organización que están en línea, estas deben tener una licencia de **Sistema telefónico** y estar habilitadas para Enterprise Voice o tener Planes de llamadas de Office 365. Vea [Asignar licencias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información acerca de planes de llamadas de Office 365, vea [¿Cuáles son los planes de llamadas en Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) y [Planes de llamadas para Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Los usuarios alojados localmente con Lync Server 2010 no se admiten como agentes de cola de llamadas. 
  
- Solo se pueden asignar números de teléfono de servicio de pago y gratuitos obtenidos en el **Centro de administración de Skype for Business** o transferidos desde otro proveedor de servicios a las colas de llamadas del Sistema telefónico. Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.
    
    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
- Cuando distribuye las llamadas entrantes de una cola de llamadas del Sistema telefónico, estos clientes son compatibles para agentes de llamadas:
    
  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
    
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
    
  - Todos los modelos de teléfonos IP compatibles con Skype for Business Online. Consulte [Obtener teléfonos con Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores) 
    
  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
    
  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
    
  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)

  - Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)

  - Cliente de Microsoft Teams para Mac

  - Aplicación Microsoft Teams para iPhone

  - Aplicación Microsoft Teams para Android
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Paso 2: obtener o transferir números de servicio de pago o gratuitos

Antes de crear o configurar una cola, tendrá que obtener sus números de servicio de pago o gratuitos, o transferir unos existentes. Después de obtener los números de teléfono de servicio de pago o gratuitos, se mostrarán en **Centro de administración de Skype for Business** > **Voz** > **Números de teléfono**, y el **Tipo de número** listado aparecerá como **Servicio - gratuito**. Para obtener sus números de servicio, consulte [Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](getting-service-phone-numbers.md) o, si desea transferir un número de servicio existente, consulte [Transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Si se encuentra fuera de Estados Unidos, no podrá usar el Centro de administración de Skype for Business para obtener números de servicio. En ese caso, vaya a [Administrar números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para ver cómo hacerlo desde fuera de Estados Unidos.
  
## <a name="step-3---create-a-new-call-queue"></a>Paso 3: crear una cola de llamadas nueva

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype for Business**

En el **Centro de administración de Skype for Business**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, y después en **Agregar nueva**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir el nombre para mostrar de la cola de llamadas, el número de teléfono y el dominio (si disponible)

![Configurar una cola de llamadas.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nombre** Introduzca un nombre para mostrar descriptivo para la cola de llamadas. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos. <br/> Este nombre se mostrará en la notificación de la llamada entrante.
***
![Número 2](../images/sfbcallout2.png)<br/>**Número de teléfono** Seleccione un número de servicio de pago o gratuito para la cola de llamadas. Este paso es opcional. <br/> Si no se enumera ninguno, deberá obtener los números de servicio para poder crear esta cola de llamadas. Para obtener sus números de servicio, vea [Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Dominio** Si está disponible, elija el dominio de Office 365 que desee usar. Esta opción solo está disponible si tiene más de un dominio en uso con Office 365. Si tiene más de uno, deberá elegir un nombre de dominio de la lista. <br/> Por ejemplo, puede tener un dominio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Configurar una cola de llamadas.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saludo**: este campo es opcional. Es el saludo que se reproduce para las personas que realizan una llamada al número de la cola de llamadas. <br/> Puede cargar un archivo de audio (en el formato .wav, .mp3 o .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Música en espera** Puede utilizar la música en espera predeterminada que se suministra con la cola de llamadas o cargar un archivo de audio en el formato .wav, mp3 o .wma para utilizarlo como su música en espera personalizada. 
   

### <a name="select-the-call-distribution-method"></a>Seleccionar método de distribución de llamadas

![Muestra las opciones del método de distribución de la llamadas](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Método de distribución de llamadas** Puede elegir **Operador** o **En serie** para el método de distribución de la cola de llamadas. De manera predeterminada, todas las colas de llamadas nuevas y existentes tienen un enrutamiento a operador seleccionado. Para usar el enrutamiento en serie, debe elegir explícitamente la opción de enrutamiento **En serie** de cmdlets y la interfaz de usuario. <br/><br/> Cuando se elige el enrutamiento en serie y se guarda la cola de llamadas, las llamadas de la cola llamarán a los agentes uno a uno, comenzando por el principio de la lista de agentes. Si un agente omite o no contesta una llamada, se realizará una llamada al siguiente agente de la lista y se probará con todos los agentes, de uno a uno, hasta que se responda la llamada o se agote el tiempo de espera en la cola.   

> [!NOTE]
> El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola. 
   
### <a name="select-an-agent-opt-out-option"></a>Seleccionar una opción de no participación de agente

![Muestra la casilla de verificación de no participación de agente](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Opción de no participación de agente** Puede elegir esta opción para permitir a los agentes de la cola de llamadas no participar en la recepción de llamadas procedentes de una cola determinada mediante la selección de **Opción de no participación de agente**.  <br/> Si habilita esta opción, permite que todos los agentes de esta cola inicien o detengan la recepción de llamadas desde esta cola de llamadas, según lo deseen. Puede revocar en cualquier momento el privilegio de no participación de agente desactivando la casilla de verificación, lo que hace que los agentes participen automáticamente de nuevo en esta cola (el valor predeterminado de todos los agentes).  <br/><br/> Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:
 1. Abra **Opciones** en el cliente de Skype for Business de su escritorio. 
 2. En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.
 3. En la página de configuración del usuario, haga clic en **Colas de llamadas**y, a continuación, desactive las casillas de verificación de las colas en las que no desee participar.
 
    > [!NOTE] 
    > Los agentes con clientes Mac, Mobile o Lync 2013 o los usuarios de Voz híbrida alojados localmente que utilicen Skype for Business 2015 pueden ir a [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para tener acceso a la opción de no participación.
   
### <a name="add-call-agents-to-a-call-queue"></a>Agregar agentes de llamadas a una cola de llamadas

![Configurar colas de llamadas.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Los agentes de llamadas (como máximo 50) pueden ser:
*    Un usuario en línea con una licencia de **Sistema telefónico** y habilitado para Enterprise Voice o con un Plan de llamada. <br/><br/> **Nota:** Para redirigir las llamadas a personas de la organización que estén en línea, estas deben tener una licencia de **Sistema telefónico** y estar habilitadas para Enterprise Voice o tener Planes de llamadas. Vea [Asignar licencias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Usuarios en línea con una licencia de **Sistema telefónico** y un Plan de llamadas que se agregan a un grupo de Office 365, una lista de distribución habilitada para correo o un grupo de seguridad. El nuevo agente agregado a una lista de distribución o a un grupo de seguridad podría tardar hasta 30 minutos en recibir llamadas de una cola de llamadas. Un grupo de seguridad o lista de distribución que se acaba de crear puede tardar hasta 48 horas para que esté disponible para usarse con colas de llamadas. Los grupos de Office 365 que se acaban de crear están disponibles casi de forma inmediata. <br/> 

    > [!NOTE] 
    > No se admiten los usuarios alojados localmente que utilicen Lync Server 2010.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Establecer el tamaño máximo de cola y el tiempo de espera máximo

![Configurar una cola de llamadas.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Número máximo de llamadas en la cola** Use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede oscilar entre 0 y 200. Cuando se alcanza este límite, la llamada se administrará de manera que se ha establecido en el ajuste **Cuando se alcanza el número máximo de llamadas** que aparece a continuación.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Cuando se alcanza el número máximo de llamadas** Cuando la cola de llamadas llegue al tamaño máximo (configurado con el ajuste **Número máximo de llamadas en la cola**) puede elegir lo que sucede a las nuevas llamadas entrantes.
*    **Desconectar con una señal de línea ocupada** Se desconectará la llamada.
*    **Reenviar esta llamada a** Si elige este ajuste, tiene tres opciones:
     *    **Persona de la empresa** Un usuario en línea con una licencia de **Sistema telefónico** y que esta habilitado para Enterprise Voice o que tiene un Plan de llamadas. Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **Persona de la empresa** y configúrela para que las llamadas que reciba esta persona se desvíen directamente al correo de voz. <br/> <br/>Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz de Sistema telefónico](/microsoftteams/set-up-phone-system-voicemail). 
     
        > [!Note]
        > No se admiten los usuarios alojados localmente que utilicen Lync Server 2010.<br/>
     
     *    **Cola de llamadas**: debe haber creado anteriormente otra cola de llamadas para poder seleccionarla.
     *    **Operador automático**: debe haber creado anteriormente un operador automático para poder seleccionarlo. Vea [Configurar un operador automático de Sistema telefónico](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Cuánto tiempo puede esperar una llamada en la cola** También puede decidir cuánto tiempo puede ponerse en espera una llamada en la cola antes de redirigirla o desconectarla. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos. <br/><br/> El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos. Esto permite manipular el flujo de llamadas con una granularidad más fina. Por ejemplo, podría especificar que todas las llamadas que un agente no responde en un plazo de 30 segundos vaya a un operador automático de búsqueda de Active Directory. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Cuando una llamada agota el tiempo de espera**: puede elegir lo que sucede con las llamadas cuando alcanzan el límite establecido en el ajuste **Cuánto tiempo puede esperar una llamada en la cola**:
*    **Desconectar** La llamada se desconectará.
*    **Reenviar esta llamada a** Si elige este ajuste, tiene tres opciones:
     *    **Persona de la empresa** Un usuario en línea con una licencia de **Sistema telefónico** y que esta habilitado para Enterprise Voice o que tiene un Plan de llamadas. Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **Persona de la empresa** y configúrela para que las llamadas que reciba esta persona se desvíen directamente al correo de voz. </br><br/>  Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz de Sistema telefónico](/microsoftteams/set-up-phone-system-voicemail). 

        > [!Note]
        > No se admiten los usuarios alojados localmente que utilicen Lync Server 2010.<br/>

     *    **Cola de llamadas**: debe haber creado anteriormente otra cola de llamadas para poder seleccionarla.
     *    **Operador automático**: debe haber creado anteriormente un operador automático para poder seleccionarlo. Vea [Configurar un operador automático de Sistema telefónico](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Cambiar la identificación de llamada del usuario para que sea el número de teléfono de la cola de llamadas

Puede proteger la identidad de un usuario cambiando su identificador de llamada para las llamadas salientes a una cola de llamadas en lugar de crear una directiva con el cmdlet **New-CallingLineIdentity**.
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**. Para ello, ejecute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información acerca de cómo realizar cambios en la configuración de la identificación de llamada de su organización [aquí](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar colas de llamadas.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

Estos son los cmdlets que necesita para administrar una cola de llamadas.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Esto es lo que conseguirá con Sistema telefónico en Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
