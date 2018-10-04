---
title: Configurar el enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Obtenga información sobre cómo configurar el enrutamiento directo de Microsoft teléfono del sistema.
ms.openlocfilehash: 7e587c92e979c7985ccbd9f05bbb5ae1115d176a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374653"
---
# <a name="configure-direct-routing"></a>Configurar el enrutamiento directo

Si no lo ha hecho ya, lea [Planear el enrutamiento directo](direct-routing-plan.md) para los requisitos previos y para revisar otros pasos debe realizar antes de configurar la red del sistema de teléfono de Microsoft. 

En este artículo se describe cómo configurar el enrutamiento directo de Microsoft teléfono del sistema. Detalla cómo emparejar un controlador de borde de sesión (SBC) admitidos para el enrutamiento directo y cómo configurar los usuarios de Microsoft Teams para usar el enrutamiento directo para conectarse a la red telefónica pública conmutada (RTC). Para completar los pasos que se explican en este artículo, los administradores necesitan un poco familiarizado con los cmdlets de PowerShell. Para obtener más información acerca del uso de PowerShell, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Se recomienda que confirme que ya se ha configurado la SBC recomendada por su proveedor SBC: 

- Documentación de implementación de AudioCodes 
- Documentación de implementación de comunicaciones de la cinta de opciones

Puede configurar el sistema de teléfono de Microsoft y permiten a los usuarios usar el enrutamiento directo, a continuación, configurar Microsoft Teams como el cliente preferido de la llamada al completar los procedimientos siguientes: 

