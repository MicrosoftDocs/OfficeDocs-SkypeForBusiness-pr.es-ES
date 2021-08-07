---
title: 'Skype Empresarial Server: Modificar las opciones de configuración del tronco SIP'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Summary: Learn how to modify SIP trunk configuration settings by using the Skype Empresarial Server Control Panel.'
ms.openlocfilehash: 1f7ef7c237295cc9a308a468b8f05424ebfe9d38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772551"
---
# <a name="skype-for-business-server-modify-sip-trunk-configuration-settings"></a>Skype Empresarial Server: Modificar las opciones de configuración del tronco SIP 
 
**Resumen:** Obtenga información sobre cómo modificar las opciones de configuración del tronco SIP mediante el Panel Skype Empresarial Server control.
  
Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de sucursal de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:
  
- Si se debe habilitar el desvío de medios en los troncos.
    
- Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP).
    
- Se requiere o no cifrado de Protocolo de transporte en tiempo real seguro (SRTP) en cada tronco.
    
Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Cualquiera de estas colecciones se puede modificar más adelante mediante el Panel de control Skype Empresarial Server o el Shell Skype Empresarial Server administración.
  
Al modificar las opciones de configuración del tronco SIP Skype Empresarial Server panel de control, las siguientes opciones están disponibles.
  
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
> Los cmdlets CsTrunkConfiguration de Lync Server admiten propiedades adicionales que no se muestran en el Panel de control de Lync Server. Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsTrunkConfiguration.](/powershell/module/skype/set-cstrunkconfiguration)
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar las opciones de configuración del tronco SIP mediante Skype Empresarial Server Panel de control

1. En Skype Empresarial Server panel de control, haga clic en **Enrutamiento de** voz y, a continuación, haga clic en Configuración **del tronco**.
    
2. En la pestaña **Configuración de tronco** haga doble clic en las opciones de configuración de troncos que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, utilice Windows PowerShell.
    
3. En el **cuadro de diálogo Editar** configuración de tronco, realice las selecciones adecuadas y, a continuación, haga clic en **Aceptar**.
    
4. La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.
    
5. En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.
    
6. En el **cuadro Skype Empresarial Server panel de control,** haga clic en **Aceptar**.
