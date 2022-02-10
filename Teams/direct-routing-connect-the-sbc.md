---
title: Conectar controlador de borde de sesión (SBC) a Enrutamiento directo
ms.reviewer: fillipse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar y conectar su SBC a Teams Sistema telefónico enrutamiento directo.
ms.openlocfilehash: 7983fa176fec5e4921db169e1e92a6f6ebc2f2a7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518722"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar controlador de borde de sesión (SBC) a Enrutamiento directo

En este artículo se describe cómo configurar un controlador de borde de sesión (SBC) y conectarlo al enrutamiento directo.  Este es el paso 1 de los pasos siguientes para configurar enrutamiento directo:

- **Paso 1. Conectar su SBC con Sistema telefónico y valide la conexión** (este artículo)
- Paso 2. [Habilitar usuarios para enrutamiento directo](direct-routing-enable-users.md)
- Paso 3. [Configurar el enrutamiento de llamadas](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md)

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo](direct-routing-configure.md).

Puede usar el centro [Microsoft Teams de administración](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) para configurar y conectar un SBC al enrutamiento directo.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Enrutamiento** **de VoiceDirect** >  y, a continuación, haga clic en la pestaña **SBC**.

2. Haga clic en **Agregar**.

3. Escriba un FQDN para el SBC. <br><br>Asegúrese de que la parte del nombre de dominio del FQDN `*.onmicrosoft.com` coincida con un dominio registrado en el inquilino y tenga en cuenta que el nombre de dominio no es compatible con el nombre de dominio FQDN de SBC. Por ejemplo, si tiene dos nombres de dominio y `contoso.com` `contoso.onmicrosoft.com`, use `sbc.contoso.com` como nombre de SBC. Si usa un subdominio, asegúrese de que este subdominio también está registrado en el espacio empresarial. Por ejemplo, si quiere usar `sbc.service.contoso.com`, debe `service.contoso.com` registrarse.

