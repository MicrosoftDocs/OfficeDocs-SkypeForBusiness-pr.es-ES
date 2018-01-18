---
title: "Crear una cola de llamadas de sistema de teléfono"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 6dab9a0a4371de29ceaf51a05368fc7ba2c0a4ac
ms.sourcegitcommit: 820ebac06f38f82c900fc87e19a9cec624d81c5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2018
---
# <a name="create-a-phone-system-call-queue"></a>Crear una cola de llamadas de sistema de teléfono

Llamada de sistema incluyen un saludo que se utiliza cuando alguien llama a un número de teléfono para su organización, la capacidad para colocar automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponible controlar la llamada, mientras que la gente que llamada se escucha música en espera. Puede crear una o varias colas de llamada para su organización.
  
Colas de llamadas de sistema de teléfono pueden proporcionar:
  
- Un mensaje de saludo empresarial.
    
- Música que se reproduce mientras los usuarios se mantienen a la espera.
    
- El redireccionamiento de llamadas para llamar a los agentes en las listas de distribución de correo y grupos de seguridad.
    
- Realizar la configuración de tamaño máximo de la cola de llamada, tiempo de espera y opciones de manejo de llamadas.
    
Cuando alguien llama a un número de teléfono que se establece de arriba con una cola de llamada, escuchará un saludo primero (si se configura cualquiera) y, a continuación, se coloca en la cola y espere el siguiente agente de llamada disponibles. La persona que llama escuchará música mientras están en espera de suspensión y las llamadas se ofrecerá a los agentes de la llamada de la manera de *Primero en ENTRAR, primero en salir* (FIFO).
  
Todas las llamadas en espera en la cola se distribuirá mediante un operador enrutamiento modo o serie enrutamiento:
  
- Con el enrutamiento de operador, la primera llamada en la cola sonará a todos los agentes a la vez.
    
- Con el enrutamiento de serie, la primera llamada en la cola sonará uno por uno todos los agentes de llamada.
    
    > [!NOTE]
    > No se llamará agentes de llamada **sin conexión**, han establecido su presencia en **No molestar,** o han optado por fuera de la cola de llamada.
  
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
    
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.
    
