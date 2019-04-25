---
title: Habilitar a los usuarios para Enterprise Voice local
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para un usuario usar el sistema telefónico en Office 365 (en la nube PBX), en primer lugar debe habilitarlos para Enterprise Voice y asígneles a un número de teléfono. Para ello, con la implementación local mientras el usuario todavía está hospedado en la implementación local.
ms.openlocfilehash: 1b8329ec4deb90aed6bb9ae93c4a202beebb673c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234080"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="09733-104">Habilitar a los usuarios para Enterprise Voice local</span><span class="sxs-lookup"><span data-stu-id="09733-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="09733-105">Para un usuario usar el sistema telefónico en Office 365 (en la nube PBX), en primer lugar debe habilitarlos para Enterprise Voice y asígneles a un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="09733-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="09733-106">Para ello, con la implementación local mientras el usuario todavía está hospedado en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="09733-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="09733-107">Para habilitar a un usuario para Enterprise Voice local y asignar a un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="09733-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="09733-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="09733-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="09733-109">Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09733-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="09733-110">También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09733-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="09733-111">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="09733-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="09733-112">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="09733-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="09733-113">En la tabla, haga clic en el Skype para la cuenta de usuario en línea de negocio que desea habilitar para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="09733-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="09733-114">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="09733-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="09733-115">En **Telefonía**, haga clic en **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="09733-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="09733-p103">Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="09733-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="09733-118">Consideraciones especiales sobre la habilitación de usuarios para Enterprise Voice local</span><span class="sxs-lookup"><span data-stu-id="09733-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="09733-119">En algunos casos, es posible que necesite modificar la forma en que habilita los usuarios para telefonía IP empresarial, con el fin de asegurarse de que puedan realizar y recibir llamadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="09733-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="09733-120">Si tiene usuarios en su implementación que cumplen las condiciones siguientes, realice los pasos que se incluye para permitir que el usuario para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="09733-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="09733-121">Si un usuario se crea en sus instalaciones AD y, a continuación, sincronizar con Skype para profesionales en línea sin que esté habilitado para Skype para la empresa o para Enterprise Voice y no tienen un LineURI conjunto, ejecute los siguientes cmdlets para cada usuario afectado, reemplazando los valores en < C0 > <b1></b1> con los valores reales para su entorno:</span><span class="sxs-lookup"><span data-stu-id="09733-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="09733-122">Si un usuario ya está habilitado para Skype para la empresa de forma local, pero no se ha habilitado para Enterprise Voice o asignado un LineURI antes de moverse a Skype para profesionales en línea, ejecute el siguiente cmdlet para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="09733-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="09733-123">Si un usuario está ya habilitado en Skype para la empresa local pero no habilitado para Enterprise Voice, incluso si ya ha asignado un LineURI, ejecute el siguiente cmdlet para cada usuario afectado:</span><span class="sxs-lookup"><span data-stu-id="09733-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


