---
title: Crear una cola de llamadas de sistema telefónico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 18988c7d6f913b85d11bc465c336dfd265fa34a0
ms.sourcegitcommit: 6340d0050a51790e40b7ab8e4e89348251ba184f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "19649586"
---
# <a name="create-a-phone-system-call-queue"></a>Crear una cola de llamadas de sistema telefónico

Llamada de teléfono del sistema colas incluyen el saludo que se usa cuando alguien llama a un número de teléfono para su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponibles controlar la llamada mientras las personas que llamada se escuchan música en espera. Puede crear una o varias colas de llamadas para su organización.
  
Pueden proporcionar las colas de llamadas de teléfono del sistema:
  
- Un mensaje de saludo empresarial.
    
- Música que se reproduce mientras los usuarios se mantienen a la espera.
    
- El redireccionamiento de llamadas para llamar a los agentes en las listas de distribución habilitados para correo y grupos de seguridad.
    
- Realizar la configuración de tamaño máximo de la cola de llamadas, tiempo de espera y las opciones de administración de llamadas.
    
Cuando alguien llama a un número de teléfono que se establece una copia de seguridad con una cola de llamadas, escuchará un saludo inicial (si se configura cualquiera) y, a continuación, se coloca en la cola y espere a que el siguiente agente de llamada disponibles. El autor de la llamada escuchará música mientras está en espera, y las llamadas se ofrecerán a los agentes de llamadas según el principio de  *primero en entrar, primero en salir*  (FIFO).
  
Todas las llamadas en espera en la cola se distribuirá mediante un modo de enrutamiento operador o el modo de enrutamiento en serie:
  
- Con el operador de enrutamiento, la primera llamada en la cola sonarán a todos los agentes al mismo tiempo.
    
- Con el enrutamiento en serie, la primera llamada en la cola sonarán todos los agentes de llamada uno por uno.
    
    > [!NOTE]
    > Los agentes de llamada que están **sin conexión**, han establecido su presencia en **No molestar** o han decidido fuera de la cola de llamada no se llamará.
  
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
    
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.
    
