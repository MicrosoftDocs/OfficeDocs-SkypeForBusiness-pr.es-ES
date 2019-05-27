---
title: Comunicarse con usuarios de Microsoft Teams de otra organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Vea cómo configurar Teams para permitir que los usuarios se comuniquen con los usuarios de otra organización.
ms.openlocfilehash: d974197f6daedab030124dfc1117610e3504ae32
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433194"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="b53e0-103">Permitir a los usuarios de su equipo conversar y comunicarse con los usuarios de otra organización de Teams</span><span class="sxs-lookup"><span data-stu-id="b53e0-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="b53e0-104">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="b53e0-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="b53e0-105">Tiene usuarios en diferentes dominios de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b53e0-105">You have users in different domains in your business.</span></span> <span data-ttu-id="b53e0-106">Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="b53e0-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="b53e0-107">Quiere que las personas de su organización usen Teams para ponerse en contacto con personas de empresas específicas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="b53e0-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="b53e0-108">Desea que cualquier persona del mundo que use Teams pueda encontrarse y ponerse en contacto con usted, usando su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b53e0-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="b53e0-109">Si usted y otro usuario habilitan el acceso externo y permiten los dominios de cada uno, esto funcionará.</span><span class="sxs-lookup"><span data-stu-id="b53e0-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="b53e0-110">Si no funciona, el otro usuario debe asegurarse de que su configuración no esté bloqueando su dominio.</span><span class="sxs-lookup"><span data-stu-id="b53e0-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="b53e0-111">Esto permitirá a los usuarios buscar, llamar y enviar mensajes instantáneos, así como configurar reuniones contigo.</span><span class="sxs-lookup"><span data-stu-id="b53e0-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="b53e0-112">Si quiere que los usuarios externos tengan acceso a los equipos y los canales, el acceso de invitados puede ser una mejor manera de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b53e0-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="b53e0-113">Siga los pasos que se indican en este artículo y asegúrese de [activar el acceso de invitado](set-up-guests.md) para que los usuarios puedan comunicarse.</span><span class="sxs-lookup"><span data-stu-id="b53e0-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b53e0-114">Para federarse en este momento dentro del cliente de Microsoft Teams a un usuario externo fuera de su organización que no es actualmente invitado de su AAD/inquilino, debe estar configurado correctamente para un híbrido y pasar a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="b53e0-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="b53e0-115">A partir de 2/25/2019, Teams aún no es compatible con la Federación nativa sin que el usuario del perfil SIP se haya alojado en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="b53e0-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="b53e0-116">Para obtener más información sobre cómo configurar su cuenta para entornos híbridos y después migrada a Teams, consulte [actualizar la implementación híbrida de Skype empresarial a teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span><span class="sxs-lookup"><span data-stu-id="b53e0-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="b53e0-117">Permitir a los usuarios de su equipo conversar y comunicarse con los usuarios de otra organización de Teams</span><span class="sxs-lookup"><span data-stu-id="b53e0-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="b53e0-118">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b53e0-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="b53e0-119">Paso 1: Asegúrese de configurar los puertos y las direcciones URL que se necesitan.</span><span class="sxs-lookup"><span data-stu-id="b53e0-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="b53e0-120">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="b53e0-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="b53e0-121">Paso 2: permitir que su organización se comunique con otra organización de Teams</span><span class="sxs-lookup"><span data-stu-id="b53e0-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="b53e0-122">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b53e0-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="b53e0-123">En el navegación de la izquierda, vaya a **configuración** > de**acceso externo**de la organización.</span><span class="sxs-lookup"><span data-stu-id="b53e0-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="b53e0-124">En la parte superior de la página **acceso externo** , haga clic en **acceso externo** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="b53e0-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="b53e0-125">Si desea permitir que todas las organizaciones de Teams se comuniquen con los usuarios de su organización, vaya al paso 5.</span><span class="sxs-lookup"><span data-stu-id="b53e0-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="b53e0-126">Si desea limitar las organizaciones que pueden comunicarse con los usuarios de su organización, puede permitir todos los dominios excepto algunos, o solo permitir organizaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="b53e0-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="b53e0-127">Para permitir todos los dominios excepto algunos, agregue los dominios que desea bloquear haciendo clic en **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="b53e0-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="b53e0-128">En el panel **Agregar un dominio** , escriba el nombre de dominio, haga clic en **bloqueado** y luego en **listo**.</span><span class="sxs-lookup"><span data-stu-id="b53e0-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="b53e0-129">Para limitar las comunicaciones a organizatioins específicos, agregue esos dominios a la lista con un estado \*\*\*\* de retengo.</span><span class="sxs-lookup"><span data-stu-id="b53e0-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="b53e0-130">Una vez que haya agregado cualquier dominio a la lista de permitidos, las comunicaciones con otras organizaciones se limitarán a las organizaciones cuyos dominios estén en la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="b53e0-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="b53e0-131">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b53e0-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="b53e0-132">A continuación, asegúrese de que el administrador de la organización de otros equipos realiza estos mismos pasos.</span><span class="sxs-lookup"><span data-stu-id="b53e0-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="b53e0-133">Por ejemplo, en su lista de **dominios permitidos** , su administrador debe entrar en el dominio de su empresa si limita las organizaciones que pueden comunicarse con sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="b53e0-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="b53e0-134">Paso 3: pruébelo</span><span class="sxs-lookup"><span data-stu-id="b53e0-134">Step 3 - Test it</span></span>
<span data-ttu-id="b53e0-135">Para probar la configuración, necesita un usuario de teams que no esté detrás de su firewall.</span><span class="sxs-lookup"><span data-stu-id="b53e0-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="b53e0-136">Después de que usted y el administrador de la organización hayan cambiado la configuración de **acceso externo** , debe estar listo.</span><span class="sxs-lookup"><span data-stu-id="b53e0-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="b53e0-137">En la aplicación de Teams, busque la persona por dirección de correo electrónico y envíe una solicitud a una conversación.</span><span class="sxs-lookup"><span data-stu-id="b53e0-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="b53e0-138">Pídale al contacto de su equipo que le envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="b53e0-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="b53e0-139">Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="b53e0-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="b53e0-140">Otra forma de comprobar si el problema es el Firewall es ir a una ubicación WiFi que no esté detrás de su firewall, como una cafetería, y usar Teams para enviar una solicitud a su contacto para conversar.</span><span class="sxs-lookup"><span data-stu-id="b53e0-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="b53e0-141">Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="b53e0-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="b53e0-142">Comunicarse con los usuarios en una organización de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="b53e0-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="b53e0-143">Si está configurando para permitir que los usuarios de su equipo encuentren y se pongan en contacto con usuarios que están en una organización de Skype empresarial y que limitan quién puede comunicarse con sus usuarios, deberá pedirle al administrador de esa organización que siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b53e0-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="b53e0-144">![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial con el **centro de administración de Skype empresarial**</span><span class="sxs-lookup"><span data-stu-id="b53e0-144">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="b53e0-145">Haga que el administrador de la organización Realice estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b53e0-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="b53e0-146">En el centro de administración de Office 365, vaya a **centros** > de administración**equipo & de Skype** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="b53e0-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="b53e0-147">En el **centro de administración de Skype empresarial**, elija**comunicaciones externas**de la **organización** > .</span><span class="sxs-lookup"><span data-stu-id="b53e0-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="b53e0-148">Para configurar la comunicación con una empresa específica o con usuarios de otro dominio, en el cuadro desplegable, elija **activado solo para los dominios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="b53e0-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="b53e0-149">O, si desea permitir la comunicación con cualquier persona del mundo que tenga abiertas las directivas de Skype empresarial, elija **activado excepto para los dominios bloqueados**.</span><span class="sxs-lookup"><span data-stu-id="b53e0-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="b53e0-150">Esta es la configuración que se aplica normalmente.</span><span class="sxs-lookup"><span data-stu-id="b53e0-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="b53e0-151">En **dominios bloqueados o**permitidos **+** , elija y agregue el nombre del dominio que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="b53e0-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="b53e0-152">Asegúrese de que el administrador de la otra organización realiza estos mismos pasos.</span><span class="sxs-lookup"><span data-stu-id="b53e0-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="b53e0-153">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="b53e0-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="b53e0-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b53e0-154">Related topics</span></span>

<span data-ttu-id="b53e0-155">[Iniciar sesión en Microsoft Teams](sign-in-teams.md)
[aprendizaje para usuarios finales para equipos](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="b53e0-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

