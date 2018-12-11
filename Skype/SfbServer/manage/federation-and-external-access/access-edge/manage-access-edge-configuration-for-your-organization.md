---
title: Administrae la configuración perimetral de acceso para su organización
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
ms.openlocfilehash: 40fdbd6e728276897e4901c849dc0e2284635ecf
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222922"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="040ea-103">Administrae la configuración perimetral de acceso para su organización</span><span class="sxs-lookup"><span data-stu-id="040ea-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="040ea-104">Después de implementar uno o más servidores perimetrales, debe habilitar a los tipos de dominio externo o acceso de proveedor, acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que se admite para su organización.</span><span class="sxs-lookup"><span data-stu-id="040ea-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="040ea-105">Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página de **Configuración perimetral de acceso** :</span><span class="sxs-lookup"><span data-stu-id="040ea-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="040ea-106">**Habilitar la federación y la conectividad de mensajería instantánea pública**   habilite esta opción si desea admitir el acceso de usuarios para dominios de socio federado.</span><span class="sxs-lookup"><span data-stu-id="040ea-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="040ea-107">Esta configuración se aplica a SIP federación configuradas para global, de sitio o de los ámbitos de usuario en la página **Directiva de acceso externo** .</span><span class="sxs-lookup"><span data-stu-id="040ea-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="040ea-108">Para que la configuración de federación que se debe aplicar, debe configurar la compatibilidad con la federación en ambas páginas.</span><span class="sxs-lookup"><span data-stu-id="040ea-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="040ea-109">Existen dos opciones que son valores de configuración opcionales para cómo se detectan los socios federados y si la declinación de responsabilidades de archivado (notificación a los contactos asociados externos comunicarse con el que la implementación tiene habilitado el archivado y que las comunicaciones se archivarán detalles) se van a enviar a los contactos:</span><span class="sxs-lookup"><span data-stu-id="040ea-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="040ea-110">**Habilitar la detección de dominio de socio**   al seleccionar esta opción permite la detección automática de dominios que se pueden federar con.</span><span class="sxs-lookup"><span data-stu-id="040ea-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="040ea-111">Skype para Business Server utiliza los registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios no incluidos en la lista de dominios permitidos, evaluar el tráfico entrante de los socios federados detectados automáticamente y limitar o bloquear ese tráfico en función de confianza nivel, de la cantidad de tráfico y las configuraciones de administrador.</span><span class="sxs-lookup"><span data-stu-id="040ea-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="040ea-112">Si no selecciona esta opción, está habilitado el acceso de usuario federado sólo para los usuarios en los dominios que incluyen en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="040ea-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="040ea-113">Si selecciona esta opción, puede especificar ese individuo dominios bloqueados o permitidos, incluida la restricción del acceso a servidores específicos que ejecutan el servicio de servidor perimetral de acceso en el dominio federado.</span><span class="sxs-lookup"><span data-stu-id="040ea-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="040ea-114">Para obtener información detallada, vea [Configurar compatibilidad para dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="040ea-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="040ea-115">**Envío de renuncia de archivado a los socios federados**   al seleccionar esta opción permite el envío de un mensaje de renuncia de archivado a los socios federados que le informa de ellos que se registran los detalles de las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="040ea-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="040ea-116">Si archiva las comunicaciones externas con dominios de socios federados, debe habilitar la notificación de renuncia de archivado advertir a los socios que se van a archivar sus detalles de los mensajes y las comunicaciones por su implementación.</span><span class="sxs-lookup"><span data-stu-id="040ea-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="040ea-117">Para obtener información detallada sobre el archivado, vea [Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="040ea-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="040ea-118">**Habilitar el acceso de usuarios remotos**   habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, por ejemplo, los usuarios que están de viaje, que puedan conectarse a Skype para Business Server y los teletrabajadores.</span><span class="sxs-lookup"><span data-stu-id="040ea-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="040ea-119">Para obtener información detallada, vea [Habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="040ea-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="040ea-120">**Permitir a los usuarios anónimos obtener acceso a las conferencias**   habilite esta opción si desea que los usuarios internos invitar a usuarios anónimos externos a las conferencias que organizan.</span><span class="sxs-lookup"><span data-stu-id="040ea-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="040ea-121">Si se habilita a esta opción, sólo permite a los usuarios anónimos para las conferencias.</span><span class="sxs-lookup"><span data-stu-id="040ea-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="040ea-122">Además de habilitar el acceso de usuarios externos de soporte, también configurar directivas para controlar el uso de acceso de usuarios remotos en su organización antes de cualquier tipo de acceso de usuarios externos está disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="040ea-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="040ea-123">Para obtener información detallada sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [Administrar la directiva de acceso externo para su organización](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="040ea-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="040ea-124">**Visualización de información de configuración del servidor perimetral de acceso mediante el uso de cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="040ea-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="040ea-125">Información de configuración de acceso perimetral puede verse mediante el uso de Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="040ea-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="040ea-126">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="040ea-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="040ea-127">Para ver información acerca de todas las opciones de configuración de servidor perimetral de acceso, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="040ea-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="040ea-128">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="040ea-128">That will return information similar to this:</span></span>
    
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

