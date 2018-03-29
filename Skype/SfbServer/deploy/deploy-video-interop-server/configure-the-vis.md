---
title: Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: Configurar la función de servidor de interoperabilidad de vídeo (VIS) en Skype para Business Server 2015.'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a>Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015
 
**Resumen:** Configurar la función de servidor de interoperabilidad de vídeo (VIS) en Skype para Business Server 2015.
  
 Configure las opciones que se asociará el VIS con vídeo troncos mediante Windows PowerShell. Una configuración de tronco de vídeo de ámbito global se crea una vez que se instala el servicio de VIS. Esta configuración de tronco de vídeo se aplica a todos los troncos que no cuentan con una configuración de tronco de vídeo con un ámbito más específico. Tenga en cuenta que la configuración de tronco de vídeo es una colección de configuraciones que se aplica a los troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar el tronco de vídeo y el plan de marcado

Utilice los siguientes comandos de Windows PowerShell para especificar la configuración de vídeo tronco y el marcado que se va a asociarse con el recién definido trunk(s) definido en el documento de la topología entre el VIS y todas las puertas de enlace de vídeo. Toda esta configuración se puede definir de forma global, en el sitio o en el servicio (puerta de enlace de vídeo). 
  
Un plan de marcado con ámbito global se crea por Skype para la implementación de Business Server. Este plan de marcado se aplica con respecto a todos los troncos que no tienen marcado a cualquier plan de ámbito más específico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar el VIS mediante Windows PowerShell

1. Crear una nueva configuración de vídeo tronco (una colección de valores) para utilizar en el maletero entre el VIS y CUCM, mediante el siguiente cmdlet de Windows PowerShell:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Si hay un tronco de vídeo existente que se debe modificar, utilice el siguiente cmdlet de Windows PowerShell:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para ver la configuración asociada con una configuración de tronco de vídeo determinado, use el siguiente cmdlet de Windows PowerShell:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para eliminar una configuración de troncales de vídeo determinado, use el siguiente cmdlet de Windows PowerShell (tenga en cuenta que la configuración de ámbito global tronco de vídeo se aplicará si no hay una configuración más específicamente con ámbito tronco de vídeo para un tronco particular):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Establecer un plan de marcado para asociar con el tronco, mediante los siguientes cmdlets de Windows PowerShell:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

El comando **Remove-CsVoiceNormalizationRule** es necesario para reemplazar una regla predeterminada que interferirá con la interacción de VIS y CUCM esperada.
> [!NOTE]
> [Quitar CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) puede utilizarse para eliminar un plan de marcado.
  
Una llamada de troncal SIP vídeo desde una puerta de enlace de vídeo cuyo URI de solicitud contiene un número no E.164, leerá el nombre del plan de marcado asociado del tronco asociado VIS e incluirá el nombre del plan de marcado en el elemento de contexto de teléfono del identificador URI de solicitud en la invitación que VI S se envía al cliente. La aplicación de conversión en el front-end extrae las reglas de normalización asociadas con el plan de marcado y las aplica al URI de solicitud.
## <a name="trunk-configuration-options"></a>Opciones de configuración del tronco

Los cmdlets de Windows PowerShell para la configuración de vídeo tronco mencionados anteriormente son nuevos en el Skype para Business Server 2015. La configuración asociada a la configuración de troncales de vídeo requiere una breve explicación.
  
 **GatewaySendsRtcpForActiveCalls** Este parámetro determina si los paquetes RTCP se envían desde el VTC a la VIS de llamadas activas. En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección. Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a los 30 segundos. El valor predeterminado es **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Este parámetro determina si los paquetes RTCP siguen enviándose a través del tronco para las llamadas que se han colocado en suspensión y no hay paquetes de media deben fluir en ambas direcciones. VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde el dispositivo VTC a VIS mientras la llamada está en espera. El valor predeterminado es **True**. Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.
  
 **EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para medios cuando el protocolo SIPTransport se establece en TLS. La opción predeterminada es **True**. Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.
  
 **EnableSessionTimer** Este parámetro habilita o deshabilita los temporizadores de sesión en el lado de VIS para cada cuadro de diálogo SIP asociados a la troncal SIP vídeo. La opción predeterminada es **False**.
  
 **ForwardErrorCorrectionType** Este parámetro se utiliza para determinar si se aplica en la pierna entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo hacia delante Error corrección (FEC) para las secuencias de vídeo. Configuración ForwardErrorCorrectionType como "None" desactiva FEC entre VIS y puerta de enlace de vídeo/VTC. Establecer ForwardErrorCorrectionType a "Cisco" permite FEC compatible con puertas de enlace de vídeo por Cisco, como Cisco Unified Communications Manager (CUCM). La opción predeterminada es **Ninguno**.
  
## <a name="see-also"></a>Vea también

#### 

[Configurar CUCM para la interoperación con Skype para Business Server 2015](configure-cucm-for-interoperation.md)

