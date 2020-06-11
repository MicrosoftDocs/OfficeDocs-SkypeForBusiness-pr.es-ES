---
title: Conectar el controlador de borde de sesión (SBC) al enrutamiento directo
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
description: Obtenga información sobre cómo configurar y conectar su SBC al enrutamiento de un sistema telefónico directo.
ms.openlocfilehash: 8ceb4d1811b479fbcdc0d4ca83f4dbc4672227bd
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691266"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar el controlador de borde de sesión (SBC) al enrutamiento directo

En este artículo se describe cómo configurar un controlador de borde de sesión (SBC) y conectarlo al enrutamiento de un sistema telefónico directo.  Este es el paso 1 de los pasos siguientes para configurar el enrutamiento directo:

- **Paso 1. Conectar su SBC con el sistema telefónico y validar la conexión** (este artículo)
- Paso 2. [Habilitar a los usuarios para el enrutamiento directo](direct-routing-enable-users.md)
- Paso 3. [Configurar el enrutamiento de llamadas](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).

Puede usar el [centro de administración de Microsoft Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) para configurar y conectar un SBC para el enrutamiento directo.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, vaya a enrutamiento de **voz**  >  **directo**y, a continuación, haga clic en la pestaña **SBCS** .
2. Haga clic en **Agregar**.
3. Escriba un FQDN para el SBC. <br><br>Asegúrese de que la parte correspondiente al nombre de dominio del FQDN coincide con un dominio que está registrado en su espacio empresarial y tenga en cuenta que el nombre de dominio `*.onmicrosoft.com` FQDN no es compatible con el nombre de dominio FQDN de SBC. Por ejemplo, si tiene dos nombres de dominio `contoso.com` y `contoso.on.microsoft.com` , use `sbc.contoso.com` como nombre de SBC.
4. Configure las siguientes opciones de SBC, en función de las necesidades de su organización. Para obtener más información sobre cada una de estas configuraciones, consulte [configuración de SBC](#sbc-settings).

    ![Captura de pantalla de la página Agregar SBC en el centro de administración de Microsoft Teams](media/direct-routing-add-sbc.png)

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="using-powershell"></a>Con PowerShell

Para conectar su SBC al enrutamiento directo, tendrá que:

1. [Conéctese a Skype empresarial online con PowerShell](#connect-to-skype-for-business-online-by-using-powershell).
2. [Conecte el SBC al inquilino](#connect-the-sbc-to-the-tenant).
3. [Verifica la conexión de SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectarse a Skype empresarial online con PowerShell

Puede usar una sesión de PowerShell conectada al espacio empresarial para emparejar el SBC a la interfaz de enrutamiento directo. Para abrir una sesión de PowerShell, siga los pasos descritos en [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Después de establecer una sesión de PowerShell remota, compruebe que puede ver los comandos para administrar el SBC. Para comprobar los comandos, escriba o copie y pegue el siguiente comando en la sesión de PowerShell y, a continuación, presione ENTRAR: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

El comando devuelve las cuatro funciones que se muestran aquí y que le permitirán administrar el SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Conectar la SBC al espacio empresarial

Use el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para conectar el SBC al inquilino. En una sesión de PowerShell, escriba lo siguiente y, a continuación, presione ENTRAR:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Le recomendamos que establezca un límite máximo de llamadas en el SBC con información que puede encontrarse en la documentación de SBC. El límite desencadenará una notificación si el SBC está en el nivel de capacidad.
  > 2. Solo puede conectar el SBC si la parte de dominio de su FQDN coincide con uno de los dominios registrados en su inquilino, excepto \* . onmicrosoft.com. \*No se admite el uso de nombres de dominio. onmicrosoft.com para el nombre FQDN de SBC. Por ejemplo, si tiene dos nombres de dominio, **contoso**. com y **contoso**. onmicrosoft.com, puede usar SBC. contoso. con para el nombre de SBC. Si intenta conectar el SBC con un nombre como SBC. contoso. ABC, el sistema no le permitirá, ya que el dominio no pertenece a este inquilino.<br/>
  > Además del dominio registrado en su espacio empresarial, es importante que haya un usuario con ese dominio y una licencia E3 o E5 asignada. Si no es así, recibirá el siguiente error:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Aquí se muestra un ejemplo:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Que devuelve:

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

> [!NOTE]
> Este ejemplo muestra solo los parámetros mínimos necesarios. Hay parámetros adicionales que puede establecer con el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) durante el proceso de conexión. Para obtener más información, consulte [configuración de SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Comprobar la conexión de SBC

Para comprobar la conexión:

- [Compruebe si la SBC está en la lista de SBCS emparejado](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Validar las opciones del SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Comprobar si la SBC está en la lista de SBCs emparejado

Después de conectar el SBC, use el cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) para comprobar que el SBC está presente en la lista de SBCS emparejado. Escriba lo siguiente en una sesión remota de PowerShell y, a continuación, presione ENTRAR:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

La puerta de enlace emparejada debe aparecer en la lista, tal y como se muestra en el ejemplo siguiente, y el parámetro **Enabled** debe mostrar el valor **true**.

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

#### <a name="validate-sip-options"></a>Validar las opciones del SIP

Para validar el emparejamiento mediante las opciones de SIP salientes, use la interfaz de administración de SBC y confirme que el SBC recibe 200 respuestas correctas a sus mensajes de opciones salientes.

Cuando el enrutamiento directo ve opciones entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje opciones de entrada. 

Para validar el emparejamiento con las opciones del SIP entrante, use la interfaz de administración de SBC y vea que el SBC envía una respuesta a las opciones mensajes entrantes desde el enrutamiento directo y que el código de respuesta que envía es 200 aceptar.

## <a name="sbc-settings"></a>Configuración de SBC

En esta tabla se enumeran las opciones que puede establecer para SBC en el centro de administración de Microsoft Teams y mediante el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) .

|¿Obligatorio?|Configuración del centro de administración de Microsoft Teams|Parámetro de PowerShell|Descripción|Valor predeterminado|Valores posibles|Tipo y restricciones|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sí|**Agregar un FQDN para el SBC**|FQDN |Ninguna|Nombre de FQDN, límite de 63 caracteres|Cadena, consulte la lista de caracteres permitidos y no permitidos en las [convenciones de nomenclatura de Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/help/909264)|
|No|**Habilitado**|Habilitado|Use esta opción para activar el SBC para las llamadas salientes. Puede usarlo para quitar temporalmente el SBC del servicio mientras se actualiza o durante el mantenimiento. |Falso|Verdadero<br/>Falso|Boolean|
|Sí|**Puerto de señalización SIP**|SipSignalingPort |Este es el puerto de escucha que se usa para comunicarse con el enrutamiento directo mediante el protocolo de nivel de transporte (TLS).|Ninguna|Cualquier puerto|0 a 65535 |
|No|**Enviar opciones de SIP**|SendSIPOptions |Define si el SBC enviará mensajes de opciones SIP. Le recomendamos encarecidamente que Active esta configuración. Cuando esta opción está deshabilitada, la SBC se excluye del sistema de supervisión y alertas.|True|True<br/>Falso|Boolean|
|No|**Reenviar historial de llamadas**|ForwardCallHistory |Indica si la información del historial de llamadas se desvía a través del tronco. Al activar esta opción, el proxy de Microsoft 365 u Office 365 envía un historial de información y un encabezado al que se hace referencia. |Falso|Verdadero<br/>Falso|Boolean|
|No|**Reenviar encabezado de identidad (PAI)**|ForwardPAI|Indica si el encabezado de PAI se reenvía junto con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada. Si esta configuración está activada, también se enviará el encabezado privacidad: identificador.|Falso|Verdadero<br/>Falso|Boolean|
|No|**Capacidad de llamadas simultáneas**|MaxConcurrentSessions |Al establecer un valor, el sistema de alertas le notificará cuando el número de sesiones simultáneas sea 90 por ciento o superior a este valor. Si no establece un valor, no se generan alertas. Sin embargo, el sistema de supervisión informará del número de sesiones simultáneas cada 24 horas. |Valor|Valor<br/>de 1 a 100.000 ||
|No|**Códigos de respuesta de conmutación por error**|FailoverResponseCodes<br>|Si el enrutamiento directo recibe un código de error 4xx o 6xx de SIP en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada de un cliente de equipo a la RTC con flujo de tráfico: el cliente de Teams-> enrutamiento directo-> red de telefonía > de SBC). Al especificar un código de respuesta de conmutación por error, esto fuerza el enrutamiento directo para probar otro SBC (si hay otra SBC en la Directiva de enrutamiento de voz del usuario) cuando recibe los códigos especificados si la SBC no puede realizar una llamada debido a problemas de red o de otro problema. Para obtener más información, consulte [conmutación por error de códigos SIP específicos recibidos desde el controlador de borde de sesión (SBC)](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||ENT|
|No|**Tiempos de conmutación por error (segundos)**|FailoverTimeSeconds |Al establecer un valor, las llamadas salientes que no respondan a la puerta de enlace dentro del tiempo establecido se enrutarán al siguiente tronco disponible. Si no hay más troncos, la llamada se elimina automáticamente. El valor predeterminado es de 10 segundos. En una organización con las redes lentas y las respuestas de puerta de enlace, esto podría dar lugar a que las llamadas se quitaran innecesariamente.|base10|Número|ENT|
|No|**País o región preferidos para el tráfico de medios**|MediaRelayRoutingLocationOverride |Use esta configuración para establecer manualmente el país o la región que prefiera para el tráfico de los medios. Le recomendamos que configure esto solo si los registros de llamadas indican claramente que la asignación predeterminada del centro de recursos para la ruta multimedia no usa la ruta más cercana al centro de recursos de SBC. De forma predeterminada, el enrutamiento directo asigna un centro de recursos basado en la dirección IP pública de SBC y siempre selecciona la ruta más cercana al centro de recursos de SBC. Sin embargo, en algunos casos, es posible que la ruta de acceso predeterminada no sea la ruta de acceso óptima. Este parámetro le permite establecer manualmente la región preferida para el tráfico de medios. |Ninguna|Códigos de países en formato ISO||
|No|**SBC admite PIDF/lo para las llamadas de emergencia**|PidfloSupported|Especifique si el SBC admite el objeto de ubicación de formato de datos de información de presencia (PIDF/lo) para llamadas de emergencia.||||
|No|**Llamar al teléfono al intentar encontrar al usuario**|GenerateRingingWhileLocatingUser|Establece si se reproduce una señal de audio a la persona que llama para indicar que Teams está en proceso de establecer la llamada. Esta configuración solo se aplica al enrutamiento directo en el modo de omisión de medios. A veces, las llamadas entrantes desde la RTC a los clientes de equipos pueden tardar más de lo esperado en establecerse. Cuando esto sucede, es posible que el autor de la llamada no oiga nada, el cliente de Teams no suene y la llamada puede ser cancelada por algunos proveedores de telecomunicaciones. Esta configuración ayuda a evitar los silencios inesperados que se pueden producir en estos escenarios.|True|True<br/>Falso|Boolean|
|No| - |MediaBypass|Esta configuración indica si la SBC admite la omisión de medios y si desea usarlo para este SBC. |Ninguna|Verdadero<br/>Falso|Boolean|

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)
