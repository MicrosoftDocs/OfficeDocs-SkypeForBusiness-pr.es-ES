---
title: Crear una nueva colección de parámetros de configuración de troncal en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: 6db4978151bf9b649375adb7a2200710a1a503c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817010"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Crear una nueva colección de parámetros de configuración de troncal en Skype empresarial Server

Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.
- Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

Al crear parámetros de configuración de tronco de usingSkype para Business Server panel de control, las siguientes opciones están disponibles:

|Valor de IU | Parámetro de PowerShell | Descripción |
|--|--|--|
|Nombre|Identity|Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.|
|Descripción|Description|Proporciona un método para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).|
|Número máximo de diálogos iniciales admitidos|MaxEarlyDialogs|Cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.|
|Nivel de compatibilidad de cifrado|SRTPMode|Indica el nivel de compatibilidad para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio. Para los casos de omisión de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración multimedia se establece mediante los cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) y [set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) .<br/>Los valores permitidos son:<br/><br/>**Requerido**: se debe usar el cifrado SRTP.<br/>**Opcional**: SRTP se usará si la puerta de enlace lo admite.<br/>**No admitido**: no se admite el cifrado SRTP y, por lo tanto, no se usará.<br/><br/>El SRTPMode se usa solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, SRTPMode se configura internamente como No admitido.|
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
|Número que llamada|N/D|Número telefónico que puede usarse para realizar una prueba ad hoc de las reglas de conversión.|
|Número llamado|N/D|Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.|
||||

> [!Note]
> Los cmdlets de Skype empresarial Server CsTrunkConfiguration admiten propiedades adicionales que no se muestran en el panel de control de Skype empresarial Server. Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) . 

**Para crear nuevos ajustes de configuración de troncal con el panel de control de Skype empresarial Server**

1. En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración troncal**.
2. En la pestaña **Configuración de tronco**, haga clic en **Nuevo** y luego haga clic en **Tronco de sitio** para crear el nuevo parámetro en el ámbito del sitio o en **Tronco de grupo** para crear el nuevo parámetro en el ámbito del servicio.
3. En el cuadro de diálogo **seleccionar un sitio** o **seleccionar un servicio** (el cuadro de diálogo que aparece dependerá de si está creando una configuración de ámbito de sitio o de ámbito o de servicio), seleccione la ubicación de la nueva configuración y, a continuación, haga clic en **Aceptar**. Si el cuadro de diálogo está en blanco, significa que no hay ningún lugar para crear la nueva configuración; por ejemplo, si el cuadro de diálogo **seleccionar un sitio** está en blanco, significa que a todos los sitios ya se les ha asignado una colección de sitios de configuración de troncales y cada sitio (y cada servicio) solo puede hospedar uno de ellos. En ese caso, puede eliminar la colección existente y crear una nueva o simplemente cambiar la colección existente.
4. En el cuadro de diálogo **Nueva configuración de tronco**, relacione las selecciones adecuadas y haga clic en **Aceptar**.
5. La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.
6. En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.
7. En el cuadro de diálogo **Panel de control de Skype para empresas** , haga clic en **Aceptar**.
