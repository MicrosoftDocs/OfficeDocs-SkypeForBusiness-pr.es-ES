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
description: Después de implementar uno o más servidores perimetrales, debe habilitar los tipos de acceso de proveedor o dominio externo, el acceso de usuarios remotos y el acceso de usuarios anónimos a conferencias a través de los servidores perimetrales que serán compatibles con su organización.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817340"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="a3443-103">Administrar la configuración perimetral de acceso para su organización</span><span class="sxs-lookup"><span data-stu-id="a3443-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="a3443-104">Después de implementar uno o más servidores perimetrales, debe habilitar los tipos de acceso de proveedor o dominio externo, el acceso de usuarios remotos y el acceso de usuarios anónimos a conferencias a través de los servidores perimetrales que serán compatibles con su organización.</span><span class="sxs-lookup"><span data-stu-id="a3443-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="a3443-105">Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **Configuración perimetral de acceso**:</span><span class="sxs-lookup"><span data-stu-id="a3443-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="a3443-106">**Habilitar la federación y la conectividad de mensajería instantánea pública**   Habilite esta opción si desea admitir el acceso de usuarios a dominios de socios federados.</span><span class="sxs-lookup"><span data-stu-id="a3443-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="a3443-107">Esta configuración se aplica a la federación SIP configurada para ámbitos globales, de sitio o de usuario en la **página Directiva de acceso** externo.</span><span class="sxs-lookup"><span data-stu-id="a3443-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="a3443-108">Para que se aplique la configuración de federación, debe configurar la compatibilidad con la federación en ambas páginas.</span><span class="sxs-lookup"><span data-stu-id="a3443-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="a3443-109">Existen dos opciones que son opciones opcionales para detectar socios federados y si se enviarán avisos de declinación de responsabilidades de archivado (notificación a los contactos federados con los que se comunica que la implementación tiene el archivado habilitado y que se archivarán los detalles de las comunicaciones) a los contactos:</span><span class="sxs-lookup"><span data-stu-id="a3443-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="a3443-110">**Habilitar la detección de dominios asociados**   Al seleccionar esta opción, se habilita la detección automática de dominios con los que puede federar.</span><span class="sxs-lookup"><span data-stu-id="a3443-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="a3443-111">Skype Empresarial Server usa registros del Sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluando automáticamente el tráfico entrante de socios federados detectados y limitando o bloqueando ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración del administrador.</span><span class="sxs-lookup"><span data-stu-id="a3443-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="a3443-112">Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos.</span><span class="sxs-lookup"><span data-stu-id="a3443-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="a3443-113">Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado.</span><span class="sxs-lookup"><span data-stu-id="a3443-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="a3443-114">Para obtener más información, consulte [Configurar la compatibilidad con dominios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="a3443-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="a3443-115">**Enviar declinación de responsabilidades de archivado a socios federados**   La selección de esta opción permite enviar un mensaje de declinación de responsabilidades de archivado a socios federados que les informa de que se registran los detalles de las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="a3443-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="a3443-116">Si archiva comunicaciones externas con dominios de socios federados, debe habilitar la notificación de declinación de responsabilidades de archivado para advertir a los asociados de que la implementación archiva sus mensajes y detalles de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="a3443-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="a3443-117">Para obtener más información sobre el archivado, vea Habilitar o deshabilitar el envío de un aviso de declinación de responsabilidades [de archivado a un socio federado.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="a3443-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="a3443-118">**Habilitar el acceso de usuarios remotos**   Habilite esta opción si desea que los usuarios de su organización que están fuera del firewall, como los teletrabadores y los usuarios que están de viaje, puedan conectarse a Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a3443-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="a3443-119">Para obtener más información, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="a3443-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="a3443-120">**Permitir que los usuarios anónimos accedan a conferencias**   Habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organizan.</span><span class="sxs-lookup"><span data-stu-id="a3443-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="a3443-121">Si se habilita esta opción, solo se permite a los usuarios anónimos realizar conferencias.</span><span class="sxs-lookup"><span data-stu-id="a3443-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="a3443-122">Además de habilitar la compatibilidad de acceso de usuario externo, también configura las directivas para controlar el uso del acceso de usuario remoto en su organización antes de que cualquier tipo de acceso de usuario esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a3443-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="a3443-123">Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea Administrar la directiva de acceso [externo para su organización.](../external-access-policies/manage-external-access-policy-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="a3443-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="a3443-124">**Visualización de la información de configuración perimetral de acceso mediante cmdlets Windows PowerShell acceso**</span><span class="sxs-lookup"><span data-stu-id="a3443-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="a3443-125">La información de configuración perimetral de acceso se puede ver mediante Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a3443-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="a3443-126">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3443-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="a3443-127">Para ver información sobre todas las opciones de configuración perimetral de acceso, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a3443-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="a3443-128">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3443-128">That will return information similar to this:</span></span>
    
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

