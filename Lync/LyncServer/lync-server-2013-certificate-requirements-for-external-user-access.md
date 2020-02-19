---
title: 'Lync Server 2013: requisitos de certificado para el acceso de usuarios externos'
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
ms.openlocfilehash: 0561c2d6b36090a9499abf360373cf0468cdbda8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-29_

El software de comunicaciones Microsoft Lync Server 2013 admite el uso de un único certificado público para las interfaces externas perimetrales de acceso y conferencia Web, además del servicio de autenticación A/V. La interfaz interna perimetral utiliza generalmente un certificado privado que emite una autoridad de certificación (CA) interna, pero también puede utilizar un certificado público siempre y cuando sea de una CA pública de confianza. El servidor proxy inverso de la implementación utiliza un certificado público y cifra la comunicación desde el proxy inverso hacia los clientes y del proxy inverso hacia los servidores internos utilizando HTTP (es decir, seguridad de la capa de transporte por HTTP).

A continuación, se indican los requisitos para el certificado público usado para interfaces externas perimetrales, de conferencia web y de acceso, así como el servicio de autenticación A/V:

  - El certificado debe ser emitido por una CA pública aprobada que admita el nombre alternativo de sujeto. Para obtener más información, consulte el artículo 929395 de Microsoft Knowledge base, "asociados de certificados de comunicaciones unificadas para Exchange Server [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)y para Communications Server" en.

  - Si el certificado se usará en un grupo de servidores perimetrales, debe crearse como exportable, con el mismo certificado usado en cada servidor perimetral en el grupo de servidores perimetrales. El requisito de clave privada exportable se debe al servicio de autenticación A/V, que debe usar la misma clave privada a través de todos los servidores perimetrales en el grupo.

  - Si desea maximizar el tiempo de actividad de los servicios de audio y vídeo, revise los requisitos de certificado para implementar un certificado de servicio perimetral A/V desacoplado (es decir, un certificado de servicio perimetral A/V independiente de los otros propósitos de certificado perimetral externo). Para obtener más información, vea [cambios en Lync server 2013 que afectan a la planeación de los servidores perimetrales](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server Certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) y staging de los [certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - El nombre de sujeto del certificado es el nombre de dominio completo (FQDN) de la interfaz externa del servicio perimetral de acceso o el VIP del equilibrador de carga de hardware (por ejemplo, access.contoso.com). ). El nombre del sujeto no puede tener un carácter comodín, debe ser un nombre explícito.
    
    <div>
    

    > [!NOTE]  
    > Para Lync Server 2013, ya no es un requisito, pero se sigue recomendando por compatibilidad con Office Communications Server.

    
    </div>

  - La lista de nombres alternativos de sujeto contiene los FQDN de:
    
      - La interfaz externa del servicio perimetral de acceso o VIP del equilibrador de carga de hardware (por ejemplo, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > A pesar de que el nombre de sujeto del certificado equivale al FQDN del servidor perimetral de acceso, el nombre alternativo del sujeto también debe contener el FQDN del servidor perimetral de acceso porque Seguridad de la capa de transporte (TLS, Transport Layer Security) ignora el nombre de sujeto y usa las entradas del nombre alternativo del sujeto para la validación.

        
        </div>
    
      - La interfaz perimetral externa de conferencia web o la VIP del equilibrador de carga de hardware (por ejemplo, webcon.contoso.com).
    
      - Si usa una federación o configuración automática de clientes, incluya también todos los FQDN de dominios SIP usados en la compañía (por ejemplo, sip.contoso.com, sip.fabrikam.com).
    
      - El servicio perimetral A/V no usa las entradas de nombre de sujeto o de nombres alternativos de sujeto.
    
    <div>
    

    > [!NOTE]  
    > El orden de los FQDN en la lista de nombres alternativos del sujeto no importa.

    
    </div>

Si va a implementar varios servidores perimetrales de carga equilibrada en un sitio, el certificado de servicio de autenticación A/V instalado en cada servidor perimetral debe ser de la misma CA y debe usar la misma clave privada. Tenga en cuenta que la clave privada del certificado debe poder exportarse, independientemente de si se usa en un servidor perimetral o en varios. También debe poder exportarse si solicita el certificado desde cualquier equipo que no sea el servidor perimetral.

Estos son los requisitos para el certificado privado (o público) usado para la interfaz perimetral interna:

  - El certificado puede ser emitido por una CA interna o por una CA pública de certificados aprobada.

  - El nombre de sujeto del certificado suele ser el FQDN de la interfaz perimetral interna o la VIP del equilibrador de carga de hardware (por ejemplo, lsedge.contoso.com). No obstante, puede usar un certificado de comodín en la interfaz perimetral interna.

  - No se necesita ningún nombre alternativo de sujeto.

El servidor proxy inverso de los servicios de implementación solicitan que los usuarios externos puedan obtener acceso a:

  - El contenido de las reuniones

  - Expandir y mostrar los miembros de los grupos de distribución

  - Archivos descargables del servicio de libreta de direcciones

  - Acceso de usuarios externos al cliente de Lync Web App

  - La página web de configuración de las conferencias de acceso telefónico

  - El servicio de información de ubicación

  - Que los dispositivos externos obtengan acceso al servicio de actualización de dispositivos y obtengan las actualizaciones

El servidor proxy inverso publique las direcciones URL de los componentes web del servidor interno. Las direcciones URL de los componentes Web se definen en el director, el servidor front-end o el grupo de servidores front-end como los **servicios web externos** en el generador de topologías.

Se pueden utilizar entradas de caracteres comodín en el campo de nombre alternativo de sujeto del certificado asignado al proxy inverso. Para obtener más información sobre cómo configurar la solicitud de certificado para el proxy inverso, vea [solicitar y configurar un certificado para el proxy http inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Vea también


[Compatibilidad con certificados comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