## <a name="step-1---getting-started"></a>Paso 1: tareas iniciales

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
- La organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema de teléfono** o una licencia de Enterprise E5. El número de licencias de usuario de **Sistema telefónico** se asignan afecta a la cantidad de números de servicio que están disponibles para ser usados para las colas de llamada. El número de colas de llamada que puede tener depende de la cantidad de licencias de **Conferencias de Audio** y **Sistema de teléfono** que están asignadas en la organización. Para obtener más información acerca de licencias, vaya [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y habilitadas para Telefonía IP empresarial o tienen planes llamar de Office 365. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitarlos para Telefonía IP empresarial, puede utilizar Windows PowerShell. Por ejemplo ejecutar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información acerca de Office 365 llamando a planes, consulte [¿Qué planes de llamada Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) y [Llamar a los planes de Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Los usuarios alojados en locales no se admite el uso de Lync Server 2010 como una cola llamar a los agentes. 
  
- Sólo se pueden asignar el pago y números de teléfono de servicio gratuito que obtuvo en el **Skype para el centro de administración de negocios** o transferido desde otro proveedor de servicios a las colas de sistema de teléfono llamada. Para obtener y utilizar números gratuitos del servicio, es necesario configurar comunicaciones créditos.
    
    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
- Cuando se va a distribuir las llamadas entrantes de una cola de llamada de teléfono de sistema, estos clientes son compatibles con agentes de llamada:
    
  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
    
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
    
  - Todos los modelos de teléfono IP compatibles con Skype para los negocios en línea. Consulte [obtención de teléfonos para Skype para los negocios en línea](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Skype de Mac para Business Client (versión 16.8.196 y posterior) 
    
  - Android Skype para Business Client (versión 6.16.0.9 y posterior)
    
  - iPhone Skype para Business Client (versión 6.16.0 y posterior)
    
  - iPad Skype para Business Client (versión 6.16.0 y posterior)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Paso 2: obtener o transferir números de servicio de pago o gratuitos

Para poder crear y configurar las colas de llamadas, necesitará obtener o transferir su pago existente o el servicio gratuito números. Después de obtener el número o números de teléfono de servicio gratuito, se mostrará en **Skype para el centro de administración de negocios** > **voz** > **números de teléfono**y la voluntad de **tipo número** en la lista aparecen como **servicio - gratis **. Para obtener los números de servicio, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](getting-service-phone-numbers.md) o si desea transferir y el número de servicio existente, consulte [transferir números de teléfono para Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede utilizar el Skype para el centro de administración de negocios para obtener números de servicio. Vaya [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de Estados Unidos.
  
## <a name="step-3---create-a-new-call-queue"></a>Paso 3: crear una cola de llamadas nueva

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, y después en **Agregar nueva**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir el nombre para mostrar de la cola de llamadas, el número de teléfono y el dominio (si disponible)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nombre**: introduzca un nombre para mostrar descriptivo para la cola de llamadas. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.<br/> Este nombre se mostrará en la notificación de la llamada entrante.
***
![Número 2](../images/sfbcallout2.png)<br/>**Número de teléfono** Seleccione un pago de servicio o número de teléfono gratuito para la cola de llamada. Esto es opcional. <br/> Si no hay ninguno en la lista, deberá obtener números de servicio para poder crear esta cola de llamada. Para obtener los números de servicio, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Dominio**: si está disponible, elija el dominio de Office 365 que desee usar. Esta opción solo está disponible si tiene más de un dominio en uso con Office 365. Si tiene más de uno, deberá elegir un nombre de dominio de la lista.<br/> Por ejemplo, puede tener un dominio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saludo** es opcional. Este es el saludo que se reproduce para las personas que llaman en al número de llamada de cola. <br/> Puede cargar un archivo de audio (formatos .wav,. mp3 o .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Mantenga la Música en** Puede utilizar el valor predeterminado de Música en espera proporcionado con la cola de llamada, o puede cargar un archivo de audio en formatos WAV, mp3 o .wma para utilizar como tu Música personalizada en suspensión. 
   

### <a name="select-the-call-distribution-method"></a>Seleccione el método de distribución de llamadas

![Muestra opciones de método de distribución de la llamada](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Llame al método de distribución** Puede elegir **el operador** o **serie** para el método de distribución de la cola de llamada. Todas las colas de llamada nueva y existente tendrá enrutamiento operador seleccionado por defecto. Para utilizar el encaminamiento de serie, debe elegir explícitamente la opción **serie** de enrutamiento en la interfaz de usuario y los cmdlets. <br/><br/> Cuando se elige la ruta serie y se guarda la cola de llamada, las llamadas de la cola sonará a los agentes uno a uno, comenzando por el principio de la lista de agentes. Si un agente se despide o no recoge una llamada, la llamada sonará al siguiente agente en la lista y probará todos los agentes de uno en uno hasta que se recoge o tiempos de espera en la cola.  <br/><br/>  **Nota:** Enrutamiento de serie omitirá a agentes con **sin conexión**, han establecido su presencia en **No molestar**u **rechazado** de recibir llamadas desde esta cola.  
   
### <a name="select-an-agent-opt-out-option"></a>Seleccione un agente opt out (opción)

![Casilla de verificación muestra el agente de cancelación de suscripción](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Opción de desactivación de agente** Puede permitir que los agentes de la cola de llamada no participar en la realización de llamadas desde una determinada cola seleccionando la **Opción de desactivación de agente**.  <br/> Al habilitar esta opción permite serán todos los agentes en esta cola para iniciar o dejar de recibir la llamada de esta cola de llamada a. Puede revocar el privilegio de optar por agente en cualquier momento desactivando la casilla de verificación, causando agentes se convierten automáticamente suscrito para esta cola otra vez (el valor predeterminado para todos los agentes).  <br/><br/> Para acceder a la opción de anulación, agentes pueden hacer lo siguiente:
 1. Abra **Opciones** en su escritorio Skype para cliente de empresa. 
 2. En la ficha **Transferencia de llamadas** , haga clic en el vínculo **Editar configuración en línea** .
 3. En la página de configuración de usuario, haga clic en **Llamar a colas**y, a continuación, desactive las casillas de verificación de las colas para las que desean participar.
   
### <a name="add-call-agents-to-a-call-queue"></a>Agregar agentes de llamadas a una cola de llamadas

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Agentes de llamada (máximo 50) pueden ser:
*    Un usuario con una licencia de **Sistema de teléfono** en línea y habilitado para la Telefonía IP empresarial o con un Plan de llamadas. <br/><br/> **Nota:**  Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y habilitadas para Telefonía IP empresarial o tener un Plan de llamadas. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitarlos para Telefonía IP empresarial, puede utilizar Windows PowerShell. Por ejemplo ejecutar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Usuarios en línea con una con una licencia de **Sistema telefónico** y un Plan de llamadas que se agregan a un grupo de Office 365, una lista de distribución de correo o un grupo de seguridad. Puede tardar hasta 30 minutos para un nuevo agente agregado para que una lista de distribución o un grupo de seguridad para empezar a recibir llamadas de una llamada de cola. Un grupo de seguridad o lista de distribución recién creado puede tardar hasta 48 horas en estar disponible para utilizarse con las colas de llamada. Recién creado Office 365 grupos están disponibles casi de inmediato. <br/> 

    > [!NOTE] 
    > Los usuarios alojados en locales no se admite el uso de Lync Server 2010.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Establecer el tamaño máximo de cola y el tiempo de espera máximo

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Máximo de llamadas en la cola** Utilice esto para establecer las llamadas máximas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede oscilar entre 0 y 200.the cuando se alcanza este límite, la llamada se gestionarán de modo que se ha establecido en la configuración **cuando se alcanza el número máximo de llamadas** siguiente.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Cuando se alcanza el número máximo de llamadas** Cuando la llamada de cola alcanza su tamaño máximo (establecida mediante el valor **máximo que se llama en la cola** ), puede elegir qué sucede con las nuevas llamadas recibidas.
*    **Desconectar con una señal de línea ocupada**: se desconectará la llamada.
*    **Desviar esta llamada** Cuando se selecciona esta opción, tienes estas opciones:
     *    **Persona de la empresa** Un usuario con una licencia de **Sistema de teléfono** en línea y habilitarse para Telefonía IP empresarial o tienen un Plan de llamadas. Puede configurar, por lo que la persona que llama se puede enviar al correo de voz. Para ello, seleccione una **persona de la empresa** y establezca esta persona para que las llamadas se desvían directamente al correo de voz. <br/>
     
        > [!Note]
        > Los usuarios alojados en locales no se admite el uso de Lync Server 2010.<br/>
     
     *    **Llame a la cola** Debe haber creado ya otra cola de llamada, pero después de hacerlo, puede seleccionar esa cola de llamada.
     *    **Operador automático** Debe haber creado a un operador automático, pero después de hacerlo, puede seleccionar el operador automático. Consulte [configurar un operador automático de sistema de teléfono](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Cuánto tiempo puede esperar una llamada en la cola**: también puede decidir cuánto tiempo puede ponerse en espera una llamada en la cola antes de redirigirla o desconectarla. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos.  <br/><br/> Puede establecerse el valor de tiempo de espera en segundos, a intervalos de 15 segundos. Esto le permite manipular el flujo de llamadas con una granularidad más fina. Por ejemplo, podría especificar que todas las llamadas que un agente no responde dentro de 30 segundos se van a un Operador automático de búsqueda de directorio. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Cuando una llamada agota el tiempo de espera**: puede elegir lo que sucede con las llamadas cuando alcanzan el límite establecido en el ajuste **Cuánto tiempo puede esperar una llamada en la cola**:
*    **Desconectar**: la llamada se desconectará.
*    **Desviar esta llamada** Cuando se selecciona esta opción, tienes estas opciones:
     *    **Persona de la empresa** Un usuario con una licencia de **Sistema de teléfono** en línea y habilitarse para Telefonía IP empresarial o tienen planes de llamada. Puede configurar, por lo que la persona que llama se puede enviar al correo de voz. Para ello, seleccione una **persona de la empresa** y establezca esta persona para que las llamadas se desvían directamente al correo de voz. 

        > [!Note]
        > Los usuarios alojados en locales no se admite el uso de Lync Server 2010.<br/>

     *    **Llame a la cola** Debe haber creado ya otra cola de llamada, pero después de hacerlo, puede seleccionar esa cola de llamada.
     *    **Operador automático** Debe haber creado a un operador automático, pero después de hacerlo, puede seleccionar el operador automático. Consulte [configurar un operador automático de sistema de teléfono](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Cambiar el identificador del usuario llamador para que sea el número de teléfono de una llamada de cola

Puede proteger la identidad de un usuario cambiando su ID de llamada para las llamadas salientes a una cola de llamada en su lugar mediante la creación de una directiva con el cmdlet **New-CallingLineIdentity** .
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplicar la directiva al usuario mediante el cmdlet de **Concesión CallingLineIdentity** . Para ello, ejecute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información sobre cómo realizar cambios en la configuración del ID de llamador en su organización [aquí](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar colas de llamadas.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

Estos son los cmdlets que necesita para administrar una cola de llamadas.
  
- [Nueva CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Conjunto de CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Quitar CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Aquí está lo que se obtiene con el sistema de teléfono en Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio Skype para empresas y Teams de Microsoft](getting-service-phone-numbers.md)

[Disponibilidad de país y región para conferencias de Audio y planes de llamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
