---
title: Mover usuarios locales a Skype para profesionales en línea
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Resumen: Información sobre cómo mover local a los usuarios de Skype para profesionales en línea.'
ms.openlocfilehash: 09eb62c59ccea1334d7f565a0a49989bff72745b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="3a0e1-103">Mover usuarios locales a Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="3a0e1-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="3a0e1-104">**Resumen:** Información sobre cómo mover usuarios locales a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3a0e1-105">Los dispositivos de Lync Phone Edition TIENEN que estar actualizados con el firmware mínimo necesario en su entorno local ANTES de migrar a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="3a0e1-106">Si transfiere los usuarios del entorno local al entorno en línea antes de actualizar el firmware, los usuarios no se podrán conectar con sus teléfonos.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="3a0e1-107">Para corregir este problema, es necesario volver a transferir los usuarios al entorno local para actualizar los teléfonos con el firmware mínimo.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="3a0e1-108">NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO O REALIZAR UN RESTABLECIMIENTO COMPLETO DEL TELÉFONO ANTES DE VOLVER A TRANSFERIR EL USUARIO AL ENTORNO LOCAL.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="3a0e1-109">Si se realiza un restablecimiento completo cuando el dispositivo no tiene instalado el firmware mínimo, se implementará la autenticación con PIN, que no es compatible con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="3a0e1-110">Para obtener más información, consulte [Introducción teléfonos de Skype para profesionales en línea](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a0e1-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="3a0e1-111">Esto es un paso opcional que sólo es necesario si va a mover los usuarios locales a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="3a0e1-112">Antes de comenzar a mover los usuarios a Skype para profesionales en línea, compruebe que la Skype para Business Connector en línea (módulo de Windows PowerShell) se implementa en los servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="3a0e1-113">Si no es así, se puede descargar desde [el centro de descarga](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="3a0e1-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="3a0e1-114">Además, para preparar AD tendrá que configurar Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="3a0e1-115">La versión de AAD Connect que tiene que usar es la versión 1.0.9125.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="3a0e1-116">Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="3a0e1-117">Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="3a0e1-118">Mover los usuarios que utilicen cualquiera Skype para el Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial en su implementación local, pero deben tener credenciales de administrador para la implementación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="3a0e1-119">Mover a los usuarios mediante el uso de Skype para el Panel de Control</span><span class="sxs-lookup"><span data-stu-id="3a0e1-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="3a0e1-120">Para mover un usuario a Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="3a0e1-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="3a0e1-121">Desde una cuenta de usuario que se asigna al rol CsUserAdministrator o csadministrator, inicie sesión en cualquier equipo en la implementación interna que tenga Skype para Business Server o al menos Skype para herramientas de administración del servidor empresarial instalado.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="3a0e1-122">En el menú Inicio o un acceso directo de escritorio, abra el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="3a0e1-123">También puede obtener acceso el Skype para el Panel de Control de servidor empresarial mediante el uso de la dirección URL de administración si ha configurado uno.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="3a0e1-124">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3a0e1-125">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3a0e1-126">Haga clic en el usuario y, después, en el menú **Acción**, haga clic en **Mover usuarios seleccionados a Skype Empresarial Online**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="3a0e1-127">En la página **Mover usuarios a Skype Empresarial Online**, lea la información y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="3a0e1-128">En la página siguiente, si no aún inicia sesión Office 365, haga clic en **iniciar sesión en Office 365**, proporcione las credenciales y haga clic en **Aceptar** y en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="3a0e1-129">Confirme que el número de usuarios que se transferirán es correcto y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="3a0e1-130">En la página siguiente, revise los resultados y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3a0e1-131">Mover a los usuarios mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="3a0e1-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3a0e1-132">Para mover un usuario local a su Skype para inquilino en línea de negocio, ejecute los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial, con las credenciales de administrador para el inquilino de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="3a0e1-133">Sustituya “username@contoso.com” por la información del usuario que quiera mover.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="3a0e1-134">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato: _Https://\<FQDN del grupo de servidores\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="3a0e1-135">Puede determinar la dirección URL para el servicio de migración hospedado mediante la visualización de la dirección URL para el Skype para el centro de administración en línea de negocio para su cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a0e1-136">La URL distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="3a0e1-137">Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365</span><span class="sxs-lookup"><span data-stu-id="3a0e1-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="3a0e1-138">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="3a0e1-139">Abra el **Centro de administración de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="3a0e1-140">Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a0e1-140">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="3a0e1-141">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="3a0e1-141">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="3a0e1-142">Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedado.svc **.</span><span class="sxs-lookup"><span data-stu-id="3a0e1-142">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="3a0e1-143">La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a0e1-143">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

