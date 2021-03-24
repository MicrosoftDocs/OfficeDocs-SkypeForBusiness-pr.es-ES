---
title: Modificar las opciones de configuración del tronco SIP en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: e426f2d9980f49a5203bec2cb47555f94f7551f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114126"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificar las opciones de configuración del tronco SIP en Skype Empresarial Server

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:

- Si se debe habilitar el desvío de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
- Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Cualquiera de estas colecciones se puede modificar más adelante mediante el Panel de control de Skype Empresarial Server o Windows PowerShell.

Al modificar las opciones de configuración del tronco SIP mediante el Panel de control del servidor de Skype Empresarial Server, hay disponibles las siguientes opciones:

|Valor de IU |Parámetro de PowerShell |Descripción |
|--|--|--|
|Name|Identidad|Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.|
|Descripción|Descripción|Proporciona una manera para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).|
|Cantidad máxima de cuadros de diálogo admitidos|MaxEarlyDialogs|La cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.|
|Nivel de compatibilidad con el cifrado|SRTPMode|Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio. Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración de medios se establece mediante los cmdlets New-CsMediaConfiguration y Set-CsMediaConfiguration.<br/>Los valores permitidos son:<br/><br/>**Obligatorio:** se debe usar el cifrado SRTP.<br/>**Opcional:** SRTP se usará si la puerta de enlace lo admite.<br/>**No compatible:** el cifrado SRTP no es compatible y, por lo tanto, no se usará.<br/><br/>El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.|
|Hacer referencia al soporte|Enable3pccRefer<br/>EnableReferSupport|Si se configura en **Habilitar enviar referencia a la puerta de enlace**, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.<br/>Si está establecido como **Habilitar la referencia mediante un control de llamadas de terceros**, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado. 3pcc también se conoce como "control de terceros" y ocurre cuando un tercero se utiliza para conectar un par de personas que llaman (por ejemplo, un operador que realiza una llamada de la persona A a una persona B).|
|Habilitar el desvío de medios|EnableBypass|Indica si la omisión de medios se encuentra habilitado para este tronco. La omisión de medios solo puede estar habilitada si el **Procesamiento de medios centralizado** también está habilitado.|
|Procesamiento de medios centralizado|ConcentratedTopology|Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).|
|Habilitar el cierre RTP|EnableRTPLatching|Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).|
|Habilitar el historial de desvío de llamadas|ForwardCallHistory|Indica si la información del historial de llamadas se reenviará mediante el tronco.|
|Habilitar los datos de reenvío de la identidad p-asserted|ForwardPAI|Indica si el encabezado de la identidad p-asserted (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad de la persona que realiza la llamada.|
|Habilitar el temporizador de desvío de conmutación por error saliente|EnableFastFailoverTimer|Indica que si las llamadas salientes no son respondidas por la puerta de enlace dentro de los 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que se pierdan innecesariamente las llamadas.|
|Usos asociados de la RTC|PSTNUsages|Recopilación de los usos de RTC asignados al tronco.|
|Número traducido para probar|N/D|Número telefónico que puede utilizarse para realizar una prueba ad hoc de la configuración del tronco.|
|Reglas asociadas de traducción|OutboundTranslationRulesList|Recopilación de reglas de traducción de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).|
|Reglas de traducción de los números llamados|OutboundCallingNumberTranslationRulesList|Colección de reglas de traducción para números de llamada saliente asignadas al tronco.|
|Número de teléfono que se debe probar|N/D|Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.|
|Número de llamada|N/D|Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.|
|Número llamado|N/D|Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.|
|||

> [!Note]
> Los cmdlets CsTrunkConfiguration de Skype Empresarial Server admiten propiedades adicionales que no se muestran en el Panel de control de Skype Empresarial Server. Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsTrunkConfiguration.](/powershell/module/skype/Set-CsTrunkConfiguration) 

**Para modificar las opciones de configuración del tronco SIP mediante el Panel de control de Skype Empresarial Server**

1. En el Panel de control de Skype Empresarial Server, haga clic en **Enrutamiento** de voz y, a continuación, haga clic en **Configuración de tronco.**
2. En la pestaña **Configuración de tronco** haga doble clic en las opciones de configuración de troncos que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, utilice Windows PowerShell.
3. En el **cuadro de diálogo Editar** configuración de tronco, realice las selecciones adecuadas y, a continuación, haga clic en **Aceptar**.
4. La propiedad Estado de la recopilación se actualizará a Sin confirmar. Para confirmar los cambios y eliminar la colección, haga clic **en Confirmar** y, a continuación, haga clic en **Confirmar todo**.
5. En el **cuadro de diálogo Configuración de voz** no confirmada, haga clic en **Aceptar**.
6. En el **cuadro de diálogo Panel de control de Skype Empresarial Server,** haga clic en **Aceptar**.