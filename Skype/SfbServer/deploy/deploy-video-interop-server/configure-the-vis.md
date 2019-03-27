---
title: Configurar el servidor de interoperabilidad vídeo en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: Configure el rol de servidor de interoperabilidad de vídeo (VISIBLES) de Skype para Business Server.'
ms.openlocfilehash: 1cdc03fea116b5c41eaca13b4349ffc340dbc061
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880189"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurar el servidor de interoperabilidad vídeo en Skype para Business Server
 
**Resumen:** Configuración de la función de servidor de interoperabilidad de vídeo (VISIBLES) en Skype para Business Server.
  
 Configure las opciones que se asociará el frente con vídeo troncos con Windows PowerShell. Una configuración de tronco de vídeo de ámbito global se crea una vez que se instala el servicio de VIS. Esta configuración de tronco de vídeo se aplica a todos los troncos que no cuentan con una configuración de tronco de vídeo con un ámbito más específico. Tenga en cuenta que la configuración de tronco de vídeo es una colección de configuraciones que se aplica a los troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar el tronco de vídeo y el plan de marcado

Uso de planeación de los siguientes comandos de Windows PowerShell para especificar la configuración del tronco de vídeo y el marcado que se asociará con el recién definido trunk(s) definido en el documento de topología entre el frente y todas las puertas de enlace de vídeo. Toda esta configuración se puede definir de forma global, en el sitio o en el servicio (puerta de enlace de vídeo). 
  
Se crea un plan de marcado con ámbito global por Skype para la implementación de Business Server. Este plan de marcado se aplica de forma con respecto a todos los troncos que no tienen ningún marcado planeación con ámbito más específica. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar el respecto al uso de Windows PowerShell

1. Crear una nueva configuración de tronco vídeo (una colección de opciones) para usar en el tronco entre el frente y Cisco Unified Communications Manager (CallManager o CUCM), mediante el siguiente cmdlet de Windows PowerShell:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Si no hay un tronco de vídeo existente que debe modificarse, use el siguiente cmdlet de Windows PowerShell:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para ver la configuración asociada con una configuración de tronco de vídeo determinado, use el siguiente cmdlet de Windows PowerShell:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para quitar una configuración de tronco de vídeo determinado, use el siguiente cmdlet de Windows PowerShell (tenga en cuenta que la configuración del tronco de vídeo con ámbito global se aplicará si no hay una configuración de ámbito más concretamente tronco de vídeo para un tronco determinado):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Establecer un plan de marcado para asociar con el tronco, con los siguientes cmdlets de Windows PowerShell:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

El comando **Remove-CsVoiceNormalizationRule** es necesario para reemplazar una regla predeterminada que interferirá con la interacción de VIS y CUCM esperada.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) puede utilizarse para quitar un plan de marcado.
  
Para una llamada de vídeo de tronco SIP desde una puerta de enlace vídeo cuyo identificador URI de solicitud contiene un número que no sean E.164, leerá el nombre del plan de marcado asociado con el tronco asociado respecto e incluirá el nombre del plan de marcado en el elemento de contexto de teléfono de la dirección URI de solicitud en la invitación a ese VI S envía a Front-End. La aplicación de conversión en el front-end extrae las reglas de normalización asociadas con el plan de marcado y las aplica al URI de solicitud.
## <a name="trunk-configuration-options"></a>Opciones de configuración del tronco

Los cmdlets de Windows PowerShell para la configuración del tronco de vídeo que se ha mencionado anteriormente eran nuevos en Skype para Business Server 2015. La configuración asociada a la configuración del tronco vídeo requiere una explicación breve.
  
 **GatewaySendsRtcpForActiveCalls** Este parámetro determina si RTCP se envían los paquetes desde el VTC a la luz visible para las llamadas activas. En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección. Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a los 30 segundos. La opción predeterminada es **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Este parámetro determina si sigue paquetes RTCP enviarse a través del tronco para las llamadas que se han colocado en espera y no se esperaban que los paquetes multimedia en cualquier dirección de flujo. VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde el dispositivo VTC a VIS mientras la llamada está en espera. El valor predeterminado es **True**. Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.
  
 **EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para los medios cuando se establece el protocolo SIPTransport en TLS. La opción predeterminada es **True**. Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.
  
 **EnableSessionTimer** Este parámetro habilita o deshabilita a temporizadores de sesión en el lado respecto de cada cuadro de diálogo SIP asociada con el tronco SIP vídeo. La opción predeterminada es **False**.
  
 **ForwardErrorCorrectionType** Este parámetro se usa para determinar si está desviar Error corrección (FEC) para las secuencias de vídeo que se aplique en la bifurcación entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo. Opción de configuración ForwardErrorCorrectionType en "None" desactiva FEC entre respecto y puerta de enlace de vídeo/VTC. Establecer ForwardErrorCorrectionType a "Cisco" permite FEC compatible con puertas de enlace de vídeo por Cisco, como Cisco Unified Communications Manager (CUCM). La opción predeterminada es **Ninguno**.
  
## <a name="see-also"></a>Consulte también

[Configurar CUCM para la interoperación con Skype para Business Server](configure-cucm-for-interoperation.md)
