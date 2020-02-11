---
title: Configurar el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 86406af88648d367f02fd420c9ba278bdfd47185
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888599"
---
# <a name="configure-direct-routing"></a>Configurar el enrutamiento directo

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo y cómo implementarlo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

Si aún no lo ha hecho, lea [planear el enrutamiento directo](direct-routing-plan.md) de los requisitos previos y revisar otros pasos que debe realizar antes de configurar la red del sistema de Microsoft Phone. 

En este artículo se describe cómo configurar el enrutamiento directo de Microsoft Phone System. Explica cómo emparejar un controlador de borde de sesión (SBC) compatible con el enrutamiento directo y cómo configurar los usuarios de Microsoft Teams para que usen el enrutamiento directo para conectarse a la red de telefonía pública conmutada (RTC). Para completar los pasos que se explican en este artículo, los administradores deben estar familiarizados con los cmdlets de PowerShell. Para obtener más información sobre cómo usar PowerShell, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Le recomendamos que confirme que su SBC ya se ha configurado tal y como recomienda su proveedor de SBC: 

- [Documentación de la implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de la implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Puede configurar el sistema de Microsoft Phone y permitir que los usuarios usen el enrutamiento directo y, a continuación, configurar Microsoft Teams como el cliente de llamadas preferido completando los siguientes procedimientos: 

- [Emparejar el SBC con un sistema telefónico de Microsoft y validar el emparejamiento](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Habilitar a los usuarios para el servicio de enrutamiento directo](#enable-users-for-direct-routing-service)
- Asegúrese de que Microsoft Teams es el cliente de llamadas preferido para los usuarios

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Emparejar la SBC al servicio de enrutamiento directo del sistema telefónico 

Estos son los tres pasos de alto nivel que permiten conectar, o emparejar, la SBC a la interfaz de enrutamiento directo: 

1. Conectarse al centro **de administración de Skype empresarial online** con PowerShell 
2. Emparejar la SBC 
3. Validar el emparejamiento 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectarse a Skype empresarial online con PowerShell 

Puede usar una sesión de PowerShell conectada al espacio empresarial para emparejar el SBC a la interfaz de enrutamiento directo. Para abrir una sesión de PowerShell, siga los pasos descritos en [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Después de establecer una sesión de PowerShell remota, compruebe que puede ver los comandos para administrar la SBC. Para validar los comandos, escriba o copie y pegue lo siguiente en la sesión de PowerShell y presione ENTRAR: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

El comando devolverá las cuatro funciones mostradas aquí que le permitirán administrar el SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Emparejar el SBC con el inquilino 

Para emparejar el SBC con el inquilino, en la sesión de PowerShell escriba lo siguiente y presione ENTRAR: 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Se recomienda establecer un límite máximo de llamadas en la SBC mediante la información que se puede encontrar en la documentación de SBC. El límite desencadenará una notificación si el SBC está en el nivel de capacidad.
  > 2. Solo puede emparejar el SBC si la parte de dominio de su FQDN coincide con uno de los dominios registrados en su inquilino \*, excepto. onmicrosoft.com. No \*se admite el uso de nombres de dominio. onmicrosoft.com para el nombre FQDN de SBC. Por ejemplo, si tiene dos nombres de dominio:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Para el nombre de SBC, puede usar el nombre sbc.contoso.com. Si intenta emparejar la SBC con un nombre SBC. contoso. ABC, el sistema no le permitirá, ya que el dominio no pertenece a este inquilino.<br/>
  > Además del dominio registrado en su inquilino, es importante que haya un usuario con ese dominio y una licencia de E3 o E5 asignada. De lo contrario, recibirá el siguiente error:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
Devuelve
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Hay opciones adicionales que se pueden establecer durante el proceso de emparejamiento. En el ejemplo anterior, sin embargo, solo se muestran los parámetros mínimos necesarios. 
 
En la tabla siguiente se enumeran los parámetros adicionales que puede usar para establecer ```New-CsOnlinePstnGateway```parámetros para.

|¿Obligatorio?|Nombre|Descripción|Valor predeterminado|Valores posibles|Tipo y restricciones|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Sí|FQDN|El nombre FQDN de SBC |Ninguna|NoneFQDN nombre, limitar 63 caracteres|Cadena, lista de caracteres permitidos y no permitidos en las [convenciones de nomenclatura de Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/help/909264)|
|No|MediaBypass |El parámetro indicado para SBC admite la omisión de medios y el administrador quiere usarlo.|Ninguna|Verdadero<br/>Falso|Boolean|
|Sí|SipSignalingPort |Puerto de escucha usado para comunicarse con los servicios de enrutamiento directo mediante el protocolo seguridad de la capa de transporte (TLS).|Ninguna|Cualquier puerto|0 a 65535 |
|No|FailoverTimeSeconds |Cuando se establece en 10 (valor predeterminado), las llamadas salientes que no responden a la puerta de enlace en 10 segundos se enrutan al siguiente tronco disponible; Si no hay más troncos, la llamada se elimina automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente. El valor predeterminado es 10.|base10|Número|ENT|
|No|ForwardCallHistory |Indica si la información del historial de llamadas se reenviará a través del tronco. Si está habilitado, el proxy RTC de Office 365 envía dos encabezados: historial-información y referencia. El valor predeterminado es **false** ($false). |Falso|Verdadero<br/>Falso|Boolean|
|No|ForwardPAI|Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada. Si Habilitaste, también se enviará el encabezado privacidad: ID. El valor predeterminado es **false** ($false).|Falso|Verdadero<br/>Falso|Boolean|
|No|SendSIPOptions |Define si un SBC o no enviará las opciones de SIP. Si se deshabilita, la SBC se excluirá del sistema de supervisión y alertas. Le recomendamos encarecidamente que habilite las opciones de SIP. El valor predeterminado es **true**. |True|True<br/>Falso|Boolean|
|No|MaxConcurrentSessions |Utilizado por el sistema de alertas. Cuando se establece un valor, el sistema de alertas generará una alerta para el administrador de inquilinos cuando el número de sesión simultánea sea 90% o superior a este valor. Si el parámetro no se establece, no se generan alertas. Sin embargo, el sistema de supervisión informará de la cantidad de sesiones simultáneas cada 24 horas. |Valor|Valor<br/>de 1 a 100.000 ||
|No|MediaRelayRoutingLocationOverride |Permite seleccionar la ruta de acceso para los medios de forma manual. El enrutamiento directo asigna un centro de recursos para la ruta de medios según la IP pública de SBC. Siempre seleccionamos el centro de recursos de SBC más cercano. Sin embargo, en algunos casos, una IP pública de, por ejemplo, un rango de Estados Unidos se puede asignar a un SBC ubicado en Europa. En este caso, usaremos una ruta de medios no óptima. Este parámetro permite establecer manualmente la región preferida para el tráfico de medios. Solo se recomienda establecer este parámetro si los registros de la llamada indican claramente que la asignación automática del centro de recursos para la ruta multimedia no asigna el más cercano al centro de recursos de SBC. |Ninguna|Códigos de países en formato ISO||
|No|Habilitado|Permite habilitar esta SBC para llamadas salientes. Puede usarse para quitar temporalmente el SBC, mientras se actualiza o durante el mantenimiento. |Falso|Verdadero<br/>Falso|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>Comprobar el emparejamiento de SBC 

Compruebe la conexión: 
- Compruebe si la SBC está en la lista de SBCs emparejado. 
- Validar las opciones del SIP. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Validar si el SBC está en la lista de SBCs emparejado 

Después de emparejar el SBC, valide que la SBC esté presente en la lista de SBCs emparejada ejecutando el siguiente comando en una sesión remota de PowerShell:`Get-CSOnlinePSTNGateway`

La puerta de enlace emparejada debe aparecer en la lista, tal y como se muestra en el ejemplo siguiente, y comprobar que el parámetro **Enabled** muestra el valor **true**. Introducir

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Que devuelve:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>Validar el flujo de opciones del SIP 

Para validar el emparejamiento mediante las opciones de SIP salientes, use la interfaz de administración de SBC y confirme que el SBC recibe 200 respuestas correctas a sus mensajes de opciones salientes.

Cuando el enrutamiento directo ve opciones entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje opciones de entrada. 

Para validar el emparejamiento con las opciones del SIP entrante, use la interfaz de administración de SBC y vea que el SBC envía una respuesta a las opciones mensajes entrantes desde el enrutamiento directo y que el código de respuesta que envía es 200 aceptar.

## <a name="enable-users-for-direct-routing-service"></a>Habilitar a los usuarios para el servicio de enrutamiento directo 

Cuando esté listo para habilitar a los usuarios para el servicio de enrutamiento directo, siga estos pasos: 

1. Cree un usuario en Office 365 y asigne una licencia de sistema telefónico. 
2. Asegúrese de que el usuario se ha alojado en Skype empresarial online. 
3. Configure el número de teléfono y habilite la telefonía IP empresarial y el buzón de voz. 
4. Configurar el enrutamiento de voz. La ruta se valida automáticamente.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Crear un usuario en Office 365 y asignar la licencia 

Hay dos opciones para crear un nuevo usuario en Office 365. Sin embargo, recomendamos que su organización seleccione y use una opción para evitar problemas de enrutamiento: 

- Crear el usuario en Active Directory local y sincronizar el usuario con la nube. Consulte [integrar los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Cree el usuario directamente en el portal de administrador de Office 365. Consulte [Agregar usuarios individualmente o de forma masiva a Office 365: ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Si su implementación de Skype empresarial online coexiste con Skype empresarial 2015 o Lync 2010/2013 local, la única opción admitida es crear el usuario en Active Directory local y sincronizar el usuario con la nube (opción 1). 

Para obtener información sobre los requisitos de licencia, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [planificar enrutamiento directo](direct-routing-plan.md).

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Comprobar que el usuario se ha alojado en Skype empresarial online 

El enrutamiento directo requiere que el usuario se base en Skype empresarial online. Para comprobarlo, consulta el parámetro RegistrarPool. Debe tener un valor en el dominio infra.lync.com.

1. Conéctese a PowerShell remoto.
2. Emita el comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurar el número de teléfono y habilitar la telefonía IP empresarial y el buzón de voz 

Una vez que haya creado el usuario y le haya asignado una licencia, el siguiente paso es configurar su número de teléfono y el buzón de voz. Esto se puede hacer en un solo paso. 

Para agregar el número de teléfono y habilitar el buzón de voz:
 
1. Conectarse a una sesión de PowerShell remota. 
2. Escribe el comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    Por ejemplo, para añadir un número de teléfono para el usuario "Spencer Low", tendría que escribir lo siguiente: 

    ```PowerShell
    Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    El número de teléfono usado debe configurarse como un número de teléfono E. 164 completo con prefijo internacional. 

      > [!NOTE]
      > Si el número de teléfono del usuario se administra localmente, use el shell local de administración de Skype empresarial o el panel de control para configurar el número de teléfono del usuario. 

### <a name="configure-voice-routing"></a>Configurar el enrutamiento de voz 

Microsoft Phone System tiene un mecanismo de enrutamiento que permite que se envíe una llamada a un SBC específico en función de lo siguiente: 

- Patrón de número denominado 
- Se denomina patrón de números + usuario específico que realiza la llamada.
 
SBCs puede designarse como activo y como backup. Eso significa que cuando el SBC configurado como activo para este patrón de número o patrón de número + usuario específico, no está disponible, las llamadas se enrutarán a un SBC de copia de seguridad.
 
El enrutamiento de llamadas consta de los siguientes elementos: 
- Directiva de enrutamiento de voz: contenedor para usos de RTC; puede asignarse a un usuario o a varios usuarios 
- Usos de RTC: contenedor de rutas de voz y usos de RTC; puede compartirse en diferentes directivas de enrutamiento de voz 
- Rutas de voz: patrón de número y conjunto de puertas de enlace RTC en línea para usarlas en las llamadas en las que el número de llamada coincide con el patrón 
- Un puntero de puerta de enlace RTC en línea a un SBC también almacena la configuración que se aplica cuando la llamada se coloca a través de SBC, como reenvío de identidad de aserción de P (PAI) o códecs preferidos; se puede Agregar a las rutas de voz 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Crear una directiva de enrutamiento de voz con un uso de RTC 

En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en el flujo de llamadas.

**Flujo de llamadas 1 (a la izquierda):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se dirige a SBC sbc1.contoso.biz o sbc2.contoso.biz. Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, la llamada se interrumpe. 

**Flujo de llamadas 2 (a la derecha):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz. Si no hay ninguna SBC disponible, se intentará la ruta con prioridad más baja (sbc3.contoso.biz y sbc4.contoso.biz). Si ninguno de los SBCs está disponible, la llamada se corta. 

![Muestra ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueba el SBCs en las rutas en orden aleatorio.

  > [!NOTE]
  > A menos que el usuario también tenga una licencia de plan de llamadas de Microsoft, las llamadas a cualquier número excepto los números que coincidan con los patrones + 1 425 XXX XX XX o + 1 206 XXX XX XX en la configuración de ejemplo se eliminan. Si el usuario tiene una licencia de plan de llamadas, la llamada se redirige automáticamente según las directivas del plan de llamadas de Microsoft. 

El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de plan de llamadas de Microsoft y no requiere configuración de enrutamiento de llamadas adicional.

En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números de Estados Unidos y Canadá (llamadas que van a denominarse patrón de números + 1 XXX XXX XX XX).

![Muestra la Directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática. Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, enrutar a través del plan de llamadas de Microsoft.

Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.

  > [!NOTE]
  > El valor de prioridad para la ruta "otros + 1" no importa en este caso, ya que hay una sola ruta que coincide con el patrón + 1 XXX XXX XX XX. Si un usuario llama a + 1 324 567 89 89 y tanto sbc5.contoso.biz como sbc6.contoso.biz no están disponibles, la llamada se cancela.

En la tabla siguiente se resume la configuración mediante tres rutas de voz. En este ejemplo, las tres rutas forman parte del mismo uso de la RTC "Estados Unidos y Canadá".

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Solo para Estados Unidos|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo para Estados Unidos|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc3.contoso.biz<br/>sbc4.contoso.biz|Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX|
|Solo para Estados Unidos|"Otros + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|||||||

Todas las rutas se asocian con el uso de la RTC "Estados Unidos y Canadá" y el uso de RTC está asociado a la Directiva de enrutamiento de voz "solo para EE. UU.". En este ejemplo, la Directiva de enrutamiento de voz se asigna a User Spencer Low.

#### <a name="examples-of-call-routes"></a>Ejemplos de rutas de llamadas

En el siguiente ejemplo, se muestra cómo configurar rutas, usos de RTC y directivas de enrutamiento, y asignamos la Directiva al usuario.

**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá".

En una sesión de PowerShell remoto de Skype empresarial, escriba:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Valide que el uso se haya creado especificando: 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
Que devuelve una lista de los nombres que se pueden truncar:
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
En el ejemplo siguiente, puede ver el resultado de ejecutar el comando `(Get-CSOnlinePSTNUsage).usage` de PowerShell para mostrar nombres completos (no truncados).

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

**Paso 2:** En una sesión de PowerShell de Skype empresarial online, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, tal y como se detalla en la tabla anterior. 

Para crear la ruta de "Redmond 1", escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Que devuelve:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Para crear la ruta de Redmond 2, escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Para crear la ruta otra + 1, escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida. Puede probarla con este sitio web:[https://www.regexpal.com](https://www.regexpal.com)

En algunos casos, es necesario enrutar todas las llamadas a la misma SBC; Use-NumberPattern ". *"

Enrutar todas las llamadas al mismo SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Confirme que ha configurado correctamente la ruta ejecutando el `Get-CSOnlineVoiceRoute` comando PowerShell con las opciones que se muestran:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Que debería devolver:
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
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "otros + 1". 

**Paso 3:** Crear una directiva de enrutamiento de voz "solo para EE. UU." y agregar a la directiva el uso de la RTC "Estados Unidos y Canadá".

En una sesión de PowerShell en Skype empresarial online, escriba:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

El resultado se muestra en este ejemplo:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Paso 4:** Conceder al usuario Spencer bajo una directiva de enrutamiento de voz con PowerShell.

En una sesión de PowerShell en Skype empresarial online, escriba:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Valide la asignación de directiva escribiendo este comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Que devuelve:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Crear una directiva de enrutamiento de voz con varios usos de RTC

La Directiva de enrutamiento de voz creada anteriormente solo permite llamadas a números de teléfono en Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.

En el ejemplo siguiente, puede crear la Directiva de enrutamiento de voz "sin restricciones". La Directiva reutiliza el uso de la RTC "Estados Unidos y Canadá" creado en el ejemplo anterior, así como el nuevo uso de RTC "internacional". 

Esto enruta todas las demás llamadas a los sbc2.contoso.biz y sbc5.contoso.biz de SBCs. Los ejemplos que se muestran asignan la Directiva solo para usuarios de "Spencer Low", sin restricciones para el usuario "John Woods".

Spencer Low: las llamadas se permiten solo a números de Estados Unidos y Canadá. Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBC. Los números que no son de Estados Unidos no se enrutan a menos que la licencia del plan de llamadas se asigne al usuario.

John Woods: permite realizar llamadas a cualquier número. Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBC. Los números que no sean de Estados Unidos se enrutarán a través de sbc2.contoso.biz y sbc5.contoso.biz.

![Muestra la Directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática. Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, enrutar a través del plan de llamadas de Microsoft.

Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.

![Muestra la Directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

En la siguiente tabla se resumen las denominaciones de uso y las rutas de voz de directivas de enrutamiento "sin restricciones". 

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Solo para Estados Unidos|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Ruta activa para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo para Estados Unidos|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc3.contoso.biz<br/>sbc4.contoso.biz|Ruta de reserva para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo para Estados Unidos|"Otros + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Ruta para números de la llamada + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Ruta para cualquier patrón de números |


  > [!NOTE]
  > - El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental. Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, no se evalúan otros usos. El uso de RTC "internacional" debe situarse después del uso de RTC "solo para EE. UU.". Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Por ejemplo, para cambiar el orden de "Estados Unidos y Canadá" primero por "internacional" y el segundo al orden invertido:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La prioridad de las rutas de voz "otras + 1" y "internacionales" se asigna automáticamente. No importa siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Ejemplo de directiva de enrutamiento de voz para el usuario John Woods

A continuación, se indican los pasos para crear el uso de RTC "internacional", la ruta de voz "internacional", la Directiva de enrutamiento de voz "sin restricciones" y, a continuación, asignarlo al usuario "John Woods".   


**Paso 1**: crear el uso de RTC "internacional". 

En una sesión de PowerShell remoto en Skype empresarial online, escriba:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Paso 2**: crear la nueva ruta de voz "internacional".

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Que devuelve:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Paso 3**: crear una directiva de enrutamiento de voz "sin restricciones". 

El uso de RTC "Redmond 1" y "Redmond" se reutiliza en esta directiva de enrutamiento de voz para mantener un control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Tome nota del orden de uso de RTC:

  a. Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue el conjunto de rutas en "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial. Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.

  b. Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento. Escribe el comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Que devuelve:

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

**Paso 4**: asignar la Directiva de enrutamiento de voz al usuario "John Woods" con el siguiente comando.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

A continuación, verifique la asignación con el comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Que devuelve:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones, y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Asignar el modo solo de Teams a los usuarios para garantizar la superficie de llamadas en Microsoft Teams

El enrutamiento directo requiere que los usuarios estén en el modo solo de equipos para garantizar las llamadas entrantes en el cliente de Teams. Para poner los usuarios en modo de solo equipos, asígnelos a la instancia "UpgradeToTeams" de TeamsUpgradePolicy. Si su organización usa Skype empresarial Server o Skype empresarial online, consulte el artículo siguiente para la interoperabilidad de información entre Skype y Teams: [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurar el envío de llamadas directamente al buzón de voz

El enrutamiento directo le permite finalizar la llamada a un usuario y enviarlo directamente al buzón de voz de los usuarios. Si deseas enviar la llamada directamente al buzón de voz, adjunta Opaque = App: el buzón de voz al encabezado URI de la solicitud. Por ejemplo, "SIP: user@yourdomain. com; Opaque = App: buzón de voz".
En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al buzón de voz del usuario directamente.

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>Traducir números de llamador y destinatario para llamadas salientes y entrantes a un formato alternativo

En ocasiones, es posible que los administradores de inquilinos deseen cambiar el número de la persona que llama o la persona que llama para las llamadas entrantes o salientes en función de los patrones creados para garantizar la interoperabilidad con SBCs. Puede configurar una directiva de reglas de traducción de números para traducir los números de llamadas o llamadas a un formato alternativo. Puede usar la Directiva para traducir números para lo siguiente:

- Llamadas entrantes: llamadas de un punto final de la RTC (llamador) a un cliente de Teams (destinatario).
- Llamadas salientes: llamadas de un cliente de Teams (llamador) a un punto final de RTC (destinatario).

La Directiva se aplica en el nivel de SBC. Puede asignar varias reglas de traducción a un SBC, que se aplican en el orden en que aparecen cuando las lista en PowerShell. También puede cambiar el orden de las reglas en la Directiva.

Para crear, modificar, ver y eliminar reglas de manipulación de números, use los cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)y [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Para asignar, configurar y enumerar reglas de manipulación de números en SBCS, use los cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) y [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) junto ```InboundTeamsNumberTranslationRules```con ```InboundPSTNNumberTranslationRules```los ```OutboundTeamsNumberTranslationRules```parámetros ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```,, ```OutboundPSTNNumberTranslationRulesList``` , y.

### <a name="examples"></a>Ejemplos

#### <a name="example-sbc-configuration"></a>Ejemplo de configuración de SBC

Para los escenarios de ejemplo, ejecutamos ```New-CsOnlinePSTNGateway``` el cmdlet para crear la siguiente configuración de SBC.

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Las reglas de traducción asignadas a SBC se resumen en la tabla siguiente.

|Nombre  |Patrón |Traducción  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

En estos casos de ejemplo, tenemos dos usuarios, Alice y Bob. Alicia es un usuario de Teams y su número es + 1 206 555 0100. Bob es un usuario de la RTC y su número es de + 1 425 555 0100.

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Ejemplo 1: llamada entrante a un número de diez dígitos

Bob llama a Alice a través de un número de diez dígitos que no sea el E. 164. Bob marca 2065550100 para comunicarse con Alice.
SBC usa 2065550100 en el RequestURI y en los encabezados y 4255550100 en el encabezado de.

|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:2065550100@sbc.contoso.com|INVITAr sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|Para    |PARA: \<SIP:2065550100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>Ejemplo 2: llamada entrante a un número de cuatro dígitos

Bob llama a Alice con un número de cuatro dígitos. Bob marca 0100 para comunicarse con Alice.
SBC usa 0100 en el RequestURI y en los encabezados y 4255550100 en el encabezado de.

|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:0100@sbc.contoso.com          |INVITAr sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Ejemplo 3: llamada saliente con un número de diez dígitos que no es E. 164 número

Alicia llama a Bob con un número de diez dígitos. Alice marca 425 555 0100 para comunicarse con Bob.
SBC está configurado para usar números de diez dígitos no E. 164 para equipos y usuarios de la RTC.

En este escenario, un plan de marcado traduce el número antes de enviarlo a la interfaz de enrutamiento directo. Cuando Alice escribe 425 555 0100 en el cliente de Teams, el número se traduce a + 14255550100 por el plan de marcado de país. Los números resultantes son una normalización acumulativa de las reglas del plan de marcado y las reglas de traducción de equipos. Las reglas de traducción de Teams quitan el "+ 1" que agregó el plan de marcado.

|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:+14255550100@sbc.contoso.com          |INVITAr sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|Para    |PARA: \<SIP:+14255550100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Ejemplo 4: llamada saliente con un número de cuatro dígitos que no es E. 164 número

Alicia llama a Bob con un número de cuatro dígitos. Alice usa 0100 para comunicarte con Bob desde llamadas o con un contacto.
SBC está configurado para usar números de cuatro dígitos que no son E. 164 para los usuarios de Teams y números de 10 dígitos para usuarios de la RTC. El plan de marcado no se aplica en este escenario.

|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:0100@sbc.contoso.com           |INVITAr sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)
