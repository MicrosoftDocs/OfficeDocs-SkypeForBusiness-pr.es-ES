---
title: 'Lync Server 2013: Requisitos de certificado para el acceso de usuarios externos'
TOCTitle: Requisitos de certificado para el acceso de usuarios externos
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48276789
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

El Microsoft Lync Server 2013 software de comunicaciones admite el uso de un único certificado público para interfaces externas perimetrales, de conferencia web y de acceso, además del servicio de autenticación A/V. La interfaz interna perimetral utiliza generalmente un certificado privado que emite una autoridad de certificación (CA) interna, pero también puede usar un certificado público siempre y cuando sea de una CA pública de confianza. El servidor proxy inverso de la implementación utiliza un certificado público y cifra la comunicación desde el proxy inverso hacia los clientes y del proxy inverso hacia los servidores internos utilizando HTTP (es decir, seguridad de la capa de transporte por HTTP).

Después se indican los requisitos para el certificado público usado para interfaces externas perimetrales, de conferencia web y de acceso, así como el servicio de autenticación A/V:

  - El certificado debe ser emitido por una CA pública aprobada que admita el nombre alternativo de sujeto. Para más información, vea el artículo 929395 de Microsoft Knowledge Base, "Socios de certificado de comunicaciones unificadas de Exchange Server y para Communications Server", en <http://go.microsoft.com/fwlink/?linkid=202834>.

  - Si el certificado se va a usar en un grupo de servidores perimetrales, créelo como exportable, con el mismo certificado usado en cada servidor perimetral en el grupo de servidores perimetrales. El requisito de clave privada exportable se debe al servicio de autenticación A/V, que debe usar la misma clave privada a través de todos los servidores perimetrales en el grupo.

  - Si desea obtener el máximo provecho del tiempo de actividad de los servicios de audio y vídeo, revise los requisitos del certificado para implementar un certificado de Servicio perimetral A/V separado (es decir un certificado de Servicio perimetral A/V diferente de los otros fines del certificado de perímetro externo). Para más información, vea [Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) y [Prueba de certificados de OAuth y audio y vídeo en Lync Server 2013 utilizando -Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate).

  - El nombre de sujeto del certificado es el nombre de dominio completo (FQDN) de la interfaz perimetral externa de Servidor perimetral de acceso o la IP virtual (VIP) del equilibrador de carga de hardware (por ejemplo, access.contoso.com).
    

    > [!NOTE]
    > Para Lync Server 2013, ya no se trata de un requisito, pero sigue siendo recomendable para la compatibilidad con Office Communications Server.



  - La lista de nombres alternativos de sujeto contiene los FQDN de:
    
      - La interfaz externa de Servidor perimetral de acceso o la VIP del equilibrador de carga de hardware (por ejemplo, sip.contoso.com).
        

        > [!NOTE]
        > A pesar de que el nombre de sujeto del certificado equivale al FQDN del servidor perimetral de acceso, el nombre alternativo del sujeto también debe contener el FQDN del servidor perimetral de acceso porque Seguridad de la capa de transporte (TLS, Transport Layer Security) ignora el nombre de sujeto y usa las entradas del nombre alternativo del sujeto para la validación.

    
      - La interfaz perimetral externa de conferencia web o la VIP del equilibrador de carga de hardware (por ejemplo, webcon.contoso.com).
    
      - Si usa una federación o configuración automática de clientes, incluya también todos los FQDN de dominios SIP usados en la compañía (por ejemplo, sip.contoso.com, sip.fabrikam.com).
    
      - El Servicio perimetral A/V no utiliza las entradas de nombre de sujeto ni de nombres alternativos de sujeto.
    

    > [!NOTE]
    > El orden de los FQDN en la lista de nombres alternativos del sujeto no importa.



Si va a implementar varios servidores perimetrales de carga equilibrada en un sitio, el certificado de servicio de autenticación A/V instalado en cada servidor perimetral debe ser de la misma CA y debe usar la misma clave privada. Tenga en cuenta que la clave privada del certificado debe poder exportarse, independientemente de si se usa en un servidor perimetral o en varios. También debe poder exportarse si solicita el certificado desde cualquier equipo que no sea el servidor perimetral.

Estos son los requisitos para el certificado privado (o público) usado para la interfaz perimetral interna:

  - El certificado puede ser emitido por una CA interna o por una CA pública de certificados aprobada.

  - El nombre de sujeto del certificado suele ser el FQDN de la interfaz perimetral interna o la VIP del equilibrador de carga de hardware (por ejemplo, lsedge.contoso.com). No obstante, puede usar un certificado de comodín en la interfaz perimetral interna.

  - No se necesita ningún nombre alternativo de sujeto.

El servidor proxy inverso de los servicios de implementación solicitan que los usuarios externos puedan obtener acceso a:

  - El contenido de las reuniones

  - Expandir y mostrar los miembros de los grupos de distribución

  - Archivos descargables del servicio de libreta de direcciones

  - El cliente Lync Web App

  - La página web de configuración de las conferencias de acceso telefónico

  - El servicio de información de ubicación

  - Que los dispositivos externos obtengan acceso al servicio de actualización de dispositivos y obtengan las actualizaciones

El servidor proxy inverso publique las direcciones URL de los componentes web del servidor interno. Estas direcciones se definen en el director, Servidor front-end o Grupo de servidores front-end como los **servicios web externos** de Generador de topologías.

Se pueden utilizar entradas de caracteres comodín en el campo de nombre alternativo de sujeto del certificado asignado al proxy inverso. Para más información sobre cómo configurar la solicitud de certificado para el proxy inverso, vea [Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

## Vea también

#### Conceptos

[Compatibilidad de certificado de comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)

