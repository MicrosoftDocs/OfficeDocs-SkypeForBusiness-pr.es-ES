---
title: Habilitar a los usuarios para Telefonía IP empresarial local
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que un usuario use sistema telefónico (PBX en la nube), primero debe habilitarlos para Telefonía IP empresarial y asignarles un número de teléfono. Para ello, use la implementación local mientras el usuario aún esté en la implementación local.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359196"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="62c64-104">Habilitar a los usuarios para Telefonía IP empresarial local</span><span class="sxs-lookup"><span data-stu-id="62c64-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="62c64-105">Para que un usuario use sistema telefónico (PBX en la nube), primero debe habilitarlos para Telefonía IP empresarial y asignarles un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="62c64-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="62c64-106">Para ello, use la implementación local mientras el usuario aún esté en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="62c64-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="62c64-107">Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.</span><span class="sxs-lookup"><span data-stu-id="62c64-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="62c64-108">Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="62c64-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="62c64-109">Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="62c64-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="62c64-110">Para habilitar un usuario para Telefonía IP empresarial local y asignar un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="62c64-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="62c64-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="62c64-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62c64-112">Use el menú Inicio o el acceso directo de escritorio para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="62c64-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="62c64-113">También puede abrir una ventana del explorador y, a continuación, escribir la dirección URL del administrador para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="62c64-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="62c64-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="62c64-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="62c64-115">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="62c64-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="62c64-116">En la tabla, haga clic en la cuenta de usuario de Skype Empresarial Online que desea habilitar para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="62c64-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="62c64-117">En el **menú Editar,** haga clic **en Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="62c64-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="62c64-118">En **Telefonía,** haga clic **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="62c64-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="62c64-119">Haga **clic en URI** de línea y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="62c64-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="62c64-120">A continuación, haga clic **en Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="62c64-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="62c64-121">Consideraciones especiales al habilitar usuarios para Telefonía IP empresarial local</span><span class="sxs-lookup"><span data-stu-id="62c64-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="62c64-122">En algunos casos, es posible que deba modificar la forma en que habilita a los usuarios Telefonía IP empresarial para asegurarse de que pueden realizar y recibir llamadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="62c64-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="62c64-123">Si tiene usuarios en la implementación que cumplen las siguientes condiciones, realice los pasos incluidos para habilitar al usuario para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="62c64-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="62c64-124">Si se crea un usuario en ad local y, a continuación, se sincroniza con Skype Empresarial Online sin estar habilitado para Skype Empresarial o para Telefonía IP empresarial y no tiene un conjunto lineURI, ejecute los cmdlets siguientes para cada usuario afectado, reemplazando los valores por valores reales para \< \> su entorno:</span><span class="sxs-lookup"><span data-stu-id="62c64-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="62c64-125">Si un usuario ya está habilitado para Skype Empresarial local, pero no se ha habilitado para Telefonía IP empresarial o se le ha asignado un LineURI antes de moverlo a Skype Empresarial Online, ejecute el siguiente cmdlet para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="62c64-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="62c64-126">Si un usuario ya está habilitado en Skype Empresarial local pero no está habilitado para Telefonía IP empresarial, incluso si ya se ha asignado un LineURI, ejecute el siguiente cmdlet para cada usuario afectado:</span><span class="sxs-lookup"><span data-stu-id="62c64-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


