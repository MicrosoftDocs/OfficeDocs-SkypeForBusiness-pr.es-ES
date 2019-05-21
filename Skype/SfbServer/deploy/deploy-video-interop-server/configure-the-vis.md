---
title: Configurar el servidor de interoperabilidad de vídeo en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: configure el rol servidor de interoperabilidad de video (VIS) en Skype empresarial Server.'
ms.openlocfilehash: 3c0b211897afdde0fc0a01e255cdc14bc466f65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302745"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurar el servidor de interoperabilidad de vídeo en Skype empresarial Server
 
**Resumen:** Configure el rol servidor de interoperabilidad de video (VIS) en Skype empresarial Server.
  
 Configure la configuración que se asociará con los troncos de video mediante Windows PowerShell. Una configuración de tronco de vídeo de ámbito global se crea una vez que se instala el servicio de VIS. Esta configuración de tronco de vídeo se aplica a todos los troncos que no cuentan con una configuración de tronco de vídeo con un ámbito más específico. Tenga en cuenta que la configuración de tronco de vídeo es una colección de configuraciones que se aplica a los troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar el tronco de vídeo y el plan de marcado

Use los siguientes comandos de Windows PowerShell para especificar la configuración del tronco de vídeo y el plan de marcado que se asociará con los troncales recién definidos definidos en el documento de topología entre las videollamadas VIS y todas las puertas de enlace de vídeo. Toda esta configuración se puede definir de forma global, en el sitio o en el servicio (puerta de enlace de vídeo). 
  
Un plan de marcado con ámbito global se crea por implementación de Skype empresarial Server. Este plan de marcado se aplica a todos los troncos que no tienen ningún plan de marcado con un ámbito más específico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar el VIS con Windows PowerShell

1. Cree una nueva configuración de troncal de video (una colección de configuraciones) para usarla en el tronco entre el administrador de comunicaciones unificadas de Windows (CallManager o CUCM) con el siguiente cmdlet de Windows PowerShell:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Si hay un tronco de vídeo existente que necesita modificar, use el siguiente cmdlet de Windows PowerShell:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para ver la configuración asociada a una configuración de tronco de vídeo determinada, use el siguiente cmdlet de Windows PowerShell:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para quitar una configuración de tronco de vídeo determinada, use el siguiente cmdlet de Windows PowerShell (tenga en cuenta que la configuración del tronco de video de ámbito global se aplicará si no hay una configuración de tronco de video de ámbito más específica para un tronco en particular):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Establezca un plan de marcado para asociarlo con el tronco mediante los siguientes cmdlets de Windows PowerShell:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

El comando **Remove-CsVoiceNormalizationRule** es necesario para reemplazar una regla predeterminada que interferirá con la interacción de VIS y CUCM esperada.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) puede usarse para quitar un plan de marcado.
  
Para una llamada troncal del SIP de video desde una puerta de enlace de vídeo cuyo URI de solicitud contiene un número no-E. 164, leerá el nombre del plan de marcado asociado con el tronco asociado, e incluirá el nombre del plan de marcado en la parte del contexto de teléfono del URI de la solicitud en la invitación que VI S envía al front-end. La aplicación de conversión en el front-end extrae las reglas de normalización asociadas con el plan de marcado y las aplica al URI de solicitud.
## <a name="trunk-configuration-options"></a>Opciones de configuración del tronco

Los cmdlets de Windows PowerShell para la configuración de tronco de video mencionados anteriormente eran nuevos en Skype empresarial Server 2015. La configuración asociada con la configuración del enlace de vídeo requiere una breve explicación.
  
 **GatewaySendsRtcpForActiveCalls** Este parámetro determina si los paquetes RTCP se envían desde el VTC a las llamadas activas. En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección. Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a los 30 segundos. La opción predeterminada es **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Este parámetro determina si los paquetes RTCP continúan enviándose a través del tronco para las llamadas que se han suspendido y no se espera que los paquetes Multimedia fluyan en ambas direcciones. VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde el dispositivo VTC a VIS mientras la llamada está en espera. El valor predeterminado es **True**. Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.
  
 **EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para los medios cuando el protocolo SIPTransport se establece en TLS. La opción predeterminada es **True**. Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.
  
 **EnableSessionTimer** Este parámetro habilita o deshabilita los temporizadores de sesión en el lado visible de cada cuadro de diálogo SIP asociado con el tronco del SIP de video. La opción predeterminada es **False**.
  
 **ForwardErrorCorrectionType** Este parámetro se usa para determinar si se debe aplicar la corrección de errores de reenvío (FEC) para las transmisiones de vídeo en el segmento entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo. Al establecer ForwardErrorCorrectionType en "ninguno", se desactiva FEC entre VIS y la puerta de enlace y VTC de video. La configuración de ForwardErrorCorrectionType a "Cisco" habilita FEC compatible con las puertas de enlace de video de Cisco, como el administrador de comunicaciones unificadas de Cisco (CUCM). La opción predeterminada es **Ninguno**.
  
## <a name="see-also"></a>Vea también

[Configurar CUCM para interoperabilidad con Skype empresarial Server](configure-cucm-for-interoperation.md)
