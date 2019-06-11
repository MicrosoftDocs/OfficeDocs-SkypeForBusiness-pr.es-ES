---
title: 'Lync Server 2013: Instrucciones para la implementación de la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Instrucciones para la implementación de la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En este tema se describen los requisitos previos y otras directrices que se deben tener en cuenta al planear la implementación de Lync Server 2013 y la carga de trabajo de telefonía IP empresarial.

<div>

## <a name="deployment-prerequisites"></a>Requisitos previos de implementación

Para obtener una experiencia óptima al implementar la telefonía IP empresarial, asegúrese de que la infraestructura de ti, la red y los sistemas cumplan los siguientes requisitos previos:

  - Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en su red.

  - Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales con el servicio perimetral de acceso, el servicio perimetral a/V, el servicio perimetral de conferencias web y un proxy inverso.

  - Uno o más usuarios se han creado y habilitado para Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) o el Service Pack más reciente o Microsoft Exchange Server 2010 está instalado. Una de estas opciones es necesaria para integrar la mensajería unificada de Exchange (UM) con Lync Server y para proporcionar notificaciones enriquecidas e información de registro de llamadas a los puntos de conexión de cliente.

  - Se ha designado un número de teléfono principal único, se ha normalizado y se ha copiado en el atributo **msRTCSIP-line** para cada usuario que va a estar habilitado para telefonía IP empresarial.
    
    <div>
    

    > [!NOTE]  
    > Lync Server admite números E. 164 y números de marcación directa (no) directos. Los números no recuperados se pueden representar con el formato <STRONG> &lt;E.&gt;164; ext&lt;=&gt; Extension</STRONG> o como una cadena de dígitos, con el requisito de que la extensión privada sea única en toda la empresa. Por ejemplo, un número privado de 1001 puede estar representado como <STRONG>+ 1425550100; ext = 1001</STRONG>o como <STRONG>1001</STRONG>. Cuando se representa como <STRONG>1001</STRONG>, la expectativa es que este número privado sea único en toda la empresa.

    
    </div>

  - Los administradores que implementan Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.

  - Como mínimo, Office Communicator 2007 se ha implementado correctamente. Para usar las características nuevas de esta versión, Lync 2013 está implementado.

  - La infraestructura de clave administrada (MKI) se implementa y configura con una infraestructura de entidad de certificación (CA) de Microsoft o de terceros.

  - Cada equipo en el que instale Media Server debe ser:
    
      - Un servidor miembro de un dominio y preparado para los servicios de dominio de Active Directory. Para los procedimientos de preparación de los servicios de dominio de Active Directory, vea [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación de implementación.
    
      - Ejecutando uno de los siguientes sistemas operativos:
        
          - <span></span>  
            La edición de 64 bits del sistema operativo Windows Server 2008 estándar
        
          - <span></span>  
            La edición de 64 bits del sistema operativo Windows Server 2008 Enterprise

  - Si la conexión a la red de telefonía pública conmutada (RTC) o a la central de conmutación (PBX) se hace por medio de una conexión de multiplexación de división de tiempo (TDM), una o más puertas de enlace RTC estarán disponibles para su implementación. (Si la conexión se hace por medio de un tronco de SIP, no es necesario una puerta de enlace RTC).

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Interrupciones en el servicio de alimentación eléctrica, red o redes

Si se produce una interrupción, una interrupción u otra degradación de los servicios de energía, red o teléfono de su ubicación, la voz, la mensajería instantánea, la presencia y otras características de Lync Server y cualquier dispositivo conectado a Lync Server pueden no funcionar correctamente.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>La telefonía IP empresarial depende de la disponibilidad del servidor y de la operatividad de hardware y cliente de voz

Las comunicaciones de voz con Lync Server dependen de la disponibilidad del software de servidor y del funcionamiento adecuado de los clientes de voz o de los dispositivos telefónicos de hardware que se conectan al software de servidor.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Métodos alternativos para acceder a servicios de emergencia

Para las ubicaciones en las que se instala un cliente de voz (por ejemplo, un equipo con cliente de Lync o un dispositivo de Lync Phone Edition), le recomendamos que mantenga una opción de copia de seguridad para que los usuarios llamen a servicios de emergencia (por ejemplo, 911 o 999) en caso de que se produzca un error de alimentación. , la degradación de la conectividad de red, la interrupción del servicio telefónico u otro problema que pueda inhibir el funcionamiento de los dispositivos Lync Server, Lync o Lync Phone Edition. Estas opciones alternativas pueden incluir un teléfono conectado a una línea de red de telefonía pública conmutada estándar o a un teléfono móvil.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Llamadas de emergencia y sistemas telefónicos de varias líneas

El uso de un sistema telefónico multilínea (MLTS) puede estar sujeto al estado U de la legislación federal o a la legislación de otros países o regiones que requieran que el MLTS ofrezca a los servicios de emergencia el número de teléfono, la extensión o la ubicación física de un llamador cuando un la persona que llama se coloca en los servicios de emergencia (por ejemplo, al marcar un número de acceso de emergencia, como 911 o 999). En esta versión, Lync Server se puede configurar para proporcionar a un proveedor de servicios de emergencia la ubicación física de una llamada, como se describe en [planeamiento de servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). El cumplimiento de las leyes de MLTS es responsabilidad exclusiva del comprador de Lync Server, del cliente de Lync y de los dispositivos Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

