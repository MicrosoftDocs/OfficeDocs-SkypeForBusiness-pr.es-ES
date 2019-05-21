---
title: Ver la información de configuración troncal en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274873"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Ver la información de configuración troncal en Skype empresarial Server

Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.

- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.
- Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

**Para ver la información de configuración del tronco de SIP mediante el panel de control de Skype empresarial Server**

1. En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración troncal**.
2. En la pestaña **configuración de tronco** verá una lista de todas las colecciones de parámetros de configuración de troncal; para cada colección verá los valores de las propiedades de **nombre**, **ámbito**, **Estado**y **omisión de elementos multimedia** , junto con el número de **usos de RTC**, **las reglas de números de llamadas**y **las reglas de números** asociados a las mismas. con la colección. Para ver más detalles sobre una colección de valores de configuración del tronco, haga clic en la colección de interés, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una colección de valores de configuración de troncales a la vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de la información de configuración del tronco de SIP mediante cmdlets de Windows PowerShell

Los ajustes de configuración del tronco de SIP se pueden ver con Skype empresarial Server PowerShell y el cmdlet Get-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server 2010 http://go.microsoft.com/fwlink/p/?linkId=255876mediante PowerShell remoto" en. REEMPLAZAR O QUITAR ESTE VÍNCULO.


**Para ver la información de configuración del tronco del SIP**

Para ver la información sobre todos los ajustes de configuración del troncal SIP, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:

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
Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



