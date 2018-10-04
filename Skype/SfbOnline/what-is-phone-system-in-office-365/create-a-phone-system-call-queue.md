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
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el sistema telefónico para colas de llamadas de Office 365 (PBX en la nube) para que le proporcionen un saludo organizativo, música en espera y redireccionamiento de llamadas a los agentes de llamadas en las listas de distribución y grupos de seguridad. También puede establecer las opciones de tamaño máximo de cola, tiempo de espera y administración de llamadas. '
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375153"
---
# <a name="create-a-phone-system-call-queue"></a>Crear una cola de llamadas de Sistema telefónico

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
Las colas de llamadas del Sistema telefónico pueden proporcionar:
  
- Un mensaje de saludo empresarial.
    
- Música que se reproduce mientras los usuarios se mantienen a la espera.
    
- El redireccionamiento de llamadas para llamar a los agentes en las listas de distribución habilitados para correo y grupos de seguridad.
    
- Realizar la configuración de tamaño máximo de la cola de llamadas, tiempo de espera y las opciones de administración de llamadas.
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.
  
Todas las llamadas en espera en la cola se distribuirá mediante un modo de enrutamiento operador o el modo de enrutamiento en serie:
  
- Con el operador de enrutamiento, la primera llamada en la cola sonarán a todos los agentes al mismo tiempo.
    
- Con el enrutamiento en serie, la primera llamada de la cola llamará a todos los agentes uno a uno.
    
    > [!NOTE]
    > No se llamará a los agentes de llamadas que están **Sin conexión**, han establecido su presencia en **No molestar** o han decidido quedar fuera de la cola de llamadas.
  
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
    
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.
    
## <a name="step-1---getting-started"></a>Paso 1: tareas iniciales

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información acerca de planes de llamadas de Office 365, vea [¿Cuáles son los planes de llamadas en Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) y [Planes de llamadas para Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Los usuarios alojados en implementaciones locales con Lync Server 2010 no se admiten como una cola llamar a los agentes. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
- Cuando se va a distribuir las llamadas entrantes de una cola de llamada de sistema telefónico, estos clientes son compatibles para agentes de llamada:
    
  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
    
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
    
  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores) 
    
  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
    
  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
    
  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)

  - Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)

  - Cliente de Microsoft Teams para Mac

  - Aplicación Microsoft Teams para iPhone

  - Aplicación Microsoft Teams para Android
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Paso 2: obtener o transferir números de servicio de pago o gratuitos

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Paso 3: crear una cola de llamadas nueva

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, y después en **Agregar nueva**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir el nombre para mostrar de la cola de llamadas, el número de teléfono y el dominio (si disponible)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nombre**: introduzca un nombre para mostrar descriptivo para la cola de llamadas. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.<br/> Este nombre se mostrará en la notificación de la llamada entrante.
***
![Número 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Dominio** Si está disponible, elija el dominio de Office 365 que desee usar. Esta opción solo está disponible si tiene más de un dominio en uso con Office 365. Si tiene más de uno, deberá elegir un nombre de dominio de la lista. <br/> Por ejemplo, puede tener un dominio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> Puede cargar un archivo de audio (formatos .wav,. mp3 o .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Música en espera** Puede usar el valor predeterminado de música en espera que se proporcionan con la cola de llamadas, o puede cargar un archivo de audio en los formatos WAV, mp3 o .wma que se utilizará como su personalizado de música en espera. 
   

### <a name="select-the-call-distribution-method"></a>Seleccionar método de distribución de llamadas

![Muestra las opciones del método de distribución de la llamadas](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> El enrutamiento en serie omitirá a los agentes que están **Sin conexión**, han establecido su presencia en **No molestar**o han **optado por no participar** en la recepción de llamadas de esta cola. 
   
### <a name="select-an-agent-opt-out-option"></a>Seleccionar una opción de no participación de agente

![Muestra la casilla de verificación de no participación de agente](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Opción de no participación de agente** Puede elegir esta opción para permitir a los agentes de la cola de llamadas no participar en la recepción de llamadas procedentes de una cola determinada mediante la selección de **Opción de no participación de agente**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> Para obtener acceso a la opción de no participación, los agentes pueden hacer lo siguiente:
 1. Abra **Opciones** en el cliente de Skype for Business de su escritorio. 
 2. En la pestaña **Desvío de llamadas**, haga clic en el vínculo **Editar la configuración de en línea**.
 3. En la página de configuración del usuario, haga clic en **Colas de llamadas**y, a continuación, desactive las casillas de verificación de las colas en las que no desee participar.
 
    > [!NOTE] 
    > Los agentes con clientes Mac, Mobile o Lync 2013 o los usuarios de Voz híbrida alojados localmente que utilicen Skype for Business 2015 pueden ir a [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para tener acceso a la opción de no participación.
   
### <a name="add-call-agents-to-a-call-queue"></a>Agregar agentes de llamadas a una cola de llamadas

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Los agentes de llamadas (como máximo 50) pueden ser:
* Un usuario en línea con una licencia de **Sistema telefónico** y habilitado para Enterprise Voice o con un Plan de llamada. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Establecer el tamaño máximo de cola y el tiempo de espera máximo

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Cuando se alcanza el número máximo de llamadas** Cuando la cola llamada alcanza su tamaño máximo (establecido con el valor **máximo de llamadas en la cola** ), puede elegir lo que ocurre con las nuevas llamadas recibidas.
* **Desconectar con una señal de línea ocupada**: se desconectará la llamada.
* **Reenviar esta llamada a** Cuando se selecciona esta opción, tendrá estas opciones:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz de Sistema telefónico](/microsoftteams/set-up-phone-system-voicemail). 
     
    > [!Note]
    > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.<br/>
     
  * **Cola de llamadas** Debe haber creado otra cola de llamada, pero después de que lo hace, puede seleccionar esa cola de llamada.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Cuánto tiempo puede esperar una llamada en la cola** También puede decidir cuánto tiempo puede ponerse en espera una llamada en la cola antes de redirigirla o desconectarla. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos. <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Cuando una llamada agota el tiempo de espera**: puede elegir lo que sucede con las llamadas cuando alcanzan el límite establecido en el ajuste **Cuánto tiempo puede esperar una llamada en la cola**:
* **Desconectar**: la llamada se desconectará.
* **Reenviar esta llamada a** Cuando se selecciona esta opción, tendrá estas opciones:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  Para obtener información acerca de las licencias necesarias para el correo de voz, vea [Configurar el correo de voz de Sistema telefónico](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010.<br/>

  * **Cola de llamadas** Debe haber creado otra cola de llamada, pero después de que lo hace, puede seleccionar esa cola de llamada.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Cambiar la identificación de llamada del usuario para que sea el número de teléfono de la cola de llamadas

Puede proteger la identidad de un usuario cambiando su identificador de llamada para las llamadas salientes a una cola de llamadas en lugar de crear una directiva con el cmdlet **New-CallingLineIdentity**.
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
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

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Una introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Esto es lo que conseguirá con Sistema telefónico en Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
