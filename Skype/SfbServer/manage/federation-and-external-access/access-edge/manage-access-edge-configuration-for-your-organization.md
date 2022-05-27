---
title: Administrar la configuración perimetral de acceso para su organización
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso de dominio o proveedor externo, acceso de usuario remoto y acceso de usuario anónimo a conferencias a través de los servidores perimetrales que se admitirán para su organización.
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674602"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Administrar la configuración perimetral de acceso para su organización

Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso de dominio o proveedor externo, acceso de usuario remoto y acceso de usuario anónimo a conferencias a través de los servidores perimetrales que se admitirán para su organización.

Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **Configuración perimetral de acceso**:

  - **Habilitación de la federación y la conectividad de mensajería instantánea pública**   Habilite esta opción si desea admitir el acceso de usuario a dominios de asociado federados. Esta configuración se aplica a la federación SIP configurada para ámbitos globales, de sitio o de usuario en la página **Directiva de acceso externo** . Para que se aplique la configuración de federación, debe configurar la compatibilidad con la federación en ambas páginas.
    
    Existen dos opciones que son opciones opcionales para la forma en que se detectan los asociados federados y si se enviarán a los contactos de archivado (notificación a los contactos federados con los que se comunica que la implementación tiene habilitado el archivado y que se archivarán los detalles de las comunicaciones):
    
      - **Habilitación de la detección de dominios de asociados**   Al seleccionar esta opción, se habilita la detección automática de dominios con los que puede federar. Skype Empresarial Server usa registros del Sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluando automáticamente el tráfico entrante de asociados federados detectados y limitando o bloqueando ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración de administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener más información, consulte [Configuración de la compatibilidad con dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Envío de declinación de responsabilidades de archivado a asociados federados**   Al seleccionar esta opción, se permite enviar un mensaje de declinación de responsabilidades de archivado a asociados federados que les informa de que se registran los detalles de las comunicaciones. Si archiva comunicaciones externas con dominios de asociado federados, debe habilitar la notificación de declinación de responsabilidades de archivado para advertir a los asociados de que la implementación archiva sus mensajes y detalles de comunicaciones. Para obtener más información sobre el archivado, consulte [Habilitación o deshabilitación del envío de una declinación de responsabilidades de archivado a un asociado federado](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitación del acceso de usuario remoto**   Habilite esta opción si desea que los usuarios de su organización que están fuera del firewall, como los teletrabajos y los usuarios que viajan, puedan conectarse a Skype Empresarial Server. Para obtener más información, consulte [Habilitación o deshabilitación del acceso de usuario remoto](enable-or-disable-remote-user-access.md).

  - **Habilitación de usuarios anónimos para acceder a conferencias**   Habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organicen. La habilitación de esta configuración solo permite a los usuarios anónimos para conferencias.

> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuario externo, también configura las directivas para controlar el uso del acceso de usuario remoto en su organización antes de que cualquier tipo de acceso de usuario esté disponible para los usuarios. Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, consulte Administración de directivas de [acceso externo para su organización](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualización de la información de configuración de Access Edge mediante cmdlets de Windows PowerShell**

  - La información de configuración de Access Edge se puede ver mediante Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 
    
    Para ver información sobre todas las opciones de configuración de Access Edge, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
     `Get-CsAccessEdgeConfiguration`
    
    Devolverá información similar a la siguiente:
    
    Identidad: global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers: False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse: False<br/>
    EnablePartnerDiscovery: False<br/>
    EnableArchivingDisclaimer: False<br/>
    EnableUserReplicator: True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner: 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored: 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage: 20<br/>
    RoutingMethod: UseDnsSrvRouting<br/>