4. Configure las siguientes opciones de configuración para el SBC, en función de las necesidades de su organización. Para obtener más información sobre cada una de estas opciones de configuración, vea [Configuración de SBC](#sbc-settings).

    ![Captura de pantalla de agregar página SBC en el Microsoft Teams de administración.](media/direct-routing-add-sbc.png)

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="using-powershell"></a>Con PowerShell

Para conectar su SBC a Enrutamiento directo, tendrá que:

1. [Conectar para Skype Empresarial en línea mediante PowerShell](#connect-to-skype-for-business-online-by-using-powershell).

2. [Conectar el SBC al inquilino](#connect-the-sbc-to-the-tenant).

3. [Compruebe la conexión SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectar usar Skype Empresarial Online con PowerShell

Para emparejar el SBC con la interfaz de enrutamiento directo, use una sesión de PowerShell conectada al inquilino. Para abrir una sesión de PowerShell, siga los pasos descritos en [Configurar el equipo para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Después de establecer una sesión remota de PowerShell, compruebe que puede ver los comandos para administrar el SBC. Para comprobar los comandos, escriba o copie y pegue el siguiente comando en la sesión de PowerShell y, después, presione Entrar: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

El comando devuelve las cuatro funciones que se muestran aquí que le permitirán administrar el SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Conectar el SBC al inquilino

Para conectar el SBC al inquilino, use el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . En una sesión de PowerShell, escriba lo siguiente y, después, presione Entrar:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Le recomendamos que establezca un límite máximo de llamadas en el SBC con información que se puede encontrar en la documentación de SBC. El límite desencadenará una notificación si el SBC está en el nivel de capacidad.
  > 2. Solo puede conectar el SBC si la parte del dominio de su FQDN coincide con uno de los dominios registrados en el espacio empresarial, \*excepto .onmicrosoft.com. El \*uso de .onmicrosoft.com nombres de dominio no es compatible con el nombre FQDN de SBC. Por ejemplo, si tiene dos nombres de dominio, **contoso.com** y **contoso.onmicrosoft.com**, puede usar sbc.contoso.com para el nombre de SBC. Si intenta conectar el SBC con un nombre como sbc.contoso.abc, el sistema no le permitirá, ya que el dominio no es propiedad de este inquilino.<br/>
  > Además del dominio registrado en el inquilino, es importante que haya un usuario con ese dominio y una licencia E3 o E5 asignada. Si no es así, recibirá el siguiente error:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Aquí se muestra un ejemplo:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Lo que devuelve:

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
> En este ejemplo solo se muestran los parámetros mínimos necesarios. Hay parámetros adicionales que puede establecer con el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) durante el proceso de conexión. Para obtener más información, vea [Configuración de SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Comprobar la conexión SBC

Para comprobar la conexión:

- [Compruebe si el SBC está en la lista de SBC emparejados](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Validar opciones SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Comprobar si el SBC está en la lista de SBC emparejados

Después de conectar el SBC, use el cmdlet [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) para comprobar que el SBC está presente en la lista de SBC emparejados. Escriba lo siguiente en una sesión remota de PowerShell y, después, presione Entrar:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

La puerta de enlace emparejada debería aparecer en la lista como se muestra en el ejemplo siguiente y el parámetro **Habilitado** debería mostrar un valor de **Verdadero**.

Lo que devuelve:

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

#### <a name="validate-sip-options"></a>Validar opciones sip

Para validar el emparejamiento con las opciones SIP salientes, use la interfaz de administración de SBC y confirme que el SBC recibe 200 respuestas de aceptar a sus mensajes DE OPCIONES salientes.

Cuando Enrutamiento directo vea OPCIONES entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN de SBC configurado en el campo Encabezado de contacto en el mensaje OPCIONES entrantes. 

Para validar el emparejamiento con opciones SIP entrantes, use la interfaz de administración de SBC y vea que el SBC envía una respuesta a los mensajes OPTIONS que vienen desde Enrutamiento directo y que el código de respuesta que envía es 200 Aceptar.

## <a name="sbc-settings"></a>Configuración de SBC

En esta tabla se enumeran las opciones que puede establecer para el SBC en el centro de administración de Microsoft Teams y mediante el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway).

|¿Obligatorio?|Teams configuración del Centro de administración|Parámetro de PowerShell|Descripción|Valor predeterminado|Valores posibles|Tipo y restricciones|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sí|**Agregar un FQDN para el SBC**|FQDN |Ninguna|Nombre FQDN, limitar 63 caracteres|Cadena, vea la lista de caracteres permitidos y no permitidos en convenciones de nomenclatura en [Active Directory para equipos, dominios, sitios y us](https://support.microsoft.com/help/909264)|
|No|**Habilitado**|Habilitado|Úsese para activar el SBC para las llamadas salientes. Puede usarlo para quitar temporalmente el SBC del servicio mientras se actualiza o durante el mantenimiento. |Falso|Verdadero<br/>Falso|Boolean|
|Sí|**Puerto de señalización SIP**|SipSignalingPort |Este es el puerto de escucha que se usa para comunicarse con enrutamiento directo mediante el protocolo de capa de transporte (TLS).|Ninguna|Cualquier puerto|De 0 a 65535 |
|No|**Opciones de enviar SIP**|SendSIPOptions |Define si el SBC enviará mensajes de opciones SIP. Le recomendamos que active esta configuración. Cuando esta configuración está desactivada, el SBC se excluye del sistema de supervisión y alertas.|Verdadero|True<br/>Falso|Boolean|
|No|**Historial de llamadas de reenvío**|ForwardCallHistory |Indica si la información del historial de llamadas se reenvía a través del tronco. Al activar esta opción, el Microsoft 365 envía un encabezado History-info y Referred-by. |Falso|Verdadero<br/>Falso|Boolean|
|No|**Encabezado forward P-Asserted-identity (PAI)**|ForwardPAI|Indica si el encabezado PAI se reenvía junto con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada. Si esta configuración está en, también se envía el encabezado Privacy:ID.|Falso|Verdadero<br/>Falso|Boolean|
|No|**Capacidad de llamada simultánea**|MaxConcurrentSessions |Al establecer un valor, el sistema de alertas le notificará cuando el número de sesiones simultáneas sea del 90 por ciento o superior a este valor. Si no establece un valor, las alertas no se generan. Sin embargo, el sistema de supervisión reportará el número de sesiones simultáneas cada 24 horas. |Null|Null<br/>De 1 a 100 000 ||
|No|**Códigos de respuesta de conmutación por error**|FailoverResponseCodes<br>|Si enrutamiento directo recibe cualquier código de error SIP 4xx o 6xx en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada de un cliente Teams a la RTC con flujo de tráfico: un cliente Teams -> enrutamiento directo -> SBC -> red de telefonía). Al especificar un código de respuesta de conmutación por error, esto obliga a Enrutamiento directo a probar otro SBC (si existe otro SBC en la directiva de enrutamiento de voz del usuario) cuando recibe los códigos especificados si el SBC no puede realizar una llamada debido a problemas de red u otros. Para obtener más información, vea [Conmutación por error de códigos SIP específicos recibidos desde el controlador de borde de sesión (SBC).](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Int|
|No|**Horas de conmutación por error (segundos)**|FailoverTimeSeconds |Al establecer un valor, las llamadas salientes que la puerta de enlace no responde en el tiempo que establece se enrutan al siguiente tronco disponible. Si no hay troncos adicionales, la llamada se descarta automáticamente. El valor predeterminado es 10 segundos. En una organización con redes lentas y respuestas de puerta de enlace, esto podría provocar que las llamadas se descartaron innecesariamente.|10|Número|Int|
|No|**País o región preferidos para el tráfico multimedia**|MediaRelayRoutingLocationOverride | No se aplica al enrutamiento directo. Este parámetro está reservado para su uso con operadores administrados en planes de llamadas |Ninguna|||
|No|**SBC admite PIDF/LO para llamadas de emergencia**|PidfloSupported|Especifique si el SBC admite el objeto de ubicación de formato de datos de información de presencia (PIDF/LO) para las llamadas de emergencia.||||
|No| - |MediaBypass|Esta configuración indica si el SBC admite la omisión de medios y si desea usarla para este SBC. |Ninguna|Verdadero<br/>Falso|Boolean|

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)
