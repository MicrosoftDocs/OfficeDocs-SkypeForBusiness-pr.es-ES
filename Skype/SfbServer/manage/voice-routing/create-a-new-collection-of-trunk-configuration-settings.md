---
title: Crear una nueva colección de opciones de configuración de troncos en Skype Empresarial Server
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
description: Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: 1dff6eaf5c3c9b0d7ea2378dc5499568b0bd65a3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823420"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Crear una nueva colección de opciones de configuración de troncos en Skype Empresarial Server

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:
- Si se debe habilitar el desvío de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
- Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype Empresarial Server, se crea automáticamente una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

Al crear opciones de configuración de troncos SIP con el Panel de control deSkype para Business Server, tiene a su disposición las siguientes opciones:

|Valor de IU | Parámetro de PowerShell | Descripción |
|--|--|--|
|Name|Identidad|Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.|
|Descripción|Descripción|Proporciona una manera para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).|
|Cantidad máxima de cuadros de diálogo admitidos|MaxEarlyDialogs|La cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.|
|Nivel de compatibilidad con el cifrado|SRTPMode|Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio. Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración de medios se establece mediante los [cmdlets New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration) y [Set-CsMediaConfiguration.](https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration)<br/>Los valores permitidos son:<br/><br/>**Obligatorio:** debe usarse el cifrado SRTP.<br/>**Opcional:** SRTP se usará si la puerta de enlace lo admite.<br/>**No admitido:** no se admite el cifrado SRTP y, por lo tanto, no se usará.<br/><br/>El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.|
|Hacer referencia al soporte|Enable3pccRefer<br/>EnableReferSupport|Si se configura en **Habilitar enviar referencia a la puerta de enlace**, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.<br/>Si está establecido como **Habilitar la referencia mediante un control de llamadas de terceros**, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado. 3pcc también se conoce como "control de terceros" y ocurre cuando un tercero se utiliza para conectar un par de personas que llaman (por ejemplo, un operador que realiza una llamada de la persona A a una persona B).|
|Habilitar el desvío de medios|EnableBypass|Indica si la omisión de medios se encuentra habilitado para este tronco. La omisión de medios solo puede estar habilitada si el **Procesamiento de medios centralizado** también está habilitado.|
|Procesamiento de medios centralizado|DescontencionesTopología|Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).|
|Habilitar el cierre RTP|EnableRTPLatching|Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).|
|Habilitar el historial de desvío de llamadas|ForwardCallHistory|Indica si la información del historial de llamadas se reenviará mediante el tronco.|
|Habilitar los datos de reenvío de la identidad p-asserted|ForwardPAI|Indica si el encabezado de la identidad p-asserted (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad de la persona que realiza la llamada.|
|Habilitar el temporizador de desvío de conmutación por error saliente|EnableFastFailoverTimer|Indica que si las llamadas salientes no son respondidas por la puerta de enlace dentro de los 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que se pierdan innecesariamente las llamadas.|
|Usos asociados de la RTC|PSTNUsages|Recopilación de los usos de RTC asignados al tronco.|
|Número traducido para probar|N/D|Número telefónico que puede utilizarse para realizar una prueba ad hoc de la configuración del tronco.|
|Reglas asociadas de traducción|OutboundTranslationRulesList|Recopilación de reglas de traducción de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).|
|Reglas de traducción de los números llamados|OutboundCallingNumberTranslationRulesList|Colección de reglas de traducción para números de llamada saliente asignadas al tronco.|
|Número de teléfono que se debe probar|N/D|Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.|
|Número de llamada|N/D|Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.|
|Número llamado|N/D|Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.|
||||

> [!Note]
> Los cmdlets CsTrunkConfiguration de Skype Empresarial Server admiten propiedades adicionales no mostradas en el Panel de control de Skype Empresarial Server. Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration) 

**Para crear nuevas opciones de configuración de tronco mediante el Panel de control de Skype Empresarial Server**

1. En el Panel de control de Skype Empresarial Server, haga clic en **Enrutamiento** de voz y, a continuación, haga clic en **Configuración del tronco.**
2. En la pestaña **Configuración de tronco**, haga clic en **Nuevo** y luego haga clic en **Tronco de sitio** para crear el nuevo parámetro en el ámbito del sitio o en **Tronco de grupo** para crear el nuevo parámetro en el ámbito del servicio.
3. En el cuadro de diálogo Seleccionar un sitio o Seleccionar un servicio (el cuadro de diálogo que aparece dependerá de si va **a** crear opciones de ámbito de sitio o de ámbito de servicio), seleccione la ubicación de las nuevas opciones de configuración y, **a** continuación, haga clic en **Aceptar.** Si el cuadro de diálogo está en blanco, significa que no hay ningún lugar donde crear la nueva configuración; por ejemplo,  si el cuadro de diálogo Seleccionar un sitio está en blanco, significa que todos los sitios ya tienen asignada una colección de sitios de configuración troncal y cada sitio (y cada servicio) solo puede hospedar una de estas colecciones. En ese caso, puede eliminar la colección existente y crear una nueva o simplemente cambiar la colección existente.
4. En el cuadro de diálogo **Nueva configuración de tronco**, relacione las selecciones adecuadas y haga clic en **Aceptar**.
5. La propiedad **Estado** de la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.
6. En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.
7. En el **cuadro de diálogo Panel de control** de Skype Empresarial, haga clic en **Aceptar.**
