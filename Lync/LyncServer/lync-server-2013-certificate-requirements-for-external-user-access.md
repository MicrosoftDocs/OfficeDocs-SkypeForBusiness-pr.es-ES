---
title: 'Lync Server 2013: Requisitos de certificado para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-29_

El software de comunicaciones Microsoft Lync Server 2013 admite el uso de un único certificado público para las interfaces externas de acceso y de conferencia Web, además del servicio de autenticación A/V. La interfaz interna de Edge generalmente usa un certificado privado emitido por una entidad de certificación (CA) interna, pero también puede usar un certificado público, siempre que proviene de una CA pública de confianza. El proxy inverso de la implementación usa un certificado público y cifra la comunicación desde el proxy inverso a los clientes y el proxy inverso a los servidores internos mediante HTTP (es decir, la seguridad de la capa de transporte a través de HTTP).

A continuación se indican los requisitos para el certificado público que se usa para las interfaces externas de acceso y de la conferencia Web, y el servicio de autenticación A/V:

  - El certificado debe ser emitido por una entidad de certificación pública aprobada que admita el nombre alternativo del sujeto. Para obtener más información, consulte el artículo 929395 de Microsoft Knowledge base, "asociados de certificados de comunicaciones unificadas para Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)y Communications Server", en.

  - Si el certificado se va a usar en un grupo perimetral, debe crearse como exportable, con el mismo certificado que se usa en cada servidor perimetral del grupo Edge. El requisito de clave privada exportable es para los fines del servicio de autenticación A/V, que debe usar la misma clave privada en todos los servidores perimetrales del grupo.

  - Si desea maximizar el tiempo de actividad de sus servicios de audio/vídeo, revise los requisitos del certificado para implementar un certificado de servicio perimetral A/V desvinculado (es decir, un certificado de servicio perimetral A/V independiente de los otros objetivos de certificado de borde externo). Para obtener más información, vea [cambios en Lync server 2013 que afectan a la planeación de los servidores perimetrales](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [plan para certificados de servidor perimetral en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) y [certificados AV y OAuth en Lync Server 2013 mediante-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - El nombre de firmante del certificado es el nombre de dominio completo de la interfaz externa de servicio perimetral de Access (FQDN) o el equilibrio de carga de hardware VIP (por ejemplo, access.contoso.com). ). El nombre del asunto no puede tener un carácter comodín, debe ser un nombre explícito.
    
    <div>
    

    > [!NOTE]  
    > Para Lync Server 2013, esto ya no es necesario, pero se le sigue recomendando para la compatibilidad con Office Communications Server.

    
    </div>

  - La lista de nombres alternativos de asunto contiene los FQDN de los siguientes elementos:
    
      - La VIP de la interfaz externa del servicio perimetral de acceso o del equilibrador de carga del hardware (por ejemplo, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Aunque el nombre del sujeto del certificado es igual al FQDN del perímetro de acceso, el nombre alternativo del sujeto también debe contener el FQDN del perímetro de acceso porque la seguridad de la capa de transporte (TLS) omite el nombre del sujeto y usa las entradas de nombre alternativo de asunto para validación.

        
        </div>
    
      - La interfaz externa perimetral de la conferencia web o el equilibrador de carga del hardware VIP (por ejemplo, webcon.contoso.com).
    
      - Si está usando la configuración automática o la Federación de clientes, incluya también cualquier FQDN de dominio SIP usado dentro de su empresa (por ejemplo, sip.contoso.com, sip.fabrikam.com).
    
      - El servicio de borde A/V no usa las entradas de nombre de sujeto o de nombre alternativo de asunto.
    
    <div>
    

    > [!NOTE]  
    > El orden de los FQDN en la lista de nombres alternativos de asunto no es relevante.

    
    </div>

Si implementa varios servidores perimetrales con equilibrio de carga en un sitio, el certificado del servicio de autenticación A/V instalado en cada servidor perimetral debe ser de la misma CA y debe usar la misma clave privada. Tenga en cuenta que la clave privada del certificado debe ser exportable, independientemente de si se usa en un servidor perimetral o en muchos servidores perimetrales. También debe ser exportable si solicita el certificado desde cualquier equipo que no sea el servidor perimetral. Puesto que el servicio de autenticación A/V no usa el nombre de asunto o el nombre alternativo de asunto, puede reutilizar el certificado perimetral de acceso siempre que se cumplan los requisitos de nombre de asunto y nombre alternativo del asunto para el límite de acceso y la clave privada del certificado, y la clave privada del certificado se puede exportar.

Los requisitos para el certificado privado (o público) que se usa para la interfaz interna de Edge son los siguientes:

  - El certificado puede ser emitido por una entidad de certificación interna o por una entidad emisora de certificados pública aprobada.

  - El nombre de firmante del certificado suele ser el FQDN de la interfaz interna del perímetro o el VIP del equilibrador de carga de hardware (por ejemplo, lsedge.contoso.com). Sin embargo, puede usar un certificado comodín en el perímetro interno.

  - No se requiere ninguna lista de nombres alternativos de asunto.

El proxy inverso en las solicitudes de servicios de implementación para:

  - Acceso de usuarios externos a contenido de reuniones para reuniones

  - Acceso de usuarios externos para expandir y mostrar miembros de grupos de distribución

  - Acceso de usuarios externos a archivos descargables desde el servicio de libreta de direcciones

  - Acceso de usuarios externos al cliente de Lync Web App

  - Acceso de usuarios externos a la Página Web de la configuración de conferencias de acceso telefónico local

  - Acceso de usuarios externos al servicio de información de ubicación

  - Acceso de dispositivo externo al servicio de actualización de dispositivos y obtener actualizaciones

El proxy inverso publica las direcciones URL de los componentes Web internos del servidor. Las direcciones URL de los componentes Web se definen en el director, el servidor front-end o el grupo front-end como **servicios web externos** en el generador de topología.

Las entradas con comodín son compatibles con el campo Nombre alternativo del sujeto del certificado asignado al proxy inverso. Para obtener más información sobre cómo configurar la solicitud de certificado para el proxy inverso, consulte [solicitar y configurar un certificado para su proxy http inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Vea también


[Compatibilidad de certificado de comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

