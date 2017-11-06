---
title: Configurar el acceso de invitado a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Habilite la característica de acceso de invitado en Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a><span data-ttu-id="2db4d-103">Configurar el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2db4d-103">Set up guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="2db4d-104">Microsoft Teams se creó a partir de los grupos de Office 365 y también depende de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2db4d-104">Microsoft Teams is built upon Office 365 Groups, and it also relies on SharePoint Online.</span></span> <span data-ttu-id="2db4d-105">Es por ello que se debe habilitar una configuración específica en los grupos de Office 365 y en SharePoint Online, además de tener que activar la característica de acceso de invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="2db4d-105">That’s why specific settings must be enabled in Office 365 Groups and SharePoint Online in addition to turning on the guest access feature in Teams.</span></span>


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a><span data-ttu-id="2db4d-106">Permitir la adición de invitados en Grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="2db4d-106">Allow the addition of guests in Office 365 Groups</span></span>
<span data-ttu-id="2db4d-107"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="2db4d-107"></span></span>


1. <span data-ttu-id="2db4d-108">Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="2db4d-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="2db4d-109">En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.</span><span class="sxs-lookup"><span data-stu-id="2db4d-109">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="2db4d-110">Seleccione **Grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2db4d-110">Select **Office 365 Groups**.</span></span>
    
     ![Grupos de Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="2db4d-112">En la página de grupos de Office 365, configure el botón de alternancia en **Activado** o **Desactivado**, dependiendo de si quiere que los propietarios del equipo y el grupo que no pertenecen a la organización accedan a los grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2db4d-112">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="2db4d-113">Pulse o haga clic en el botón de alternancia, cambie a **Activado** junto a **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización).</span><span class="sxs-lookup"><span data-stu-id="2db4d-113">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>


![La captura de pantalla muestra el panel Grupos de Office 365 con las opciones activadas para permitir que los miembros del grupo externos a la organización accedan al contenido del grupo y para permitir que los propietarios del grupo agreguen a los grupos personas que no pertenecen a la organización.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a><span data-ttu-id="2db4d-115">Habilitar el uso compartido en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2db4d-115">Enable sharing in SharePoint Online</span></span>

<span data-ttu-id="2db4d-116">Con la opción Compartir en SharePoint Online, es posible agregar a los invitados a su organización.</span><span class="sxs-lookup"><span data-stu-id="2db4d-116">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="2db4d-117">De forma predeterminada, la opción Compartir está habilitada.</span><span class="sxs-lookup"><span data-stu-id="2db4d-117">By default, the Sharing option is enabled.</span></span> <span data-ttu-id="2db4d-118">Si desea más información sobre cómo se desactiva la opción Compartir, consulte [Activar o desactivar la opción de uso compartido](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span><span class="sxs-lookup"><span data-stu-id="2db4d-118">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
   <span data-ttu-id="2db4d-119">Los administradores pueden crear cuentas de invitado en Azure Active Directory, aparte de la configuración del uso compartido externo.</span><span class="sxs-lookup"><span data-stu-id="2db4d-119">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="2db4d-120">Si este uso está desactivado, solo el administrador podrá crear cuentas de invitado.</span><span class="sxs-lookup"><span data-stu-id="2db4d-120">If external sharing is off, only an admin can create guest accounts.</span></span> 
    

> [!IMPORTANT]
> <span data-ttu-id="2db4d-121">Si desactiva la opción Compartir, el acceso de invitado no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="2db4d-121">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="2db4d-122">Activar o desactivar el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2db4d-122">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="2db4d-123"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="2db4d-123"></span></span>

<span data-ttu-id="2db4d-124">Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados.</span><span class="sxs-lookup"><span data-stu-id="2db4d-124">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="2db4d-125">La configuración de invitado se establece en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2db4d-125">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="2db4d-126">Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2db4d-126">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="2db4d-127">Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.</span><span class="sxs-lookup"><span data-stu-id="2db4d-127">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>



1. <span data-ttu-id="2db4d-128">Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="2db4d-128">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="2db4d-129">En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.</span><span class="sxs-lookup"><span data-stu-id="2db4d-129">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Inicie sesión en Office 365, acceda al Centro de administración de Office 365, seleccione Configuración y, a continuación, elija Servicios y complementos.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="2db4d-131">Seleccione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="2db4d-131">Select **Microsoft Teams**.</span></span>
    
     ![La captura de pantalla muestra la opción del complemento de Microsoft Teams, como se selecciona en el Centro de administración de Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="2db4d-133">En **Select the user/license type you want to configure** (Seleccione el tipo de usuario/licencia que desea configurar), seleccione **Invitado**.</span><span class="sxs-lookup"><span data-stu-id="2db4d-133">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![La captura de pantalla del complemento de Microsoft Teams muestra la licencia de invitado seleccionada y la opción de Microsoft Teams establecida en Activado.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="2db4d-135">Pulse o haga clic en el botón de alternancia que hay junto a **Turn Microsoft Teams on or off for all users of this type** (Activar o desactivar Microsoft Teams para todos los usuarios de este tipo), cambie a **Activado** para activar Microsoft Teams y el acceso de invitado para su organización y, por último, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2db4d-135">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

