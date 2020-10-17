---
title: 'Lync Server 2013: directrices de implementación para telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05cde2a845dd6314d8822e6b58445eed5c6a1d19
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531077"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Instrucciones de implementación para telefonía IP empresarial en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En este tema se describen los requisitos previos y otras instrucciones que se deben tener en cuenta al planear la implementación de Lync Server 2013 y la carga de trabajo de la telefonía IP empresarial.

<div>

## <a name="deployment-prerequisites"></a>Requisitos previos de implementación

Para obtener una experiencia óptima al implementar la telefonía IP empresarial, asegúrese de que la infraestructura de ti, la red y los sistemas cumplen los siguientes requisitos previos:

  - Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en la red.

  - Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales con el servicio perimetral de acceso, el servicio perimetral a/V, el servicio perimetral de conferencia web y un proxy inverso.

  - Se han creado uno o más usuarios y están habilitados para Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) o el último Service Pack o Microsoft Exchange Server 2010 está instalado. Uno de ellos es necesario para integrar la mensajería unificada (MU) de Exchange con Lync Server y proporcionar notificaciones enriquecidas e información de registro de llamadas a los extremos de cliente.

  - Un número de teléfono principal único se ha designado, normalizado y copiado al atributo **msRTCSIP-line** para cada usuario que se va a habilitar para la telefonía IP empresarial.
    
    <div>
    

    > [!NOTE]  
    > Lync Server admite números E. 164 y números de marcado hacia adentro (DID) no directo. Los números no DID pueden representarse con el formato <STRONG> &lt; E. 164 &gt; ; ext &lt; = &gt; Extension</STRONG> o como una cadena de dígitos, con el requisito de que la extensión privada sea única en toda la empresa. Por ejemplo, el número privado 1001 se puede representar como <STRONG>+1425550100;ext=1001</STRONG> o como <STRONG>1001</STRONG>. Cuando se representa como <STRONG>1001</STRONG>, se espera que este número privado sea único en toda la empresa.

    
    </div>

  - Los administradores que implementen la telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.

  - Como mínimo, Office Communicator 2007 se ha implementado correctamente. Para usar las características nuevas de esta versión, se ha implementado Lync 2013.

  - Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.

  - Cada equipo donde se instale el servidor de mediación deberá:
    
      - Un servidor miembro de un dominio y preparado para los servicios de dominio de Active Directory. Para los procedimientos de preparación de los servicios de dominio de Active Directory, consulte preparación de los [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.
    
      - Ejecutar uno de los sistemas operativos siguientes:
        
          - <span></span>  
            La edición de 64 bits del sistema operativo Windows Server 2008 Standard
        
          - <span></span>  
            La edición de 64 bits del sistema operativo Windows Server 2008 Enterprise

  - Si la conexión a la red telefónica conmutada (RTC) o central de conmutación (PBX) se realiza por medio de una conexión de multiplexación por división de tiempo (TDM), una o más puertas de enlace RTC deben estar disponibles para la implementación. (Si la conexión se realiza por medio de un tronco SIP, no se necesita ninguna puerta de enlace RTC.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Interrupciones de alimentación, de la red o del servicio telefónico

Si se produce una interrupción, una interrupción u otra degradación de los servicios de alimentación, red o teléfono en su ubicación, es posible que la voz, la mensajería instantánea, la presencia y otras características de Lync Server y cualquier dispositivo conectado a Lync Server no funcionen correctamente.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Enterprise Voice depende de la disponibilidad del servidor y de la operabilidad del cliente VoIP y del hardware

Las comunicaciones de voz con Lync Server dependen de la disponibilidad del software de servidor y del correcto funcionamiento de los clientes de voz o de los dispositivos telefónicos de hardware que se conectan al software del servidor.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Métodos de acceso alternativos a los servicios de emergencia

Para las ubicaciones en las que se instala un cliente de voz (por ejemplo, un equipo con cliente de Lync o un dispositivo de Lync Phone Edition), se recomienda mantener una opción de copia de seguridad para que los usuarios llamen a los servicios de emergencia (por ejemplo, 911 o 999) en caso de que se produzca un error en la alimentación, degradación de la conectividad de red, interrupción del , Lync o dispositivos de Lync Phone Edition. Esas opciones alternativas pueden ser un teléfono conectado a una línea de la red telefónica conmutada estándar o un teléfono móvil.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Llamadas de emergencia y sistemas telefónicos de varias líneas

El uso de un sistema telefónico multilínea (MLTS) puede estar sujeto a U. el estado o leyes federales o las leyes de otros países o regiones que requieren la MLTS para proporcionar al número de teléfono, la extensión o la ubicación física de un autor de la llamada a los servicios de emergencia aplicables cuando una persona que llama se coloca en los servicios de emergencia (por ejemplo, cuando se marca un número de acceso de emergencia como 911 o 999). En esta versión, Lync Server se puede configurar para proporcionar una ubicación física de un autor de llamada a un proveedor de servicios de emergencia, tal como se describe en [Planning for Emergency Services (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). El cumplimiento de la ley MLTS es la única responsabilidad del comprador de los dispositivos Lync Server, cliente de Lync y Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