## <a name="step-1---getting-started"></a>Paso 1: tareas iniciales

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
- Su organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema telefónico** o una licencia Enterprise E5. El número de licencias de usuario de **Sistema telefónico** que se asignan afecta al número de números de servicio que están disponibles para usarse en las colas de llamadas. El número de colas de llamada que puede tener depende de que el número de licencias de **Sistema telefónico** y **Conferencias de Audio** que se asignan en la organización. Para obtener más información acerca de las licencias, vaya [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información acerca de planes de llamada de Office 365, vea [¿Cuáles son los planes de llamada en Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) y [Llamar a los planes de Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Los usuarios alojados en implementaciones locales con Lync Server 2010 no se admiten como una cola llamar a los agentes. 
  
- Sólo se pueden asignar números de pago y los números de teléfono de un servicio gratuito que obtuvo en el **Skype para el centro de administración de negocio** o transferido desde otro proveedor de servicios a las colas de llamadas de sistema telefónico. Para obtener y usar los números de teléfono gratuito de servicio, debe configurar Communications créditos.
    
    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
- Cuando se va a distribuir las llamadas entrantes de una cola de llamada de sistema telefónico, estos clientes son compatibles para agentes de llamada:
    
  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
    
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
    
  - Todos los modelos de teléfonos IP compatibles con Skype Empresarial Online. Consulte [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype para Business Client (versión 16.8.196 y posterior) 
    
  - Android Skype para Business Client (versión 6.16.0.9 y posterior)
    
  - iPhone Skype para Business Client (versión 6.16.0 y posterior)
    
  - iPad Skype para Business Client (versión 6.16.0 y posterior)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Paso 2: obtener o transferir números de servicio de pago o gratuitos

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en **Skype para el centro de administración de negocio** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito **. Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción de Skype para profesionales y los equipos de Microsoft](getting-service-phone-numbers.md) o si desea transferir y el número de servicio existente, vea [transferir los números de teléfono para Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el Skype para el centro de administración de negocio para obtener números de servicio. Vaya a [administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.
  
## <a name="step-3---create-a-new-call-queue"></a>Paso 3: crear una cola de llamadas nueva

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, y después en **Agregar nueva**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir el nombre para mostrar de la cola de llamadas, el número de teléfono y el dominio (si disponible)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nombre**: introduzca un nombre para mostrar descriptivo para la cola de llamadas. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.<br/> Este nombre se mostrará en la notificación de la llamada entrante.
***
![Número 2](../images/sfbcallout2.png)<br/>**Número de teléfono**: seleccione un número de servicio de pago o gratuito para la cola de llamadas. Esto es opcional. <br/> Si no se enumera ninguno, deberá obtener los números de servicio para poder crear esta cola de llamadas. Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción de Skype para profesionales y los equipos de Microsoft](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Dominio**: si está disponible, elija el dominio de Office 365 que desee usar. Esta opción solo está disponible si tiene más de un dominio en uso con Office 365. Si tiene más de uno, deberá elegir un nombre de dominio de la lista.<br/> Por ejemplo, puede tener un dominio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saludo**: este campo es opcional. Este es el saludo que se reproduce para las personas que llamar el número de llamada de cola. <br/> Puede cargar un archivo de audio (formatos .wav,. mp3 o .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Música en espera** Puede usar el valor predeterminado de música en espera que se proporcionan con la cola de llamadas, o puede cargar un archivo de audio en los formatos WAV, mp3 o .wma que se utilizará como su personalizado de música en espera. 
   

### <a name="select-the-call-distribution-method"></a>Seleccione el método de distribución de llamada

![Muestra las opciones del método de distribución de la llamada](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Llame al método de distribución** Puede elegir el **operador** o **en serie** para el método de distribución de la cola de llamada. Todas las colas de llamadas nuevas y existentes tienen un enrutamiento operador seleccionada de manera predeterminada. Para usar el enrutamiento en serie, debe elegir explícitamente la opción de enrutamiento **en serie** de cmdlets y la interfaz de usuario. <br/><br/> Cuando se elige el enrutamiento en serie y se guarda la cola de llamadas, las llamadas desde la cola sonarán a los agentes uno a uno, comenzando por el principio de la lista de agentes. Si un agente omite o no recoge una llamada, la llamada sonará al siguiente agente en la lista y probará todos los agentes de uno a uno hasta que se recoge o tiempos de espera en la cola.   

> [!NOTE]
> Enrutamiento en serie omitirá a los agentes que están **sin conexión**, han establecido su presencia en **No molestar**o contienen **participa** de la obtención de las llamadas de esta cola. 
   
### <a name="select-an-agent-opt-out-option"></a>Seleccionar un agente excluir de opción

![Casilla de verificación se muestra en el agente de cancelación de suscripción](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Agente de excluir de opción** Puede permitir a los agentes de la cola de llamada anular teniendo las llamadas procedentes de una cola determinada mediante la selección de **Agente de excluir de opción**.  <br/> Si habilita esta opción permite que va todos los agentes en esta cola para iniciar o detener la recepción de llamadas desde esta cola de llamada en. Puede revocar el privilegio de agente voluntaria en cualquier momento desactivando la casilla de verificación, lo que provoca que los agentes se convierten en participa automáticamente de para volver a esta cola (el valor predeterminado de todos los agentes).  <br/><br/> Para obtener acceso a la opción Anular, los agentes pueden hacer lo siguiente:
 1. Abra **las opciones** en su escritorio Skype para clientes empresariales. 
 2. En la pestaña **Desvío de llamadas** , haga clic en el vínculo **Editar la configuración de en línea** .
 3. En la página de configuración de usuario, haga clic en **Las colas de llamadas**y, a continuación, desactive las casillas de verificación de las colas para el que desean excluir.
 
    > [!NOTE] 
    > Los agentes con Mac, mobile, o clientes de Lync 2013 o usuarios de voz híbrida que están hospedan local utilizando Skype para servidor empresarial 2015, puede ir a [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para tener acceso a la opción de descarte.
   
### <a name="add-call-agents-to-a-call-queue"></a>Agregar agentes de llamadas a una cola de llamadas

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Los agentes de llamada (máximo de 50) pueden ser:
*    Un usuario con una licencia de **Sistema telefónico** en línea y habilitados para Enterprise Voice o con un Plan de llamada. <br/><br/> **Nota:**  Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o disponer de un Plan de llamada. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Usuarios en línea con una licencia de **Sistema telefónico** y un Plan de llamada que se agregan a un grupo de Office 365, una lista de distribución habilitados para correo o un grupo de seguridad. El nuevo agente agregado a una lista de distribución o a un grupo de seguridad podría tardar hasta 30 minutos en recibir llamadas de una cola de llamadas. Un grupo de seguridad o lista de distribución recién creado puede tardar hasta 48 horas para que estén disponibles para usarse con colas de llamadas. Recién creado Office 365 grupos están disponibles casi inmediatamente. <br/> 

    > [!NOTE] 
    > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Establecer el tamaño máximo de cola y el tiempo de espera máximo

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede oscilar entre 0 y 200. cuando se alcanza este límite, la llamada que se controlarán de manera que se ha establecido en la configuración **cuando se alcanza el número máximo de llamadas** que aparece a continuación.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Cuando se alcanza el número máximo de llamadas** Cuando la cola llamada alcanza su tamaño máximo (establecido con el valor **máximo de llamadas en la cola** ), puede elegir lo que ocurre con las nuevas llamadas recibidas.
*    **Desconectar con una señal de línea ocupada**: se desconectará la llamada.
*    **Reenviar esta llamada a** Cuando se selecciona esta opción, tendrá estas opciones:
     *    **Persona de la empresa** Un usuario con una licencia de **Sistema telefónico** en línea y estar habilitados para Enterprise Voice o disponer de un Plan de llamada. Puede establecer que el autor de la llamada se derive a un correo de voz. Para ello, seleccione una **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz. <br/> <br/>Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz del sistema telefónico](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.<br/>
     
     *    **Cola de llamadas** Debe haber creado otra cola de llamada, pero después de que lo hace, puede seleccionar esa cola de llamada.
     *    **Operador automático** Debe haber creado a un operador automático, pero después de que lo hace, puede seleccionar a operador automático. Consulte [configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Cuánto tiempo puede esperar una llamada en la cola**: también puede decidir cuánto tiempo puede ponerse en espera una llamada en la cola antes de redirigirla o desconectarla. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos.  <br/><br/> El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos. Esto permite manipular el flujo de llamadas con una granularidad más fina. Por ejemplo, podría especificar que todas las llamadas que un agente no responde dentro de 30 segundos vaya a un operador automático de búsqueda de Active Directory. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Cuando una llamada agota el tiempo de espera**: puede elegir lo que sucede con las llamadas cuando alcanzan el límite establecido en el ajuste **Cuánto tiempo puede esperar una llamada en la cola**:
*    **Desconectar**: la llamada se desconectará.
*    **Reenviar esta llamada a** Cuando se selecciona esta opción, tendrá estas opciones:
     *    **Persona de la empresa** Un usuario con una licencia de **Sistema telefónico** en línea y estar habilitados para Enterprise Voice o tienen planes de llamada. Puede establecer que el autor de la llamada se derive a un correo de voz. Para ello, seleccione una **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz. </br><br/>  Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz del sistema telefónico](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.<br/>

     *    **Cola de llamadas** Debe haber creado otra cola de llamada, pero después de que lo hace, puede seleccionar esa cola de llamada.
     *    **Operador automático** Debe haber creado a un operador automático, pero después de que lo hace, puede seleccionar a operador automático. Consulte [configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Cambiar el identificador del usuario autor de la llamada para que sea el número de teléfono de la cola de llamada

Puede proteger la identidad del usuario cambiando su identificador de autor de la llamada para las llamadas salientes a una cola de llamada en su lugar mediante la creación de una directiva con el cmdlet **New-CallingLineIdentity** .
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplicar la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity** . Para ello, ejecute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información acerca de cómo realizar cambios en la configuración de identificador de autor de la llamada de su organización [aquí](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar colas de llamadas.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

Estos son los cmdlets que necesita para administrar una cola de llamadas.
  
- [Nueva CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Esto es lo que conseguirá con Sistema telefónico en Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
