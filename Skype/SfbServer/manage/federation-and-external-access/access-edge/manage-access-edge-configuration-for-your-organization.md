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
localization_priority: Normal
description: Después de implementar uno o varios servidores perimetrales, debe habilitar el acceso de los tipos de dominios externos o proveedores, el acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que serán compatibles con su organización.
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280197"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="e5c2c-103">Administrae la configuración perimetral de acceso para su organización</span><span class="sxs-lookup"><span data-stu-id="e5c2c-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="e5c2c-104">Después de implementar uno o varios servidores perimetrales, debe habilitar el acceso de los tipos de dominios externos o proveedores, el acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que serán compatibles con su organización.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="e5c2c-105">Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **configuración de Edge de Access** :</span><span class="sxs-lookup"><span data-stu-id="e5c2c-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="e5c2c-106">**Habilitar Federación y conectividad**   de mensajería instantánea pública habilite esta opción si desea permitir el acceso de los usuarios a dominios federados de socios federados.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="e5c2c-107">Esta configuración se aplica a la Federación SIP configurada para el ámbito global, de sitio o de usuario en la página **Directiva de acceso externo** .</span><span class="sxs-lookup"><span data-stu-id="e5c2c-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="e5c2c-108">Para que se aplique la configuración de Federación, debe configurar la compatibilidad de Federación en ambas páginas.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="e5c2c-109">Existen dos opciones opcionales para la forma en que se detectan los socios federados, y si se archivan descargos de responsabilidad (notificación a los contactos federados con los que se comunica que su implementación tiene habilitado el archivado y que las comunicaciones los detalles que se archivarán se enviarán a los contactos:</span><span class="sxs-lookup"><span data-stu-id="e5c2c-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="e5c2c-110">**Habilitar la detección**   de dominios asociados al seleccionar esta opción se habilita la detección automática de dominios con los que se puede federar.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="e5c2c-111">Skype empresarial Server usa registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios que no aparecen en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados descubiertos y limitar o bloquear ese tráfico en función de la confianza. nivel, cantidad de tráfico y configuración de administrador.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="e5c2c-112">Si no selecciona esta opción, acceso de usuarios federados solo se habilitará para los usuarios de los dominios que incluya en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="e5c2c-113">Independientemente de si selecciona esta opción, puede especificar que los dominios individuales se bloqueen o se permitan, incluido el acceso restringido a servidores específicos que ejecuten el servicio perimetral de acceso en el dominio federado.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="e5c2c-114">Para obtener más información, vea [configurar la compatibilidad de dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="e5c2c-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="e5c2c-115">**Enviar renuncia de archivado a socios**   federados la selección de esta opción permite el envío de un mensaje de renuncia de archivado a socios federados que les informa de que se registran los detalles de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="e5c2c-116">Si archiva comunicaciones externas con dominios federados de socios federados, debe habilitar la notificación de renuncia de archivado para avisar a los socios de que su implementación ha archivado sus mensajes y sus detalles de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="e5c2c-117">Para obtener más información sobre el archivado, vea [habilitar o deshabilitar el envío de una renuncia de archivado a un socio federado](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="e5c2c-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="e5c2c-118">**Habilitar el acceso**   de usuarios remotos habilite esta opción si quiere que los usuarios de su organización que estén fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="e5c2c-119">Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e5c2c-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="e5c2c-120">**Permitir el acceso de usuarios anónimos**   a las conferencias habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organizan.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="e5c2c-121">Habilitar esta opción solo permite usuarios anónimos en conferencias.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="e5c2c-122">Además de habilitar la compatibilidad con el acceso de usuarios externos, también puede configurar directivas para controlar el uso del acceso de usuarios remotos de su organización antes de que los usuarios puedan tener acceso a cualquier tipo de acceso de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="e5c2c-123">Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [administrar la Directiva de acceso externo para su organización](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e5c2c-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="e5c2c-124">**Ver la información de configuración perimetral de acceso mediante cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e5c2c-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="e5c2c-125">La información de configuración perimetral de acceso se puede ver con Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e5c2c-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="e5c2c-126">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="e5c2c-127">Para ver la información acerca de todas las opciones de configuración de Edge de Access, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="e5c2c-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="e5c2c-128">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5c2c-128">That will return information similar to this:</span></span>
    
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

