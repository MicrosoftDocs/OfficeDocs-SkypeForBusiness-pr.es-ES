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
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158020"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar el controlador de borde de sesión (SBC) al enrutamiento directo 

En este artículo se describe cómo conectar el controlador de borde de sesión (SBC) al enrutamiento directo del sistema.  Este es el paso 1 de los pasos siguientes para configurar el enrutamiento directo:

- **Paso 1. Conectar su SBC con el sistema telefónico y validar la conexión** (este artículo)
- Paso 2. [Habilitar a los usuarios para el enrutamiento directo](direct-routing-enable-users.md)
- Paso 3. [Configurar el enrutamiento de llamadas](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).

Para conectar su SBC al enrutamiento directo, tendrá que: 

1. Conéctese al centro de administración de **Skype empresarial online** con PowerShell.            
2. Conecte el SBC al inquilino.
3. Validar la conexión. 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectarse a Skype empresarial online con PowerShell 

Puede usar una sesión de PowerShell conectada al espacio empresarial para emparejar el SBC a la interfaz de enrutamiento directo. Para abrir una sesión de PowerShell, siga los pasos descritos en [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Después de establecer una sesión de PowerShell remota, compruebe que puede ver los comandos para administrar el SBC. Para validar los comandos, escriba o copie y pegue el siguiente comando en la sesión de PowerShell y presione ENTRAR: 

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


## <a name="connect-the-sbc-to-the-tenant"></a>Conectar la SBC al espacio empresarial 

Para conectar el SBC al inquilino, en la sesión de PowerShell escriba lo siguiente y presione ENTRAR: 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft recomienda establecer un límite máximo de llamadas en la SBC mediante la información que se puede encontrar en la documentación de SBC. El límite desencadenará una notificación si el SBC está en el nivel de capacidad.
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
Existen opciones adicionales que pueden establecerse durante el proceso de conexión. En el ejemplo anterior, sin embargo, solo se muestran los parámetros mínimos necesarios. 
 
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
|No|MaxConcurrentSessions |Utilizado por el sistema de alertas. Cuando se establece un valor, el sistema de alertas generará una alerta para el administrador de inquilinos cuando el número de sesiones simultáneas sea 90% o superior a este valor. Si no se establece el parámetro, no se generarán las alertas. Sin embargo, el sistema de supervisión informará de la cantidad de sesiones simultáneas cada 24 horas. |Valor|Valor<br/>de 1 a 100.000 ||
|No|MediaRelayRoutingLocationOverride |Permite seleccionar la ruta de acceso para los medios de forma manual. El enrutamiento directo asigna un centro de recursos para la ruta de medios según la IP pública de SBC. Siempre seleccionamos el centro de recursos de SBC más cercano. Sin embargo, en algunos casos, una IP pública de, por ejemplo, un rango de Estados Unidos puede asignarse a un SBC ubicado en Europa. En este caso, usaremos una ruta de medios no óptima. Este parámetro permite establecer manualmente la región preferida para el tráfico de medios. Microsoft solo recomienda establecer este parámetro si los registros de la llamada indican claramente que la asignación automática del centro de recursos para la ruta multimedia no asigna el más cercano al centro de recursos de SBC. |Ninguna|Códigos de países en formato ISO||
|No|Habilitado|Permite habilitar esta SBC para llamadas salientes. Puede usarse para quitar temporalmente la SBC mientras se actualiza o durante el mantenimiento. |Falso|Verdadero<br/>Falso|Boolean|
 
## <a name="verify-the-sbc-connection"></a>Comprobar la conexión de SBC 

Para comprobar la conexión: 
- Compruebe si la SBC está en la lista de SBCs emparejado. 
- Validar las opciones del SIP. 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Comprobar si la SBC está en la lista de SBCs emparejado 

Después de conectar el SBC, valide que la SBC esté presente en la lista de SBCs emparejada ejecutando el siguiente comando en una sesión remota de PowerShell: 

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

### <a name="validate-sip-options-flow"></a>Validar el flujo de opciones del SIP 

Para validar el emparejamiento mediante las opciones de SIP salientes, use la interfaz de administración de SBC y confirme que el SBC recibe 200 respuestas correctas a sus mensajes de opciones salientes.

Cuando el enrutamiento directo ve opciones entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje opciones de entrada. 

Para validar el emparejamiento con las opciones del SIP entrante, use la interfaz de administración de SBC y vea que el SBC envía una respuesta a las opciones mensajes entrantes desde el enrutamiento directo y que el código de respuesta que envía es 200 aceptar.


## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
