---
title: Administrae la configuración perimetral de acceso para su organización
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de implementar uno o varios servidores perimetrales, debe habilitar el acceso de los tipos de dominios externos o proveedores, el acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que serán compatibles con su organización.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818351"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Administrae la configuración perimetral de acceso para su organización

Después de implementar uno o varios servidores perimetrales, debe habilitar el acceso de los tipos de dominios externos o proveedores, el acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que serán compatibles con su organización.

Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **configuración de Edge de Access** :

  - **Habilitar Federación y conectividad**   de mensajería instantánea pública habilite esta opción si desea permitir el acceso de los usuarios a dominios federados de socios federados. Esta configuración se aplica a la Federación SIP configurada para el ámbito global, de sitio o de usuario en la página **Directiva de acceso externo** . Para que se aplique la configuración de Federación, debe configurar la compatibilidad de Federación en ambas páginas.
    
    Existen dos opciones opcionales para la forma en que se detectan los socios federados, y si se archivan descargos de responsabilidad (notificación a los contactos federados con los que se comunica que su implementación tiene habilitado el archivado y que las comunicaciones los detalles que se archivarán se enviarán a los contactos:
    
      - **Habilitar la detección**   de dominios asociados al seleccionar esta opción se habilita la detección automática de dominios con los que se puede federar. Skype empresarial Server usa registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios que no aparecen en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados descubiertos y limitar o bloquear ese tráfico en función de la confianza. nivel, cantidad de tráfico y configuración de administrador. Si no selecciona esta opción, acceso de usuarios federados solo se habilitará para los usuarios de los dominios que incluya en la lista de dominios permitidos. Independientemente de si selecciona esta opción, puede especificar que los dominios individuales se bloqueen o se permitan, incluido el acceso restringido a servidores específicos que ejecuten el servicio perimetral de acceso en el dominio federado. Para obtener más información, vea [configurar la compatibilidad de dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Enviar renuncia de archivado a socios**   federados la selección de esta opción permite el envío de un mensaje de renuncia de archivado a socios federados que les informa de que se registran los detalles de la comunicación. Si archiva comunicaciones externas con dominios federados de socios federados, debe habilitar la notificación de renuncia de archivado para avisar a los socios de que su implementación ha archivado sus mensajes y sus detalles de comunicaciones. Para obtener más información sobre el archivado, vea [habilitar o deshabilitar el envío de una renuncia de archivado a un socio federado](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitar el acceso**   de usuarios remotos habilite esta opción si quiere que los usuarios de su organización que estén fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Skype empresarial Server. Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).

  - **Permitir el acceso de usuarios anónimos**   a las conferencias habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organizan. Habilitar esta opción solo permite usuarios anónimos en conferencias.

> [!NOTE]  
> Además de habilitar la compatibilidad con el acceso de usuarios externos, también puede configurar directivas para controlar el uso del acceso de usuarios remotos de su organización antes de que los usuarios puedan tener acceso a cualquier tipo de acceso de usuario externo. Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [administrar la Directiva de acceso externo para su organización](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Ver la información de configuración perimetral de acceso mediante cmdlets de Windows PowerShell**

  - La información de configuración perimetral de acceso se puede ver con Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 
    
    Para ver la información acerca de todas las opciones de configuración de Edge de Access, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
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

