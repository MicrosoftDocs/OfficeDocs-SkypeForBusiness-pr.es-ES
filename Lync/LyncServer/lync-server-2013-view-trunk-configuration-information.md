---
title: 'Lync Server 2013: ver información de configuración troncal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77f53a4263fd0e0b64ccd6894d27e30c0c5be95c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Ver la información de configuración troncal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

  - Si se debe activar la omisión de medios en los troncos.

  - Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.

  - Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Microsoft Lync Server 2013, se crea una colección global de parámetros de configuración del tronco del SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Para ver la información de configuración del tronco de SIP mediante el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **enrutamiento de voz** y luego en **configuración troncal**.

2.  En la pestaña **configuración de tronco** verá una lista de toda la colección de valores de configuración de troncal; para cada colección verá valores para las propiedades **nombre**, **ámbito**, **Estado**y omisión de **elementos multimedia** , junto con el número de **usos de RTC**, **las reglas de números de llamadas**y **las reglas numéricas** asociadas a la colección. Para ver más detalles sobre una colección de valores de configuración del tronco, haga clic en la colección de interés, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una colección de valores de configuración de troncales a la vez.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de la información de configuración del tronco de SIP mediante cmdlets de Windows PowerShell

Los ajustes de configuración del tronco de SIP se pueden ver con Lync Server PowerShell y el cmdlet Get-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>Para ver la información de configuración del tronco del SIP

  - Para ver información sobre todos los valores de configuración del tronco del SIP, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsTrunkConfiguration
    
    Devolverá información similar a la siguiente:
    
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

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

