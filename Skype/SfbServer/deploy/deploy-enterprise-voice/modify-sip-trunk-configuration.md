---
title: Modificar los ajustes de configuración del tronco de SIP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Resumen: Aprenda a modificar los ajustes de configuración del tronco del Protocolo de preconfiguración de SIP con el panel de control de Skype empresarial Server.'
ms.openlocfilehash: 6db2ddcf0155a599d8604bce2e3d5b5d34d6df20
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240283"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificar los ajustes de configuración del tronco de SIP en Skype empresarial Server
 
**Resumen:** Para obtener más información sobre cómo modificar los ajustes de configuración del tronco de protocolo, use el panel de control de Skype empresarial Server.
  
Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
  
- Si se debe activar la omisión de medios en los troncos.
    
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
    
- Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.
    
Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Cualquiera de estas colecciones se puede modificar más adelante con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server.
  
Al modificar los ajustes de configuración del tronco de SIP mediante el panel de control de Skype empresarial Server, las siguientes opciones están disponibles para usted.
  
|**Configuración de UI**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identity  <br/> |Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.  <br/> |
|Descripción  <br/> |Description  <br/> |Proporciona un método para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).  <br/> |
|Número máximo de diálogos iniciales admitidos  <br/> |MaxEarlyDialogs  <br/> |Cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.  <br/> |
|Nivel de compatibilidad de cifrado  <br/> |SRTPMode  <br/> | Indica el nivel de compatibilidad para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio. Para los casos de omisión de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración multimedia se establece mediante los cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) y [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) . <br/>  Los valores permitidos son: <br/>  Requeridos: debe usarse el cifrado SRTP. <br/>  Opcional: el SRTP se usará si la puerta de enlace lo admite. <br/>  No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se usará. <br/>  El SRTPMode se usa solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, SRTPMode se configura internamente como No admitido.<br/> |
|Compatibilidad con referencias  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Si se establece en **Habilitar referencias de envío a la puerta de enlace**, indica que el tronco admite la recepción de Solicitudes de referencia del Servidor de mediación.  <br/> Si se establece en en **Habilitar referencia mediante el control de llamadas a terceros**, indica que se puede usar el protocolo 3pcc para permitir llamadas transferidas para omitir el sitio hospedado. 3pcc también se conoce como "control de terceros" y ocurre cuando se usa un tercero para conectar un par de personas que llaman (por ejemplo, un operador que realiza una llamada de la persona A a una persona B).<br/> |
|Habilitar omisión de medios  <br/> |EnableBypass  <br/> |Indica si la omisión de medios está habilitada para este tronco. La omisión de medios solo puede estar habilitada si la opción **Procesamiento de medios centralizado** también está habilitada.<br/> |
|Procesamiento de medios centralizado  <br/> |ConcentratedTopology  <br/> |Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).  <br/> |
|Habilitar cierre RTP  <br/> |EnableRTPLatching  <br/> |Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).  <br/> |
|Habilitar el historial de llamadas reenviadas  <br/> |ForwardCallHistory  <br/> |Indica si la información del historial de llamadas se reenviará a través del tronco.  <br/> |
|Habilitar el reenvío de datos P-Asserted-Identity  <br/> |ForwardPAI  <br/> |Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada.  <br/> |
|Habilitar temporizador de conmutación por error del enrutamiento de salida  <br/> |EnableFastFailoverTimer  <br/> |Indica que si las llamadas salientes no son respondidas por la puerta de enlace en el plazo de 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente.  <br/> |
|Usos de la RTC asociados  <br/> |PSTNUsages  <br/> |Colección de usos de RTC asignados al tronco.  <br/> |
|Número traducido para probar  <br/> |N/D  <br/> |Número telefónico que puede usare para realizar una prueba ad hoc de la configuración del tronco.  <br/> |
|Reglas de conversión asociadas  <br/> |OutboundTranslationRulesList  <br/> |Recopilación de reglas de conversión de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).  <br/> |
|Reglas de traducción de números llamados  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Colección de reglas de conversión de números de llamadas salientes asignadas al tronco.  <br/> |
|Número de teléfono para probar  <br/> |N/D  <br/> |Número telefónico que puede usarse para realizar una prueba ad hoc de las reglas de conversión.  <br/> |
|Número que llamada  <br/> |N/D  <br/> |Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.  <br/> |
|Número llamado  <br/> |N/D  <br/> |Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.  <br/> |
   
> [!NOTE]
> Los cmdlets de CsTrunkConfiguration de Lync Server admiten propiedades adicionales que no se muestran en el panel de control de Lync Server. Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) .
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar los ajustes de configuración del tronco del protocolo troncal con el panel de control de Skype empresarial Server

1. En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración troncal**.
    
2. En la pestaña **Configuración de tronco**, haga doble clic en las opciones de configuración de tronco que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, use Windows PowerShell.
    
3. En el cuadro de diálogo **Editar configuración de tronco**, realice las selecciones apropiadas y seleccione **Aceptar**.
    
4. La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.
    
5. En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.
    
6. En el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.
    

