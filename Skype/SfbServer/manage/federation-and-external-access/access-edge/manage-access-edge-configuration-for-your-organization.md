---
title: Administrar la configuración perimetral de acceso para su organización
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso de proveedor o dominio externo, acceso de usuarios remotos y acceso de usuarios anónimos a conferencias a través de los servidores perimetrales que se admiten para su organización.
ms.openlocfilehash: 7f5ea6db17b498d2f1732cf72fc5462546d7598841a1bd489ac77c8749d86130
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848545"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Administrar la configuración perimetral de acceso para su organización

Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso de proveedor o dominio externo, acceso de usuarios remotos y acceso de usuarios anónimos a conferencias a través de los servidores perimetrales que se admiten para su organización.

Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **Configuración perimetral de acceso**:

  - **Habilitar la federación y la conectividad de mensajería instantánea pública**   Habilite esta opción si desea admitir el acceso de usuarios a dominios de socios federados. Esta configuración se aplica a la federación SIP configurada para ámbitos globales, de sitio o de usuario en la **página Directiva de acceso** externo. Para que se apliquen las opciones de federación, debe configurar la compatibilidad de federación en ambas páginas.
    
    Existen dos opciones que son opciones opcionales para detectar socios federados y si las declinaciones de responsabilidades de archivado (notificación a los contactos federados con los que se comunica que la implementación tiene el archivado habilitado y que se archivarán los detalles de las comunicaciones) se enviarán a los contactos:
    
      - **Habilitar la detección de dominios de partners**   Al seleccionar esta opción, se habilita la detección automática de dominios con los que se puede federar. Skype Empresarial Server usa registros del Sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluando automáticamente el tráfico entrante de socios federados detectados y limitando o bloqueando ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración de administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener más información, vea [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Enviar declinación de responsabilidades de archivado a socios federados**   La selección de esta opción permite enviar un mensaje de declinación de responsabilidades de archivado a socios federados que les aconseje que se graben los detalles de las comunicaciones. Si archiva las comunicaciones externas con dominios de socios federados, debe habilitar la notificación de declinación de responsabilidades de archivado para advertir a los partners de que sus mensajes y detalles de comunicaciones están siendo archivados por la implementación. Para obtener más información sobre el archivado, vea Habilitar o deshabilitar el envío de una declinación de responsabilidades [de archivado a un partner federado.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **Habilitar el acceso de usuarios remotos**   Habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabadores y los usuarios que están de viaje, puedan conectarse a Skype Empresarial Server. Para obtener más información, [vea Enable or disable remote user access](enable-or-disable-remote-user-access.md).

  - **Permitir que los usuarios anónimos accedan a conferencias**   Habilite esta opción si desea que los usuarios internos inviten a los usuarios anónimos externos a las conferencias que organizan. Habilitar esta configuración solo permite a los usuarios anónimos realizar conferencias.

> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuario externo, también configura las directivas para controlar el uso del acceso de usuario remoto en su organización antes de que cualquier tipo de acceso de usuario esté disponible para los usuarios. Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualización de información de configuración perimetral de acceso mediante Windows PowerShell cmdlets**

  - La información de configuración perimetral de access se puede ver mediante Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration.** Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. 
    
    Para ver información sobre todas las opciones de configuración de Access Edge, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
     `Get-CsAccessEdgeConfiguration`
    
    Devolverá información similar a la siguiente:
    
    Identity : Global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery : False<br/>
    EnableArchivingDisclaimer : False<br/>
    EnableUserReplicator : True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner : 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored : 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage : 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

