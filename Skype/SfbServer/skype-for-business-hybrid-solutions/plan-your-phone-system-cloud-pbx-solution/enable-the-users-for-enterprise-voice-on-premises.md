---
title: Habilitar a los usuarios para Enterprise Voice local
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
description: Para que un usuario Use un sistema telefónico en Office 365 (PBX en la nube), primero debe habilitarlo para telefonía IP empresarial y asignarle un número de teléfono. Esto se hace con la implementación local mientras el usuario aún está alojado en la implementación local.
ms.openlocfilehash: 4409de1965fbcca641dde69d70c734d1bcd3a8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802300"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="5685a-104">Habilitar a los usuarios para Enterprise Voice local</span><span class="sxs-lookup"><span data-stu-id="5685a-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="5685a-105">Para que un usuario Use un sistema telefónico en Office 365 (PBX en la nube), primero debe habilitarlo para telefonía IP empresarial y asignarle un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="5685a-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="5685a-106">Esto se hace con la implementación local mientras el usuario aún está alojado en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="5685a-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="5685a-107">Para habilitar un usuario para Enterprise Voice local y asignar un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="5685a-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="5685a-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5685a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5685a-109">Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5685a-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="5685a-110">También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5685a-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5685a-111">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5685a-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="5685a-112">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5685a-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="5685a-113">En la tabla, haga clic en la cuenta de usuario de Skype empresarial online que desea habilitar para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5685a-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="5685a-114">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5685a-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="5685a-115">En **Telefonía**, haga clic en **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="5685a-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="5685a-p103">Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5685a-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="5685a-118">Consideraciones especiales al habilitar usuarios para Enterprise Voice local</span><span class="sxs-lookup"><span data-stu-id="5685a-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="5685a-119">En algunos casos, es posible que necesite modificar la forma en que habilita los usuarios para telefonía IP empresarial, con el fin de asegurarse de que puedan realizar y recibir llamadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="5685a-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="5685a-120">Si tiene usuarios de su implementación que cumplen las siguientes condiciones, realice los pasos que se incluyen para habilitar al usuario para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5685a-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="5685a-121">Si se crea un usuario en su ad local y, a continuación, se sincroniza con Skype empresarial online sin estar habilitado para Skype empresarial o para telefonía IP empresarial y no tiene un conjunto de LineURI, ejecute los siguientes cmdlets para cada usuario afectado, sustituyendo los \< \> valores de con los valores reales de su entorno:</span><span class="sxs-lookup"><span data-stu-id="5685a-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="5685a-122">Si un usuario ya está habilitado para Skype empresarial local, pero no se ha habilitado para telefonía IP empresarial o ha asignado un LineURI antes de moverlo a Skype empresarial online, ejecute el siguiente cmdlet para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="5685a-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="5685a-123">Si un usuario ya está habilitado en Skype empresarial local pero no habilitado para telefonía IP empresarial, incluso si ya tiene asignada una LineURI, ejecute el siguiente cmdlet para cada usuario afectado:</span><span class="sxs-lookup"><span data-stu-id="5685a-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


