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
description: Obtenga información sobre cómo configurar y conectar su SBC al enrutamiento directo de sistema telefónico.
ms.openlocfilehash: e20ab921e8f01d8beea15f0b1dd8a50e229f4e91
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099450"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar el controlador de borde de sesión (SBC) al enrutamiento directo

En este artículo se describe cómo configurar un controlador de borde de sesión (SBC) y conectarlo al enrutamiento directo del sistema telefónico.  Este es el paso 1 de los siguientes pasos para configurar el enrutamiento directo:

- **Paso 1. Conectar el SBC con sistema telefónico y validar la conexión** (en este artículo)
- Paso 2. [Habilitar usuarios para enrutamiento directo](direct-routing-enable-users.md)
- Paso 3. [Configurar el enrutamiento de llamadas](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

Puede usar el Centro [de administración de Microsoft Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) para configurar y conectar un SBC al enrutamiento directo.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Enrutamiento** directo de voz y, a continuación, haga clic  >  en la pestaña **OSBC.**
2. Haga clic en **Agregar**.
3. Escriba un FQDN para la SBC. <br><br>Asegúrese de que la parte del nombre de dominio del FQDN coincide con un dominio que está registrado en su inquilino y tenga en cuenta que el nombre de dominio no es compatible con el nombre de dominio FQDN de `*.onmicrosoft.com` SBC. Por ejemplo, si tiene dos nombres de dominio y `contoso.com` `contoso.onmicrosoft.com` use como nombre `sbc.contoso.com` SBC. Si usa un subdominio, asegúrese de que este subdominio también está registrado en su inquilino. Por ejemplo, si desea `sbc.service.contoso.com` usarlo, debe `service.contoso.com` registrarse.
4. Configure las siguientes opciones para el SBC en función de las necesidades de su organización. Para obtener más información sobre cada una de estas opciones de configuración, consulte [configuración SBC.](#sbc-settings)

    ![Captura de pantalla de la página Agregar SBC en el Centro de administración de Microsoft Teams](media/direct-routing-add-sbc.png)

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="using-powershell"></a>Con PowerShell

Para conectar su SBC a enrutamiento directo, tendrá que:

1. [Conéctese a Skype Empresarial Online con PowerShell.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Conecte el SBC al inquilino.](#connect-the-sbc-to-the-tenant)
3. [Compruebe la conexión SBC.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectarse a Skype Empresarial Online con PowerShell

Puede usar una sesión de PowerShell conectada al inquilino para emparejar el SBC con la interfaz de enrutamiento directo. Para abrir una sesión de PowerShell, siga los pasos indicados en [Configurar el equipo para Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
Después de establecer una sesión de PowerShell remota, compruebe que puede ver los comandos para administrar la SBC. Para comprobar los comandos, escriba o copie y pegue el comando siguiente en la sesión de PowerShell y, después, presione Entrar: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

El comando devuelve las cuatro funciones que se muestran aquí que le permitirán administrar la SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Conectar la SBC al inquilino

Use el [cmdlet New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para conectar el SBC al inquilino. En una sesión de PowerShell, escriba lo siguiente y, después, presione Entrar:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Le recomendamos que establezca un límite máximo de llamadas en el SBC con información que se pueda encontrar en la documentación de SBC. El límite desencadenará una notificación si el SBC se encuentra en el nivel de capacidad.
  > 2. Solo puede conectar la SBC si la parte del dominio de su FQDN coincide con uno de los dominios registrados en su inquilino, excepto \* .onmicrosoft.com. El \* uso de .onmicrosoft.com nombres de dominio no es compatible con el nombre FQDN de SBC. Por ejemplo, si tiene dos nombres de dominio, **contoso.com** y **contoso**.onmicrosoft.com, puede usar sbc.contoso.con para el nombre SBC. Si intenta conectar la SBC con un nombre como sbc.contoso.abc, el sistema no le permitirá, ya que el dominio no es propiedad de este inquilino.<br/>
  > Además del dominio registrado en su inquilino, es importante que haya un usuario con ese dominio y una licencia E3 o E5 asignada. Si no es así, recibirá el siguiente error:<br/>
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
> En este ejemplo solo se muestran los parámetros mínimos necesarios. Hay parámetros adicionales que puede establecer con el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) durante el proceso de conexión. Para obtener más información, vea [Configuración de SBC.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Comprobar la conexión SBC

Para comprobar la conexión:

- [Compruebe si la SBC está en la lista de](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)SBC emparejadas.
- [Validar las opciones SIP.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Comprobar si la SBC está en la lista de OBC emparejadas

Después de conectar el SBC, use el cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) para comprobar que el SBC está en la lista de SBC emparejados. Escriba lo siguiente en una sesión remota de PowerShell y, después, presione Entrar:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

La puerta de enlace emparejada debería aparecer en la lista, como se muestra en el ejemplo siguiente, y el parámetro **Enabled** debe mostrar el valor **True.**

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

#### <a name="validate-sip-options"></a>Validar las opciones de SIP

Para validar el emparejamiento mediante opciones SIP salientes, use la interfaz de administración SBC y confirme que la SBC recibe 200 respuestas de aceptar a sus mensajes de OPCIONES salientes.

Cuando enrutamiento directo ve opciones entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN SBC configurado en el campo del encabezado de contacto en el mensaje OPCIONES entrantes. 

Para validar el emparejamiento mediante opciones SIP entrantes, use la interfaz de administración SBC y vea que SBC envía una respuesta a los mensajes OPTIONS procedentes de enrutamiento directo y que el código de respuesta que envía es 200 aceptar.

## <a name="sbc-settings"></a>Configuración de SBC

Esta tabla enumera las opciones que puede establecer para el SBC en el Centro de administración de Microsoft Teams y mediante el cmdlet [New-CsOnlinePSTNGateway.](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)

|¿Obligatorio?|Configuración del Centro de administración de Microsoft Teams|Parámetro de PowerShell|Descripción|Valor predeterminado|Valores posibles|Tipo y restricciones|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sí|**Agregar un FQDN para la SBC**|FQDN |Ninguna|Nombre de FQDN, límite de 63 caracteres|Cadena, consulte la lista de caracteres permitidos y no permitidos en las convenciones de nomenclatura en Active Directory para [equipos, dominios,](https://support.microsoft.com/help/909264) sitios y OUs|
|No|**Habilitado**|Habilitado|Se usa para activar el SBC para las llamadas salientes. Puede usar esto para quitar temporalmente la SBC del servicio mientras se actualiza o durante el mantenimiento. |Falso|Verdadero<br/>Falso|Boolean|
|Sí|**Puerto de señalización SIP**|SipSignalingPort |Este es el puerto de escucha que se usa para comunicarse con enrutamiento directo mediante el protocolo de capa de transporte (TLS).|Ninguna|Cualquier puerto|0 a 65535 |
|No|**Opciones de enviar SIP**|SendSIPOptions |Define si SBC enviará mensajes de opciones SIP. Es muy recomendable que active esta configuración. Si esta configuración está desactivada, la SBC se excluye del sistema de supervisión y alertas.|True|True<br/>Falso|Boolean|
|No|**Historial de llamadas de reenvío**|ForwardCallHistory |Indica si la información del historial de llamadas se reenvía a través del tronco. Al activar esta opción, el proxy de Microsoft 365 u Office 365 envía un encabezado con la información del historial y se le hace referencia. |Falso|Verdadero<br/>Falso|Boolean|
|No|**Encabezado de identidad P (PAI) reenviado**|ForwardPAI|Indica si el encabezado PAI se reenvía con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada. Si esta configuración está en línea, también se envía el encabezado Privacy:ID.|Falso|Verdadero<br/>Falso|Boolean|
|No|**Capacidad de llamadas simultáneas**|MaxConcurrentSessions |Al establecer un valor, el sistema de alertas le notificará cuando el número de sesiones simultáneas sea el 90 por ciento o superior a este valor. Si no establece un valor, no se generarán alertas. Sin embargo, el sistema de supervisión informará del número de sesiones simultáneas cada 24 horas. |Nulo|Nulo<br/>De 1 a 100 000 ||
|No|**Códigos de respuesta a conmutación por error**|FailoverResponseCodes<br>|Si el enrutamiento directo recibe un código de error 4xx o 6xx SIP en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada desde un cliente de Teams a la RTC con flujo de tráfico: cliente de Teams -> Enrutamiento directo -> SBC -> red telefónica). Al especificar un código de respuesta de conmutación por error, esto obliga al enrutamiento directo a probar otro SBC (si existe otro SBC en la directiva de enrutamiento de voz del usuario) cuando reciba los códigos especificados si la SBC no puede realizar una llamada debido a problemas de red u otros problemas. Para obtener más información, consulte [Conmutación por error de códigos SIP específicos recibidos desde el controlador de borde de sesión (SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|No|**Horas de conmutación por error (segundos)**|FailoverTimeSeconds |Cuando establece un valor, las llamadas salientes que la puerta de enlace no responde dentro del tiempo establecido se enrutan al siguiente tronco disponible. Si no hay troncos adicionales, la llamada se descarta automáticamente. El valor predeterminado es 10 segundos. En una organización con redes lentas y respuestas de puerta de enlace, esto podría provocar potencialmente que las llamadas se desasejar innecesariamente.|10|Número|Int|
|No|**País o región preferidos para el tráfico multimedia**|MediaRerouroutingLocationOverride |Se usa para configurar manualmente el país o la región que prefiera para el tráfico multimedia. Le recomendamos que lo establezca solo si los registros de llamadas indican claramente que la asignación predeterminada del centro de datos para la ruta de acceso multimedia no usa la ruta más cercana al centro de datos SBC. De forma predeterminada, enrutamiento directo asigna un centro de datos según la dirección IP pública del SBC y siempre selecciona la ruta de acceso más cercana al centro de datos SBC. Sin embargo, en algunos casos, la ruta predeterminada podría no ser la ruta óptima. Este parámetro le permite establecer manualmente la región preferida para el tráfico multimedia. |Ninguna|Códigos de país en formato ISO||
|No|**SBC admite PIDF/LO para llamadas de emergencia**|PidfloSupported|Especifique si SBC admite el objeto de ubicación de formato de datos de información de presencia (PIDF/LO) para las llamadas de emergencia.||||
|No|**Llamar al teléfono mientras se intenta encontrar al usuario**|GenerateRingingWhileLocatingUser|Establezca si se reproduce una señal de audio al autor de la llamada para indicar que Teams está en proceso de establecer la llamada. Esta configuración solo se aplica al enrutamiento directo en modo de omisión que no es multimedia. A veces, las llamadas entrantes desde los clientes de RTC a Teams pueden tardar más de lo esperado en establecerse. Cuando esto sucede, es posible que el autor de la llamada no oiga nada, que el cliente de Teams no suene y que algunos proveedores de telecomunicaciones cancelen la llamada. Esta configuración ayuda a evitar silencios inesperados que se pueden producir en estos escenarios.|True|True<br/>Falso|Boolean|
|No| - |MediaBypass|Esta configuración indica si la SBC admite la omisión de medios y si desea usarla para esta SBC. |Ninguna|Verdadero<br/>Falso|Boolean|

## <a name="see-also"></a>Consulte también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)
