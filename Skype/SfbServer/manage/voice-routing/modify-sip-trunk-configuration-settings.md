---
title: Modificar las opciones de configuración del tronco SIP en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: d8cc9dd36bde05b60f95ed9369eaa80e4cd8668f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223293"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificar las opciones de configuración del tronco SIP en Skype para Business Server

Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo (RTCP) de control de transporte en tiempo real.
- Si se requiere cifrado del protocolo seguro en tiempo real (SRTP) en cada tronco.

Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Cualquiera de estas colecciones puede modificarse más adelante mediante puede ser la Skype para el Panel de Control de servidor empresarial o Windows PowerShell.

Al modificar las opciones de configuración de tronco SIP con el Skype para el Panel de Control de servidor de servidor empresarial, las siguientes opciones están disponibles para usted:

|Valor de IU |Parámetro de PowerShell |Descripción |
|--|--|--|
|Nombre|Identity|Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.|
|Descripción|Description|Proporciona un método para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).|
|Número máximo de diálogos iniciales admitidos|MaxEarlyDialogs|Cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.|
|Nivel de compatibilidad de cifrado|SRTPMode|Indica el nivel de compatibilidad para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio. Para los casos de omisión de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. Configuración de medios se establece mediante el uso de los cmdlets New-CsMediaConfiguration y Set-CsMediaConfiguration.<br/>Los valores permitidos son:<br/><br/>**Obligatorio**: debe usarse el cifrado SRTP.<br/>**Opcional**: se utilizará SRTP si la puerta de enlace lo admite.<br/>**No se admiten**: el cifrado SRTP no se admite y, por tanto, no se podrá utilizar.<br/><br/>El SRTPMode se usa solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, SRTPMode se configura internamente como No admitido.|
|Compatibilidad con referencias|Enable3pccRefer<br/>EnableReferSupport|Si se establece en **Habilitar referencias de envío a la puerta de enlace**, indica que el tronco admite la recepción de Solicitudes de referencia del Servidor de mediación.<br/>Si se establece en en **Habilitar referencia mediante el control de llamadas a terceros**, indica que se puede usar el protocolo 3pcc para permitir llamadas transferidas para omitir el sitio hospedado. 3pcc también se conoce como "control de terceros" y ocurre cuando se usa un tercero para conectar un par de personas que llaman (por ejemplo, un operador que realiza una llamada de la persona A a una persona B).|
|Habilitar omisión de medios|EnableBypass|Indica si la omisión de medios está habilitada para este tronco. La omisión de medios solo puede estar habilitada si la opción **Procesamiento de medios centralizado** también está habilitada.|
|Procesamiento de medios centralizado|ConcentratedTopology|Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).|
|Habilitar cierre RTP|EnableRTPLatching|Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).|
|Habilitar el historial de llamadas reenviadas|ForwardCallHistory|Indica si la información del historial de llamadas se reenviará a través del tronco.|
|Habilitar el reenvío de datos P-Asserted-Identity|ForwardPAI|Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada.|
|Habilitar temporizador de conmutación por error del enrutamiento de salida|EnableFastFailoverTimer|Indica que si las llamadas salientes no son respondidas por la puerta de enlace en el plazo de 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente.|
|Usos de la RTC asociados|PSTNUsages|Colección de usos de RTC asignados al tronco.|
|Número traducido para probar|N/D|Número telefónico que puede usare para realizar una prueba ad hoc de la configuración del tronco.|
|Reglas de conversión asociadas|OutboundTranslationRulesList|Recopilación de reglas de conversión de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).|
|Reglas de traducción de números llamados|OutboundCallingNumberTranslationRulesList|Colección de reglas de conversión de números de llamadas salientes asignadas al tronco.|
|Número de teléfono para probar|N/D|Número telefónico que puede usarse para realizar una prueba ad hoc de las reglas de conversión.|
|Número que llamada|N/D|Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.|
|Número llamado|N/D|Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.|
|||

> [!Note]
> Skype para Business Server CsTrunkConfiguration cmdlets admitir propiedades adicionales que no se muestra en el Skype para el Panel de Control de servidor empresarial. Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration) . 

**Para modificar las opciones de configuración de troncos SIP mediante el uso de la Skype para el Panel de Control de servidor empresarial**

1. En Skype para el Panel de Control de servidor empresarial, haga clic en **Enrutamiento de voz**y, a continuación, haga clic en **Configuración del tronco**.
2. En la pestaña **Configuración de tronco**, haga doble clic en las opciones de configuración de tronco que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, use Windows PowerShell.
3. En el cuadro de diálogo **Editar configuración de tronco** , realice las selecciones adecuadas y, a continuación, haga clic en **Aceptar**.
4. La propiedad Estado para la colección se actualizará a No confirmado. Para confirmar los cambios y para eliminar la colección, haga clic en **Confirmar**y, a continuación, haga clic en **Confirmar todo**.
5. En el cuadro de diálogo **Configuración de voz no confirmados**, haga clic en **Aceptar**.
6. En el cuadro de diálogo **Skype para el Panel de Control de servidor empresarial** , haga clic en **Aceptar**.