---
title: 'Skype Empresarial Server: crear una nueva colección de opciones de configuración de tronco'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 'Summary: Learn how to create a new collection of trunk configuration settings by using the Skype Empresarial Server Control Panel.'
ms.openlocfilehash: a538ad2ff5e19c21ba36afaf928144c7d255e8e2
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012334"
---
# <a name="skype-for-business-server-create-a-new-collection-of-trunk-configuration-settings"></a>Skype Empresarial Server: crear una nueva colección de opciones de configuración de tronco

**Resumen:** Obtenga información sobre cómo crear una nueva colección de opciones de configuración de tronco mediante el panel Skype Empresarial Server control.
  
Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de sucursal de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:
  
- Si se debe habilitar el desvío de medios en los troncos.
    
- Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP).
    
- Se requiere o no cifrado de Protocolo de transporte en tiempo real seguro (SRTP) en cada tronco.
    
Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).
  
Al crear opciones de configuración de tronco SIP mediante Skype Empresarial Server Panel de control, las siguientes opciones están disponibles.
  
|**Valor de IU**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identidad  <br/> |Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.  <br/> |
|Descripción  <br/> |Descripción  <br/> |Proporciona una manera para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).  <br/> |
|Cantidad máxima de cuadros de diálogo admitidos  <br/> |MaxEarlyDialogs  <br/> |La cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.  <br/> |
|Nivel de compatibilidad con el cifrado  <br/> |SRTPMode  <br/> | Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio. Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración de medios se establece mediante los [cmdlets New-CsMediaConfiguration](/powershell/module/skype/new-csmediaconfiguration) y [Set-CsMediaConfiguration.](/powershell/module/skype/set-csmediaconfiguration) <br/>  Los valores permitidos son: <br/>  Requeridos: debe usarse el cifrado SRTP. <br/>  Opcional: el SRTP se utilizará si la puerta de enlace lo admite. <br/>  No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se utilizará. <br/>  El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.<br/> |
|Hacer referencia al soporte  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Si se configura en **Habilitar enviar referencia a la puerta de enlace**, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.  <br/> Si está establecido como **Habilitar la referencia mediante un control de llamadas de terceros**, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado. 3pcc también se conoce como "control de terceros" y ocurre cuando un tercero se utiliza para conectar un par de personas que llaman (por ejemplo, un operador que realiza una llamada de la persona A a una persona B).<br/> |
|Habilitar el desvío de medios  <br/> |EnableBypass  <br/> |Indica si la omisión de medios se encuentra habilitado para este tronco. La omisión de medios solo puede estar habilitada si el **Procesamiento de medios centralizado** también está habilitado.<br/> |
|Procesamiento de medios centralizado  <br/> |ConcentratedTopology  <br/> |Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).  <br/> |
|Habilitar el cierre RTP  <br/> |EnableRTPLatching  <br/> |Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).  <br/> |
|Habilitar el historial de desvío de llamadas  <br/> |ForwardCallHistory  <br/> |Indica si la información del historial de llamadas se reenviará mediante el tronco.  <br/> |
|Habilitar los datos de reenvío de la identidad p-asserted  <br/> |ForwardPAI  <br/> |Indica si el encabezado de la identidad p-asserted (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad de la persona que realiza la llamada.  <br/> |
|Habilitar el temporizador de desvío de conmutación por error saliente  <br/> |EnableFastFailoverTimer  <br/> |Indica que si las llamadas salientes no son respondidas por la puerta de enlace dentro de los 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que se pierdan innecesariamente las llamadas.  <br/> |
|Usos asociados de la RTC  <br/> |PSTNUsages  <br/> |Recopilación de los usos de RTC asignados al tronco.  <br/> |
|Número traducido para probar  <br/> |N/D  <br/> |Número telefónico que puede utilizarse para realizar una prueba ad hoc de la configuración del tronco.  <br/> |
|Reglas asociadas de traducción  <br/> |OutboundTranslationRulesList  <br/> |Recopilación de reglas de traducción de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).  <br/> |
|Reglas de traducción de los números llamados  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Colección de reglas de traducción para números de llamada saliente asignadas al tronco.  <br/> |
|Número de teléfono que se debe probar  <br/> |N/D  <br/> |Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.  <br/> |
|Número de llamada  <br/> |N/D  <br/> |Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.  <br/> |
|Número llamado  <br/> |N/D  <br/> |Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.  <br/> |
   
> [!NOTE]
> Los cmdlets Skype Empresarial Server CsTrunkConfiguration admiten propiedades adicionales que no se muestran en Skype Empresarial Server Panel de control. Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsTrunkConfiguration.](/powershell/module/skype/new-cstrunkconfiguration)
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para crear nuevas opciones de configuración de tronco mediante Skype Empresarial Server Panel de control

1. En Skype Empresarial Server panel de control, haga clic en **Enrutamiento de** voz y, a continuación, haga clic en Configuración **del tronco**.
    
2. En la pestaña **Configuración de tronco**, haga clic en **Nuevo** y luego haga clic en **Tronco de sitio** para crear el nuevo parámetro en el ámbito del sitio o en **Tronco de grupo** para crear el nuevo parámetro en el ámbito del servicio.
    
3. En el cuadro de diálogo **Seleccionar un sitio** o **Seleccionar un servicio** (el cuadro de diálogo que aparece depende de si va a crear parámetros de ámbito de sitio o ámbito de servicio) seleccione la ubicación para los nuevos parámetros de configuración y luego haga clic en **Aceptar**. Si el cuadro de diálogo está en blanco, significa que no hay lugar para crear los nuevos parámetros; por ejemplo, si el cuadro de diálogo **Seleccionar un sitio** está en blanco significa que todos los sitios ya se han asignado una colección de sitios de configuración del tronco y cada sitio (y cada servicio) solo puede alojar una de esas colecciones. En ese caso, puede eliminar la colección existente y crear una nueva o simplemente cambiar la colección existente.
    
4. En el cuadro de diálogo **Nueva configuración de tronco**, relacione las selecciones adecuadas y haga clic en **Aceptar**.
    
5. La propiedad **Estado** de la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.
    
6. En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.
    
7. En el **cuadro Skype Empresarial Server panel de control,** haga clic en **Aceptar**.
