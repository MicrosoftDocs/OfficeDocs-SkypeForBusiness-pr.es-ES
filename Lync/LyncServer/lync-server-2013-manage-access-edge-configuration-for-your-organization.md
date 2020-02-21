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

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="b8a16-102">Administrar la configuración perimetral de acceso para su organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8a16-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b8a16-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b8a16-104">Esta documentación es preliminar y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="b8a16-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="b8a16-105">Los temas en blanco se incluyen para referencia futura.</span><span class="sxs-lookup"><span data-stu-id="b8a16-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="b8a16-106">Después de implementar uno o varios servidores perimetrales, debe habilitar el acceso de los tipos de dominio o proveedor externo, el acceso de usuarios remotos y el acceso de usuarios anónimos a las conferencias a través de los servidores perimetrales que serán compatibles con la organización.</span><span class="sxs-lookup"><span data-stu-id="b8a16-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="b8a16-107">Estas opciones incluyen los siguientes tipos de acceso que se pueden configurar a través de la página **Configuración perimetral de acceso**:</span><span class="sxs-lookup"><span data-stu-id="b8a16-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="b8a16-108">**Habilitar la Federación y la conectividad**   de mensajería instantánea pública habilite esta funcionalidad si desea admitir el acceso del usuario a dominios de socios federados.</span><span class="sxs-lookup"><span data-stu-id="b8a16-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="b8a16-109">Esta configuración se aplica a la Federación SIP y a la Federación XMPP que están configuradas para los ámbitos globales, de sitio o de usuario en la página **Directiva de acceso externo** .</span><span class="sxs-lookup"><span data-stu-id="b8a16-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="b8a16-110">Para que se aplique la configuración de Federación, debe configurar la compatibilidad de Federación en ambas páginas.</span><span class="sxs-lookup"><span data-stu-id="b8a16-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="b8a16-111">Existen dos opciones que son valores opcionales para la manera en que se detectan los socios federados y si las renuncias de archivado (notificación a contactos federados con los que se comunica que su implementación tiene el archivado habilitado y que se archivarán los detalles de comunicaciones) se enviarán a los contactos</span><span class="sxs-lookup"><span data-stu-id="b8a16-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="b8a16-112">**Habilitar detección**   del dominio del asociado: al seleccionar esta opción, se habilita la detección automática de dominios con los que se puede federar.</span><span class="sxs-lookup"><span data-stu-id="b8a16-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="b8a16-113">Lync Server 2013 usa registros del sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados detectados y limitar o bloquear el tráfico en función del nivel de confianza. la cantidad de tráfico y la configuración del administrador.</span><span class="sxs-lookup"><span data-stu-id="b8a16-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="b8a16-114">Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos.</span><span class="sxs-lookup"><span data-stu-id="b8a16-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="b8a16-115">Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado.</span><span class="sxs-lookup"><span data-stu-id="b8a16-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="b8a16-116">Para obtener más información, consulte [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="b8a16-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="b8a16-117">**Enviar renuncia de archivado a socios**   federados la selección de esta opción permite enviar un mensaje de renuncia de archivado a socios federados que les informa de que se registran los detalles de comunicación.</span><span class="sxs-lookup"><span data-stu-id="b8a16-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="b8a16-118">Si archiva las comunicaciones externas con dominios de socios federados, debe habilitar la notificación de renuncia de archivado para avisar a los socios de que su implementación ha archivado los detalles de sus mensajes y comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="b8a16-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="b8a16-119">Para obtener más información sobre el archivado, vea [definir los requisitos para el archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="b8a16-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="b8a16-120">**Habilitar el acceso**   de usuarios remotos habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8a16-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="b8a16-121">Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b8a16-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="b8a16-122">**Permitir que los usuarios anónimos obtengan acceso**   a las conferencias habilite esta opción si desea que los usuarios internos inviten a usuarios anónimos externos a conferencias que organizan.</span><span class="sxs-lookup"><span data-stu-id="b8a16-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="b8a16-123">Al habilitar esta configuración, solo se permiten usuarios anónimos para conferencias.</span><span class="sxs-lookup"><span data-stu-id="b8a16-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="b8a16-124">Para configurar la experiencia de conferencia y las opciones que definen cómo y lo que los usuarios pueden hacer con las conferencias y para la inclusión de usuarios anónimos, vea los detalles en [Create or Modify Conferencing Conference User Experience for a site o users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing Policy Setting Reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b8a16-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8a16-125">Además de habilitar la compatibilidad de acceso de usuario externo, también configura las directivas para controlar el uso del acceso de usuario remoto en su organización antes de que cualquier tipo de acceso de usuario esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8a16-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="b8a16-126">Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">administrar la Directiva de acceso externo en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8a16-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b8a16-127">**Visualización de la información de configuración perimetral de acceso mediante cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b8a16-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="b8a16-128">La información de configuración perimetral de acceso se puede ver con Windows PowerShell y el cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b8a16-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="b8a16-129">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8a16-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b8a16-130">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="b8a16-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="b8a16-131">Para ver información sobre todas las opciones de configuración perimetral de acceso, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b8a16-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="b8a16-132">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8a16-132">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="b8a16-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b8a16-133">In This Section</span></span>

  - [<span data-ttu-id="b8a16-134">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="b8a16-135">Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="b8a16-136">Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="b8a16-137">Habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="b8a16-138">Habilitar o deshabilitar el acceso de usuarios anónimos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="b8a16-139">Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8a16-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

