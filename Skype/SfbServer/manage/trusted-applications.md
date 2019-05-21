---
title: Administrar aplicaciones de confianza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Una aplicación de confianza es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Skype empresarial Server.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275069"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="9bffc-103">Administrar aplicaciones de confianza en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9bffc-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="9bffc-104">Una *aplicación de confianza* es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9bffc-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="9bffc-105">Para obtener más información acerca de las aplicaciones de UCMA, consulte "documentación de SDK de comunicaciones http://go.microsoft.com/fwlink/p/?linkId=210320unificadas de la API de Core 3,0" en.</span><span class="sxs-lookup"><span data-stu-id="9bffc-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="9bffc-106">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9bffc-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="9bffc-107">Use este artículo para aprender a configurar un nuevo servidor de aplicaciones de confianza, ver una lista de aplicaciones de confianza y ver la información de la aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="9bffc-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="9bffc-108">Configurar un nuevo servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="9bffc-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="9bffc-109">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9bffc-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="9bffc-110">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Skype empresarial Server**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="9bffc-111">Seleccione **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="9bffc-112">En el cuadro de diálogo **Guardar topología como** , haga clic en el archivo del generador de topología que desea usar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="9bffc-113">En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza**y luego haga clic en **nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="9bffc-114">Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o de varios servidores y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="9bffc-115">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9bffc-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="9bffc-116">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="9bffc-117">Seleccione el nodo superior de **Skype empresarial Server**y, a continuación, en el menú **acciones** , haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="9bffc-118">El **grupo de aplicaciones de confianza** se creó correctamente y se asoció con el grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="9bffc-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="9bffc-119">Ver una lista de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="9bffc-119">View a list of trusted applications</span></span>

<span data-ttu-id="9bffc-120">Puede usar el panel de control de Skype empresarial Server para ver una lista de las aplicaciones de confianza que ha implementado en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9bffc-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="9bffc-121">Una aplicación de confianza es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9bffc-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="9bffc-122">Esta relación de confianza se resume en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="9bffc-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="9bffc-123">Las aplicaciones de confianza no son desafiadas para la autenticación por parte de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9bffc-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="9bffc-124">Skype empresarial Server no limita las aplicaciones de confianza para las transacciones SIP, las conexiones o las llamadas salientes de protocolo de voz a través de Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="9bffc-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="9bffc-125">Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden unirse a conferencias sin aparecer en las listas.</span><span class="sxs-lookup"><span data-stu-id="9bffc-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="9bffc-126">Las aplicaciones de confianza son altamente disponibles y resistentes.</span><span class="sxs-lookup"><span data-stu-id="9bffc-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="9bffc-127">En el panel de control de Skype empresarial Server, puede ver el nombre de las aplicaciones, el grupo donde se ejecutan y el puerto que usan.</span><span class="sxs-lookup"><span data-stu-id="9bffc-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="9bffc-128">Para ver una lista de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="9bffc-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="9bffc-129">Inicie sesión en cualquier equipo en la implementación interna desde una cuenta de usuario que esté asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9bffc-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="9bffc-130">Para más información sobre los roles administrativos predefinidos disponibles en Skype empresarial Server, consulte [control de acceso basado en roles (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="9bffc-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="9bffc-131">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9bffc-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="9bffc-132">En la barra de navegación izquierda, haga clic en **topología**y, a continuación, haga clic en **aplicación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="9bffc-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="9bffc-133">En la página de la **aplicación de confianza** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9bffc-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="9bffc-134">Ver información de la aplicación de confianza</span><span class="sxs-lookup"><span data-stu-id="9bffc-134">View trusted application information</span></span>

<span data-ttu-id="9bffc-135">Puede ver información sobre sus aplicaciones de confianza mediante Windows PowerShell y el cmdlet **Get-CsTrustedApplication** .</span><span class="sxs-lookup"><span data-stu-id="9bffc-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="9bffc-136">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bffc-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="9bffc-137">Para ver las aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="9bffc-137">To view trusted applications</span></span>

<span data-ttu-id="9bffc-138">Para ver todas las aplicaciones de confianza, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="9bffc-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="9bffc-139">Este comando devuelve información similar a la siguiente para cada aplicación de confianza:</span><span class="sxs-lookup"><span data-stu-id="9bffc-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="9bffc-140">Para obtener más información, vea [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="9bffc-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
