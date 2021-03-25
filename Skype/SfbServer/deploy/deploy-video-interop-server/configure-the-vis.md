---
title: Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: configure el rol servidor de interoperabilidad de vídeo (VIS) en Skype Empresarial Server.'
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120309"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server
 
**Resumen:** Configure el rol Servidor de interoperabilidad de vídeo (VIS) en Skype Empresarial Server.
  
 Configure las opciones que el VIS asociará a los troncos de vídeo mediante Windows PowerShell. Una configuración de tronco de vídeo con ámbito global se crea una vez instalado el servicio VIS. El VIS aplica esta configuración de tronco de vídeo a todos los troncos que no tienen una configuración de tronco de vídeo con un ámbito más específico. Tenga en cuenta que la configuración del tronco de vídeo es una colección de opciones que se aplican a los troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar el tronco de vídeo y el plan de marcado

Use los siguientes comandos Windows PowerShell para especificar la configuración del tronco de vídeo y el plan de marcado que se asociarán con los troncos recién definidos definidos en el documento de topología entre el VIS y todas las puertas de enlace de vídeo. Todas estas opciones de configuración se pueden establecer en los niveles Global, Site o Service (Video Gateway). 
  
Se crea un plan de marcado con ámbito global por implementación de Skype Empresarial Server. Vis aplica este plan de marcado a todos los troncos que no tienen ningún plan de marcado con un ámbito más específico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar el VIS mediante Windows PowerShell

1. Cree una nueva configuración de tronco de vídeo (una colección de configuraciones) para usarla en el tronco entre el VIS y el Administrador de comunicaciones unificadas de Cisco (CallManager o CUCM), mediante el siguiente cmdlet Windows PowerShell web:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Si hay un tronco de vídeo existente que debe modificarse, use el siguiente cmdlet Windows PowerShell vídeo:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para ver la configuración asociada a una configuración de tronco de vídeo determinada, use el siguiente cmdlet Windows PowerShell vídeo:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para quitar una configuración de tronco de vídeo determinada, use el siguiente cmdlet Windows PowerShell (tenga en cuenta que la configuración del tronco de vídeo de ámbito global se aplicará si no hay una configuración de tronco de vídeo con ámbito más específico para un tronco concreto):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Establezca un plan de marcado para asociarlo con el tronco, mediante los siguientes cmdlets Windows PowerShell:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

El **comando Remove-CsVoiceNormalizationRule** es necesario para invalidar una regla predeterminada que interfiera con la interacción vis y CUCM esperada.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) se puede usar para quitar un plan de marcado.
  
Para una llamada troncal SIP de vídeo desde una puerta de enlace de vídeo cuyo URI de solicitud contiene un número que no es E.164, VIS leerá el nombre del plan de marcado asociado al tronco asociado e incluirá el nombre del plan de marcado en la parte de contexto del teléfono del URI de solicitud en la invitación que vis envía al front-end. A continuación, la aplicación de traducción del front-end extrae y aplica las reglas de normalización asociadas con el plan de marcado al URI de solicitud.
## <a name="trunk-configuration-options"></a>Opciones de configuración de tronco

Los cmdlets Windows PowerShell para la configuración del tronco de vídeo mencionados anteriormente eran nuevos en Skype Empresarial Server 2015. La configuración asociada a la configuración del tronco de vídeo requiere una breve explicación.
  
 **GatewaySendsRtcpForActiveCalls** Este parámetro determina si los paquetes RTCP se envían desde VTC al VIS para llamadas activas. En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección. Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a 30 segundos. El valor predeterminado es **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Este parámetro determina si los paquetes RTCP siguen en envío a través del tronco para las llamadas que se han colocado en espera y no se espera que los paquetes multimedia fluyan en ninguna dirección. VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde VTC a VIS mientras la llamada está en espera. El valor predeterminado es **True**. Cuando el protocolo SIPTransport se establece en TCP, esta configuración se omite.
  
 **EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para medios cuando el protocolo SIPTransport está establecido en TLS. El valor predeterminado es **True**. Cuando el protocolo SIPTransport se establece en TCP, esta configuración se omite.
  
 **EnableSessionTimer** Este parámetro habilita o deshabilita los temporizadores de sesión en el lado VIS para cada cuadro de diálogo SIP asociado al tronco SIP de vídeo. El valor predeterminado es **False**.
  
 **ForwardErrorCorrectionType** Este parámetro se usa para determinar si la corrección de errores de reenvío (FEC) para secuencias de vídeo se va a aplicar en el tramo entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo. Al establecer ForwardErrorCorrectionType en "None" se desactiva FEC entre VIS y Video Gateway/VTC. Al establecer ForwardErrorCorrectionType en "Cisco" se habilita FEC compatible con las puertas de enlace de vídeo de Cisco, como Cisco Unified Communications Manager (CUCM). El valor predeterminado es **Ninguno**.
  
## <a name="see-also"></a>Ver también

[Configurar CUCM para interoperación con Skype Empresarial Server](configure-cucm-for-interoperation.md)