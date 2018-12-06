---
title: "Lync Server 2013: Administrar configuración perimetral de acceso para su organización"
TOCTitle: Administrae la configuración perimetral de acceso para su organización
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ552443(v=OCS.15)
ms:contentKeyID: 49115264
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar la configuración perimetral de acceso para su organización en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Esta documentación es preliminar y está sujeta a cambios. Los temas en blanco que se incluyen actúan como marcadores de posición.

Tras implementar uno o más Servidores perimetrales, debe habilitar los tipos de acceso de proveedor o dominio externo, el acceso de usuario remoto y el acceso de usuario anónimo a las conferencias a través del Servidores perimetrales que se admitirán para su organización.

Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **Configuración perimetral de acceso**:

  - **Habilitar federación y conectividad pública de mensajería instantánea**: habilite esta opción si desea admitir el acceso del usuario a dominios de socios federados. Esta configuración se aplica tanto a la federación SIP como a la federación XMPP que se configura para ámbitos de usuario, de sitio o global en la página **Directiva de acceso externo**. Para la configuración de federación que se va a aplicar, debe configurar la compatibilidad de federación en ambas páginas.
    
    Existen dos opciones que son valores opcionales para la manera en que se detectan los socios federados y si las renuncias de archivado (notificación a contactos federados con los que se comunica que su implementación tiene el archivado habilitado y que se archivarán los detalles de comunicaciones) se enviarán a los contactos
    
      - **Habilitar detección de dominio de socio**: la selección de esta opción habilita la detección automática de dominios con los que puede federar. Lync Server 2013 usa registros del Sistema de nombres de dominio (DNS) para tratar de detectar dominios no mostrados en la lista de dominios permitidos, evaluando automáticamente el tráfico de entrada desde los socios federados detectados y limitando o bloqueando dicho tráfico basado en el nivel de confianza, la cantidad de tráfico y la configuración de administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que incluya en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener detalles, vea [Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Enviar declinación de responsabilidades de archivado a los socios federados**: la selección de esta opción permite el envío de un mensaje de declinación de responsabilidades de archivado a socios federados que les avisa de que los detalles de comunicación están registrados. Si archiva comunicaciones externas con dominios de socio federados, debe habilitar la notificación de declinación de responsabilidades para advertir a los socios de que sus mensajes y detalles de comunicación se están archivando por su implementación. Para ver detalles sobre el archivado, vea [Definir los requisitos para archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Habilitar acceso de usuario remoto**: habilite esta opción si desea que los usuarios de su organización que están fuera de su firewall, como teletrabajadores y usuarios que viajan, puedan conectarse a Lync Server. Para obtener detalles, vea [Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Habilitar usuarios anónimos para obtener acceso a conferencias**: habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organizan. Al habilitar esta configuración solo permitirá usuarios anónimos para conferencias. Para configurar la experiencia de conferencia y las opciones que definirán qué harán los usuarios con las conferencias, y la manera de hacerlo, y para la inclusión de usuarios anónimos, vea los detalles en [Crear o modificar experiencia de usuario de conferencia para un sitio o grupo de usuarios](https://technet.microsoft.com/es-es/library/gg429715\(v=ocs.15\)) y [Referencia de configuración de directivas de conferencias en Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).


> [!NOTE]
> Además de habilitar la compatibilidad de acceso de usuario externo, también configura las directivas para controlar el uso del acceso de usuario remoto en su organización antes de que cualquier tipo de acceso de usuario esté disponible para los usuarios. Para obtener detalles acerca de la creación, configuración y aplicación de directivas para acceso de usuario externo, vea <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Administrar la directiva de acceso de la organización en Lync Server 2013</A>.



**Visualización de la información de configuración perimetral de acceso mediante los cmdlets Windows PowerShell**

  - La información de configuración perimetral de acceso se puede ver usando Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Para ver información acerca de todos los valores de configuración perimetral de acceso, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsAccessEdgeConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

## En esta sección

  - [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar y deshabilitar el acceso anónimo de usuarios en Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

