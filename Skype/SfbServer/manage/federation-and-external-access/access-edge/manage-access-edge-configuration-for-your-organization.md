---
title: Administrae la configuración perimetral de acceso para su organización
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de implementar uno o más servidores perimetrales, debe habilitar a los tipos de dominio externo o acceso de proveedor, acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que se admite para su organización.
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199923"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Administrae la configuración perimetral de acceso para su organización

Después de implementar uno o más servidores perimetrales, debe habilitar a los tipos de dominio externo o acceso de proveedor, acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que se admite para su organización.

Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página de **Configuración perimetral de acceso** :

  - **Habilitar la federación y la conectividad de mensajería instantánea pública**   habilite esta opción si desea admitir el acceso de usuarios para dominios de socio federado. Esta configuración se aplica a SIP federación configuradas para global, de sitio o de los ámbitos de usuario en la página **Directiva de acceso externo** . Para que la configuración de federación que se debe aplicar, debe configurar la compatibilidad con la federación en ambas páginas.
    
    Existen dos opciones que son valores de configuración opcionales para cómo se detectan los socios federados y si la declinación de responsabilidades de archivado (notificación a los contactos asociados externos comunicarse con el que la implementación tiene habilitado el archivado y que las comunicaciones se archivarán detalles) se van a enviar a los contactos:
    
      - **Habilitar la detección de dominio de socio**   al seleccionar esta opción permite la detección automática de dominios que se pueden federar con. Skype para Business Server utiliza los registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios no incluidos en la lista de dominios permitidos, evaluar el tráfico entrante de los socios federados detectados automáticamente y limitar o bloquear ese tráfico en función de confianza nivel, de la cantidad de tráfico y las configuraciones de administrador. Si no selecciona esta opción, está habilitado el acceso de usuario federado sólo para los usuarios en los dominios que incluyen en la lista de dominios permitidos. Si selecciona esta opción, puede especificar ese individuo dominios bloqueados o permitidos, incluida la restricción del acceso a servidores específicos que ejecutan el servicio de servidor perimetral de acceso en el dominio federado. Para obtener información detallada, vea [Configurar compatibilidad para dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Envío de renuncia de archivado a los socios federados**   al seleccionar esta opción permite el envío de un mensaje de renuncia de archivado a los socios federados que le informa de ellos que se registran los detalles de las comunicaciones. Si archiva las comunicaciones externas con dominios de socios federados, debe habilitar la notificación de renuncia de archivado advertir a los socios que se van a archivar sus detalles de los mensajes y las comunicaciones por su implementación. Para obtener información detallada sobre el archivado, vea [Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitar el acceso de usuarios remotos**   habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, por ejemplo, los usuarios que están de viaje, que puedan conectarse a Skype para Business Server y los teletrabajadores. Para obtener información detallada, vea [Habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).

  - **Permitir a los usuarios anónimos obtener acceso a las conferencias**   habilite esta opción si desea que los usuarios internos invitar a usuarios anónimos externos a las conferencias que organizan. Si se habilita a esta opción, sólo permite a los usuarios anónimos para las conferencias.

> [!NOTE]  
> Además de habilitar el acceso de usuarios externos de soporte, también configurar directivas para controlar el uso de acceso de usuarios remotos en su organización antes de cualquier tipo de acceso de usuarios externos está disponible para los usuarios. Para obtener información detallada sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [Administrar la directiva de acceso externo para su organización](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualización de información de configuración del servidor perimetral de acceso mediante el uso de cmdlets de Windows PowerShell**

  - Información de configuración de acceso perimetral puede verse mediante el uso de Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration** . Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 
    
    Para ver información acerca de todas las opciones de configuración de servidor perimetral de acceso, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
     `Get-CsAccessEdgeConfiguration`
    
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