- [Empareje la SBC con un sistema de teléfono de Microsoft y validar el emparejamiento](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [Habilitar a usuarios para el servicio de enrutamiento directo](#enable-users-for-direct-routing-service)
- [Asegúrese de que Microsoft Teams es el cliente llamado preferido para los usuarios](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a>Empareje la SBC para dirigir el servicio de enrutamiento del sistema de teléfono 

Los siguientes son los tres pasos de alto nivel para permitirle conectarse o emparejar la SBC a la interfaz de enrutamiento directo: 

- Conectarse al centro de administración de **Skype para profesionales en línea** con PowerShell 
- Par el SBC 
- Validar el emparejamiento 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a>Conectarse a Skype para profesionales en línea mediante el uso de PowerShell 

Puede usar una sesión de PowerShell conectado a los inquilinos para emparejar la SBC a la interfaz de enrutamiento directo. Para abrir una sesión de PowerShell, siga los pasos descritos en [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Después de establecer una sesión remota de PowerShell, compruebe que puede ver los comandos para administrar la SBC. Para validar los comandos, escriba o copiar y pegar en las siguientes opciones en la sesión de PowerShell y presione ENTRAR: 

```
gcm *onlinePSTNGateway*
```

El comando devolverá las cuatro funciones que se muestra aquí que le permiten administrar el SBCs. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Par la SBC para el inquilino 

Para emparejar la SBC para el inquilino, en la sesión de PowerShell, escriba lo siguiente y presione ENTRAR: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Se recomienda establecer un límite para el SBC, uso de la información que se encuentra en la documentación de SBC. El límite activará una notificación si SBC está en el nivel de capacidad.
  > 2. Sólo puede emparejar la SBC con FQDN, donde la parte del dominio del nombre coincide con uno de los dominios registrados en el inquilino, excepto \*. onmicrosoft.com. Uso de \*. omicrosoft.com los nombres de dominio no es compatible con los nombres de SBC FQDN. Por ejemplo, si tiene dos nombres de dominio:<br/><br/>
  > .xyz **ABC**<br/>**ABC**. onmicrosoft.com<br/><br/>
  > Para el nombre SBC, puede usar el nombre sbc.abc.xyz. Si se intenta emparejar la SBC con un nombre sbc.xyz.abc, el sistema no le, como el dominio no pertenece a este inquilino.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Devuelve:
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Existen opciones adicionales que se pueden establecer durante el emparejamiento. En el ejemplo anterior, sin embargo, solo la mínima necesaria se muestran los parámetros. 
 
En la siguiente tabla se enumera los parámetros adicionales que puede usar en la configuración de parámetros para *New-CsOnlinePstnGateway*. 

|¿Obligatorio?|Nombre|Descripción|Predeterminado|Valores posibles|Tipo y restricciones|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Sí|FQDN|El nombre FQDN de la SBC |Ninguna|Nombre de NoneFQDN, límite 63 caracteres|Cadena, lista de caracteres permitidos y no permitidos en [las convenciones de nomenclatura en Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/help/909264)|
|No|MediaBypass |El parámetro reservado para uso futuro. Parámetro indicado de la SBC admite el desvío de medios y el administrador desea usarlo.|Ninguna|Verdadero<br/>Falso|Booleano|
|Sí|SipSignallingPort |Puerto de escucha usado para la comunicación con los servicios de enrutamiento directa mediante el protocolo de seguridad de capa de transporte (TLS).|Ninguna|Cualquier puerto|0 a 65535 |
|No|FailoverTimeSeconds |Cuando se establece en 10 (valor predeterminado), las llamadas salientes que no hay respondidas por la puerta de enlace dentro de 10 segundos se enrutan al siguiente tronco disponible; Si no hay ningún troncos adicionales, automáticamente se interrumpe la llamada. En una organización con redes lentas y respuestas a las puertas de enlace, puede tener como resultado interrupciones innecesarias de las llamadas. El valor predeterminado es 10.|10|Número|Int|
|No|ForwardCallHistory |Indica si la información del historial de llamadas se reenviará a través del tronco. Si se habilita, el Proxy de RTC de Office 365 envía dos encabezados: información de historial y remitido por. El valor predeterminado es **False** ($False). |Falso|Verdadero<br/>Falso|Booleano|
|No|ForwardPAI|Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad del autor de la llamada. El valor predeterminado es **False** ($False).|Falso|Verdadero<br/>Falso|Booleano|
|No|SendSIPOptions |Define si un SBC se o no enviará las opciones de SIP. Si deshabilita esta opción, la SBC se excluirán del sistema de supervisión y alertas. Se recomienda encarecidamente que habilite las opciones de SIP. Valor predeterminado es **True**. |True|True<br/>Falso|Booleano|
|No|MaxConcurrentSessions |Usada por el sistema de alertas. Cuando se establece ningún valor, el sistema de alertas generará una alerta para el Administrador de inquilinos cuando el número de sesión simultáneo es 90% o mayor que este valor. Si no se establece el parámetro, no se generan las alertas. Sin embargo, el sistema de supervisión informará número de sesiones simultáneas cada 24 horas. |Null|Null<br/>1 y 100.000. ||
|No|Habilitado *|Se usa para habilitar este SBC para las llamadas salientes. Puede usarse para quitar temporalmente el SBC, mientras se está actualizando o durante el mantenimiento. |Falso|Verdadero<br/>Falso|Booleano|
 
### <a name="verify-the-sbc-pairing"></a>Compruebe el emparejamiento de SBC 

Compruebe la conexión: 
- Compruebe si la SBC está en la lista de SBCs emparejados. 
- Validar las opciones de SIP. 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a>Validar si SBC está en la lista de SBCs emparejados 

Después de par el SBC, validar que el SBC está presente en la lista de SBCs emparejados ejecutando el siguiente comando en una sesión remota de PowerShell:`Get-CSOnlinePSTNGateway`

La puerta de enlace emparejado debe aparecer en la lista tal como se muestra en el ejemplo siguiente y compruebe que el parámetro *Enabled* muestra el valor **True**. Escriba:

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Que devuelve:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>Validar flujo de opciones de SIP 

Para validar el uso de las opciones de SIP saliente emparejamiento, usar la interfaz de administración de SBC y ver que la SBC obtener 200 respuestas Aceptar a las opciones de salida.
  
Cuando el enrutamiento directo ve opciones entrantes, se iniciará salientes opciones de envío para el FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje entrante de opciones. 

Para validar el uso de las opciones de SIP entrantes de emparejamiento, usar la interfaz de administración de SBC y ver que la SBC Obtiene la respuesta en los mensajes de las opciones que provienen de enrutamiento directo y que el código de respuesta es 200 Aceptar.  

## <a name="enable-users-for-direct-routing-service"></a>Habilitar a usuarios para el servicio de enrutamiento directo 

Cuando esté listo para habilitar a los usuarios para el servicio de enrutamiento directa, siga estos pasos: 

1. Crear un usuario en Office 365 y asigna una licencia de sistema de teléfono. 
2. Asegúrese de que el usuario está hospedado en Skype para profesionales en línea. 
3. Configurar el número de teléfono y habilitar correo de voz y enterprise voice. 
4. Configurar enrutamiento de voz. La ruta se validará automáticamente.  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Crear un usuario en Office 365 y asignar la licencia 

Hay dos opciones para crear un nuevo usuario en Office 365. Sin embargo, se recomienda que la organización, seleccione y utilice una opción para evitar problemas de enrutamiento: 

- Crear el usuario en Active Directory local y sincronizar el usuario a la nube. Vea [directorios de integrar su local con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).  
- Crear el usuario directamente en el Portal de administrador de Office 365. Vea [Agregar usuarios individualmente o de forma masiva a Office 365 - ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

  Si se elabora el sistema que coexiste con Skype para 2015 empresarial o Lync 2010 o 2013 local, la única opción compatible es crear el usuario en Active Directory local y sincronizar el usuario a la nube (opción 1). 

Licencias necesarias: 

- Office 365 E3 de empresa (incluidos SfB Plan2, Exchange Plan2 y equipos) + del sistema de teléfono  
- Office 365 Enterprise E5 (incluidos SfB Plan2, Plan2 de Exchange, los equipos y del sistema de teléfono) 

Licencias opcionales: 

- Plan de llamada 
- Audioconferencia 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Asegúrese de que el usuario está hospedado en Skype para profesionales en línea 

Enrutamiento directo requiere que el usuario a estar alojado en Skype para profesionales en línea. Puede comprobarlo mirando el parámetro RegistrarPool. Debe tener un valor en el dominio infra.lync.com.

1. Conectar con PowerShell remoto.
2. Problema el comando: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurar el número de teléfono y habilitar correo de voz y telefonía IP empresarial 

Una vez que haya creado el usuario y asigna una licencia, el siguiente paso es configurar su número de teléfono y correo de voz. Esto puede realizarse en un solo paso. 

Para agregar el número de teléfono y habilitar para correo de voz:
 
1. Conectarse a una sesión remota de PowerShell. 
2. Escriba el comando: 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

Por ejemplo, para agregar un número de teléfono para el usuario "Sergio bajo", escribiría lo siguiente: 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

El número de teléfono utilizado debe configurarse como un número de teléfono E.164 completo con el código de país. 

  > [!NOTE]
  > Si el número de teléfono del usuario se administra en local, use local Skype para Shell de administración de negocio o Panel de Control para configurar el número de teléfono del usuario. 

### <a name="configure-voice-routing"></a>Configurar enrutamiento de voz 

Microsoft Phone System tiene un mecanismo de enrutamiento que permite que una llamada se envíen a un SBC específico en función de: 

- Patrón de número llamado 
- Patrón de número llamado + usuario específico que realiza la llamada
 
SBCs se pueden designar como activo y copia de seguridad. Es decir, cuando la SBC que está configurado como activo para este patrón de número, o patrón de número + usuario específico, no está disponible y, a continuación, se van a enrutar las llamadas a un SBC copia de seguridad.
 
Enrutamiento de llamadas se compone de los siguientes elementos: 
- Directiva de enrutamiento de voz: contenedor de usos de RTC; se pueden asignar a un usuario o a varios usuarios 
- Usos de RTC: contenedor de rutas de voz y los usos de RTC; se pueden compartir en diferentes directivas de enrutamiento de voz 
- Rutas: patrón de número y un conjunto de puertas de enlace RTC en línea que se usará para las llamadas donde número de llamada coincide con el patrón de voz 
- Puerta de enlace de RTC Online - puntero en SBC, también almacena la configuración que se aplica cuando se llama a través de SBC, como hacia delante P-Asserted-Identity (PAI) o códecs preferido; se pueden agregar a las rutas de voz 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Creación de una directiva de enrutamiento de voz con un uso de RTC 

En el siguiente diagrama se muestra dos ejemplos de las directivas de enrutamiento de voz en el flujo de la llamada.

**Llamar al flujo de 1 (a la izquierda):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta a SBC sbc1<span></span>. contoso.biz o sbc2<span></span>. contoso.biz. Si ninguno de los dos sbc1<span></span>. contoso.biz ni sbc2<span></span>. contoso.biz están disponibles, se interrumpe la llamada. 

**2 de flujo de llamadas (a la derecha):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1<span></span>. contoso.biz o sbc2<span></span>. contoso.biz. Si ninguno de los dos SBC está disponible, se intentará la ruta con la prioridad más baja (sbc3<span></span>. contoso.biz y sbc4<span></span>. contoso.biz). Si ninguno de los SBCs están disponible, se interrumpe la llamada. 

![Se muestran ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

En ambos ejemplos, mientras que la ruta de voz se asigna prioridades, el SBCs en las rutas se intentan en orden aleatorio.

  > [!NOTE]
  > A menos que el usuario también dispone de una licencia de llamar a planeación de Microsoft, se quitan las llamadas a cualquier número excepto los números que coincidan con los patrones de + +1 425 XXX XX XX o +1 206 XXX XX XX en el ejemplo de configuración. Si el usuario tiene una licencia de planeación de la llamada, la llamada se enruta automáticamente según las directivas de la planeación de una llamada a Microsoft. 

La planeación de una llamada a Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de llamar a planeación de Microsoft y no requiere la configuración de enrutamiento de llamada adicionales.

En el ejemplo que se muestra en el diagrama siguiente, se agrega una ruta de voz para enviar las llamadas a todos los demás Estados Unidos y Canadá número (llamadas que vaya a patrón de número llamado + 1 XXX XXX XX XX).

![Directiva de enrutamiento con una tercera ruta de voz de muestra](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Para todas las llamadas, si un usuario tiene dos licencias (sistema de teléfono de Microsoft y llamar a planeación de Microsoft), se usa ruta automático. Si no hay nada coincide con los patrones de números en las rutas de voz en línea creadas por el administrador, se enruta a través de una llamada a planeación de Microsoft.

Si el usuario tiene sólo del sistema de teléfono de Microsoft, se interrumpe la llamada porque no hay reglas de coincidencia están disponibles.

  > [!NOTE]
  > El valor de la prioridad de ruta "Otros + 1" no importa en este caso, como hay sólo una ruta que coincide con el patrón + 1 XXX XXX XX XX. Si un usuario realiza una llamada a + 1 324 567 89 89 y sbc5.contoso.biz y sbc6.contoso.biz no están disponibles, se interrumpe la llamada.

La tabla siguiente resume la configuración con tres rutas de voz. En este ejemplo, todas las rutas de tres forman parte de la misma uso de RTC "Nosotros y Canadá".

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|NOSOTROS solo|"Redmond 1"|^\\+ 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Ruta activa para números de llamada +1 425 XXX XX XX o +1 206 XXX XX XX|
|NOSOTROS solo|"Redmond 2"|^\\+ 1 (425\|206)(\d{7})$|2|sbc3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Ruta de reserva para los números llamados +1 425 XXX XX XX o +1 206 XXX XX XX|
|NOSOTROS solo|"Otros + 1"|^\\+ 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Enrutar para números de llamada + 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)|
|||||||

Todas las rutas se asocian con el uso de RTC "Nosotros y Canadá" y el uso de RTC está asociado con la directiva de enrutamiento de voz "Sólo en Estados Unidos." En este ejemplo, se asigna la directiva de enrutamiento de voz al usuario Spencer Low.

#### <a name="examples-of-call-routes"></a>Ejemplos de rutas de llamadas

En el siguiente ejemplo, demostraremos cómo configurar rutas, usos de RTC y las directivas de enrutamiento y se asigne la directiva para el usuario.

**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá".

En un Skype para la sesión de PowerShell remoto empresarial, escriba:

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

Validar que el uso se ha creado escribiendo: 
```
Get-CSOnlinePSTNUsage
``` 
Que devuelve una lista de nombres que es posible que esté truncada:
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
En el ejemplo siguiente, puede ver el resultado de la ejecución del comando de PowerShell *`(Get-CSOnlinePSTNUsage).usage`* para mostrar los nombres completos (no truncados).    
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Paso 2:** En una sesión de PowerShell en Skype para profesionales en línea, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, como se detalla en la tabla anterior. 

Para crear la ruta de "Redmond 1", escriba:

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Que devuelve:
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
Para crear la ruta de Redmond 2, escriba:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Para crear la ruta de otra + 1, escriba:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida. Puede probarla con este sitio Web:[https://www.regexpal.com](https://www.regexpal.com)

En algunos casos es necesario para enrutar todas las llamadas a la misma SBC; Por favor, use - NumberPattern ". *"

- Enrutar todas las llamadas a la misma SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Validar que ha configurado correctamente la ruta mediante la ejecución de la `Get-CSOnlineVoiceRoute` comando de Powershell mediante las opciones tal como se muestra: 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Que se debe devolver:
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

En el ejemplo, la ruta "Otros + 1" automáticamente se asignó prioridad. 

**Paso 3:** Crear una directiva de enrutamiento de voz "Nosotros solo" y agregar a la directiva el uso de RTC "Estados Unidos y Canadá".

En una sesión de PowerShell en Skype para profesionales en línea, escriba:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

En este ejemplo, se muestra el resultado:

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Paso 4:** Conceder al usuario Spence Low una directiva de enrutamiento de voz mediante el uso de PowerShell.

- En una sesión de Powershell en Skype para profesionales en línea, escriba:

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Validar la asignación de directiva, escriba este comando:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Que devuelve:
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Creación de una directiva de enrutamiento de voz con varios usos de RTC

La directiva de enrutamiento de voz creada anteriormente sólo permite las llamadas a números de teléfono en Estados Unidos y Canadá--a menos que la licencia de llamar a planeación de Microsoft también está asignada al usuario.

En el ejemplo siguiente, puede crear la directiva de enrutamiento de voz "No hay restricciones". La directiva vuelve a usar el uso de RTC "Nosotros y Canadá" creado en el ejemplo anterior, así como el uso de RTC nuevo "Internacional". 

Esto distribuye todas las demás llamadas a la sbc2 SBCs<span></span>. contoso.biz y sbc5<span></span>. contoso.biz. Los ejemplos que se muestran asignan directiva de nosotros solo al usuario "Sergio bajo" y sin restricciones al usuario "John Woods."

Sergio baja – permiten llamadas sólo a los números de Estados Unidos y Canadá. Cuando se llama al intervalo de números de Redmond, se debe usar el conjunto específico de SBC. Los números que no son-US no se enrutarán a menos que la licencia de planeación de la llamada se asigna al usuario.

John Woods – permitidas a cualquier número de llamadas. Cuando se llama al intervalo de números de Redmond, se debe usar el conjunto específico de SBC. Los números que no son-US se enrutarán a través de sbc2<span></span>. contoso.biz y sbc5<span></span>. contoso.biz.

![Muestra la directiva de enrutamiento de voz asignada a usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Para todas las llamadas, si un usuario tiene dos licencias (sistema de teléfono de Microsoft y llamar a planeación de Microsoft), se usa ruta automático. Si no hay nada coincide con los patrones de números en las rutas de voz en línea creadas por el administrador, se enruta a través de una llamada a planeación de Microsoft.

Si el usuario tiene sólo del sistema de teléfono de Microsoft, se interrumpe la llamada porque no hay reglas de coincidencia están disponibles.

![Muestra la directiva de enrutamiento de voz asignada a usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

En la siguiente tabla se resume denominación de uso de enrutamiento directiva "Sin restricciones" y rutas de voz. 

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|NOSOTROS solo|"Redmond 1"|^ + 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Ruta activa para los números del destinatario de la llamada +1 425 XXX XX XX o +1 206 XXX XX XX|
|NOSOTROS solo|"Redmond 2"|^ + 1 (425\|206)(\d{7})$|2|sbc3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Ruta de reserva para los números del destinatario de la llamada +1 425 XXX XX XX o +1 206 XXX XX XX|
|NOSOTROS solo|"Otros + 1"|^ + 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|+ 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX) los números de ruta para el destinatario de la llamada|
|International|International|\d+|4|sbc2<span></span>. contoso.biz<br/>sbc5<span></span>. contoso.biz|Ruta para cualquier patrón de número |


  > [!NOTE]
  > - El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental. Los usos se aplican en orden, y si se encuentra una coincidencia en el primer uso, a continuación, otros usos no se evaluarán nunca. El uso de RTC "Internacional" se debe colocar después el uso de RTC "Sólo en EE." Para cambiar el orden de los usos de RTC, vuelva a ejecutar la `Set-CSOnlineRouteRoutingPolicy` comando. <br/>Por ejemplo, para cambiar el orden de "Nosotros y Canadá" ejecutar "Internacional" y el segundo para el orden inverso:<br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La prioridad de las rutas de voz de "caracteres International" y "Otros + 1" se asignan automáticamente. Éstos no importan como que tienen una prioridad inferior que "Redmond 1" y "Redmond 2".

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Ejemplo de directiva de enrutamiento de voz para el usuario John Woods

Los pasos para crear el uso de RTC "Internacional", "Internacional", de la ruta de voz "Sin restricciones," Directiva de enrutamiento de voz y, a continuación, se asigna al usuario "John Woods" son los siguientes.


1. En primer lugar, cree el uso de RTC "Internacional". En una sesión remota de PowerShell en Skype para profesionales en línea, escriba:

   ```
   Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
   ```

2. A continuación, cree la nueva ruta de voz "Internacional".

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   Que devuelve:

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : \d+
   OnlinePstnUsages          : {International}    
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. A continuación, no cree una directiva de enrutamiento de voz "restricciones". El uso de RTC "Redmond 1" y "Redmond" volver a usar en esta directiva de enrutamiento de voz para conservar un tratamiento especial para las llamadas al número "XX XX de XXX +1 425" y "XX XX de XXX +1 206" como llamadas locales o local.

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   Que devuelve

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. Asignar la directiva de enrutamiento de voz para el usuario "John Woods" mediante el siguiente comando.

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   A continuación, compruebe la asignación mediante el comando:   

   ```
   Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
   ```
   Que devuelve:

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

El resultado es que la directiva de voz que se aplican a las llamadas de John Woods se sin restricciones y va a seguir la lógica de enrutamiento de llamadas disponible para llamadas de Estados Unidos, Canadá e internacional.

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a>Establecer Teams Microsoft como cliente llamado preferido para los usuarios

Sólo enrutamiento directa enruta las llamadas a y desde los usuarios si utilizan al cliente de los equipos. Si su organización sólo usa los equipos, "Equipos sólo" modo en la directiva de actualización se recomienda establecer. Si su organización usa Skype para Business Server o Skype para profesionales en línea, consulte el siguiente artículo para obtener más información y seleccione la opción adecuada: [comprender la coexistencia y actualización de viaje para Skype para profesionales y los equipos](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 


## <a name="see-also"></a>Vea también

[Planeación de enrutamiento directo](direct-routing-plan.md)
