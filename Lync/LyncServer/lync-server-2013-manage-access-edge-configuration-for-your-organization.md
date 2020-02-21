---
title: 'Lync Server 2013: administrar la configuración perimetral de acceso para su organización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31aa51647fa19a11cb4944829c2ab5e8eb10f2e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Administrar la configuración perimetral de acceso para su organización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Esta documentación es preliminar y está sujeta a cambios. Los temas en blanco se incluyen para referencia futura.

Después de implementar uno o varios servidores perimetrales, debe habilitar el acceso de los tipos de dominio o proveedor externo, el acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que serán compatibles con la organización.

Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **Configuración perimetral de acceso**:

  - **Habilitar la Federación y la conectividad**   de mensajería instantánea pública habilite esta funcionalidad si desea admitir el acceso del usuario a dominios de socios federados. Esta configuración se aplica a la Federación SIP y a la Federación XMPP que están configuradas para los ámbitos globales, de sitio o de usuario en la página **Directiva de acceso externo** . Para que se aplique la configuración de Federación, debe configurar la compatibilidad de Federación en ambas páginas.
    
    Existen dos opciones que son valores opcionales para la manera en que se detectan los socios federados y si las renuncias de archivado (notificación a contactos federados con los que se comunica que su implementación tiene el archivado habilitado y que se archivarán los detalles de comunicaciones) se enviarán a los contactos
    
      - **Habilitar detección**   del dominio del asociado: al seleccionar esta opción, se habilita la detección automática de dominios con los que se puede federar. Lync Server 2013 usa registros del sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados detectados y limitar o bloquear el tráfico en función del nivel de confianza. la cantidad de tráfico y la configuración del administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener más información, consulte [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Enviar renuncia de archivado a socios**   federados la selección de esta opción permite enviar un mensaje de renuncia de archivado a socios federados que les informa de que se registran los detalles de comunicación. Si archiva las comunicaciones externas con dominios de socios federados, debe habilitar la notificación de renuncia de archivado para avisar a los socios de que su implementación ha archivado los detalles de sus mensajes y comunicaciones. Para obtener más información sobre el archivado, vea [definir los requisitos para el archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Habilitar el acceso**   de usuarios remotos habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server. Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Permitir que los usuarios anónimos obtengan acceso**   a las conferencias habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organizan. Al habilitar esta configuración, solo se permiten usuarios anónimos para conferencias. Para configurar la experiencia de conferencia y las opciones que definen cómo y lo que los usuarios pueden hacer con las conferencias y para la inclusión de usuarios anónimos, vea los detalles en [Create or Modify Conferencing Conference User Experience for a site o users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing Policy Setting Reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuario externo, también configura las directivas para controlar el uso del acceso de usuario remoto en su organización antes de que cualquier tipo de acceso de usuario esté disponible para los usuarios. Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">administrar la Directiva de acceso externo en Lync Server 2013</A>.



</div>

**Visualización de la información de configuración perimetral de acceso mediante cmdlets de Windows PowerShell**

  - La información de configuración perimetral de acceso se puede ver con Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.
    
    Para ver información sobre todas las opciones de configuración perimetral de acceso, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
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

<div>

## <a name="in-this-section"></a>En esta sección

  - [Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar o deshabilitar el acceso de usuarios anónimos en Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

