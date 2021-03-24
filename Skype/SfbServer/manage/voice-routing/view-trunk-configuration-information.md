---
title: Ver información de configuración de tronco en Skype Empresarial Server
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
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102996"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Ver información de configuración de tronco en Skype Empresarial Server

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.

- Si se debe habilitar el desvío de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
- Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

**Para ver la información de configuración del tronco SIP mediante el Panel de control de Skype Empresarial Server**

1. En el Panel de control de Skype Empresarial Server, haga clic en **Enrutamiento** de voz y, a continuación, haga clic en **Configuración de tronco.**
2. En la **pestaña Configuración de** tronco verá una lista de todas las colecciones de configuraciones de tronco; para cada colección, verá los valores de las propiedades **Name**, **Scope**, **State** y **Media bypass,** junto con el número de usos de RTC, las reglas de número de llamada y las reglas de número de llamada **asociadas** a la colección.  Para ver detalles adicionales sobre una colección de opciones de configuración de tronco, haga clic en la colección de interés, haga clic en **Editar** y, a continuación, haga clic **en Mostrar detalles.** Tenga en cuenta que solo puede ver información detallada para una colección de opciones de configuración de tronco a la vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de configuración de tronco SIP mediante Windows PowerShell cmdlets

Las opciones de configuración del tronco SIP se pueden ver con PowerShell de Skype Empresarial Server y el cmdlet Get-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: Administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en https://go.microsoft.com/fwlink/p/?linkId=255876 . REEMPLACE O QUITE ESTE VÍNCULO.


**Para ver la información de configuración del tronco SIP**

Para ver información sobre todas las opciones de configuración del tronco SIP, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:

```powershell
Get-CsTrunkConfiguration
```

Devolverá información similar a la siguiente:

```console
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
Para obtener más información, vea el tema de ayuda del cmdlet [Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)