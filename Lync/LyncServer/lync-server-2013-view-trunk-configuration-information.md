---
title: Visualización de la información de configuración de troncos en Lync Server 2013
TOCTitle: Visualización de la información de configuración de troncos en Lync Server 2013
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49889797
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de configuración de troncos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

  - Si se debe activar la omisión de medios en los troncos.

  - Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).

  - Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.

Al instalar Microsoft Lync Server 2013, se crea una sola recopilación global de opciones de configuración del tronco SIP. Además, los administradores pueden crear recopilaciones de opciones de configuración personalizadas en el ámbito del sitio o del servicio (solo para el servicio de puerta de enlace RTC).

## Consulta de la información de configuración del tronco SIP en el Panel de control de Lync Server

1.  En Panel de control de Lync Server, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.

2.  En la pestaña **Configuración de tronco**, verá una lista de todas las recopilaciones de opciones de configuración del tronco. Para cada recopilación verá los valores de las propiedades **Nombre**, **Ámbito**, **Estado** y **Omisión de medios**, junto con el número de **usos de RTC**, **Reglas del número que llama** y **Reglas del número llamado** asociados a la recopilación. Para ver información más detallada sobre una recopilación de opciones de configuración de un tronco, haga clic en la recopilación que le interese, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**. Observe que solo puede ver la información detallada de una recopilación de opciones de configuración de tronco en cada momento.

## Consulta de la información de configuración de un tronco usando los cmdlets de Lync Server PowerShell

Las opciones de configuración de los troncos SIP también se pueden ver usando Lync Server PowerShell y el cmdlet Get-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Consulta de la información de configuración de un tronco SIP

  - Para consultar información de todas las opciones de configuración de un tronco SIP, escriba el siguiente comando en el Shell de administración de Lync Server y pulse ENTRAR:
    
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

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration).

