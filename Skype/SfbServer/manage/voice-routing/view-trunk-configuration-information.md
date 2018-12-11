---
title: Ver la información de configuración de tronco en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: 9d4890cd70256c6f063653a29d5d41f6e5a301cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222719"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Ver la información de configuración de tronco en Skype para Business Server

Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.

- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo (RTCP) de control de transporte en tiempo real.
- Si se requiere cifrado del protocolo seguro en tiempo real (SRTP) en cada tronco.

Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

**Para ver información de configuración de tronco SIP mediante Skype para el Panel de Control de servidor empresarial**

1. En Skype para el Panel de Control de servidor empresarial, haga clic en **Enrutamiento de voz**y, a continuación, haga clic en **Configuración del tronco**.
2. En la ficha **Configuración del tronco** verá una lista de las de las colecciones de opciones de configuración de tronco; para cada colección de podrá ver los valores de las propiedades **nombre**, **ámbito**, **estado**y **el desvío de medios** , junto con el número de **usos de RTC**, **las reglas de números de llamada**y **reglas de números llamados** asociado con la colección. Para ver detalles adicionales acerca de una colección de opciones de configuración de tronco, haga clic en la colección de interés, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**. Tenga en cuenta que puede ver información detallada solo para una colección de opciones de configuración de tronco a la vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de configuración de tronco SIP mediante el uso de cmdlets de Windows PowerShell

SIP configuración del tronco configuración puede verse mediante el uso de Skype para Business Server PowerShell y el cmdlet Get-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, consulte el artículo del blog de Lync Server Windows PowerShell "Rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell" en http://go.microsoft.com/fwlink/p/?linkId=255876. REEMPLAZAR O QUITAR ESTE VÍNCULO.


**Para ver la información de configuración de tronco SIP**

Para ver información acerca de todas las opciones de configuración del tronco SIP, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:

`Get-CsTrunkConfiguration`

Devolverá información similar a la siguiente:

```
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



