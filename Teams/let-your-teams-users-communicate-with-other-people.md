---
title: Comunicarse con los usuarios de los equipos de otra organización.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Vea cómo configurar los equipos para permitir a los usuarios comunicarse con usuarios de otra organización.
ms.openlocfilehash: 6fb71e4c9e1461ca920d480336288b06e3111eb2
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240843"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="7fe76-103">Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="7fe76-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="7fe76-104">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="7fe76-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="7fe76-105">Tienen los usuarios en diferentes dominios en su negocio.</span><span class="sxs-lookup"><span data-stu-id="7fe76-105">You have users in different domains in your business.</span></span> <span data-ttu-id="7fe76-106">Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="7fe76-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="7fe76-107">Las personas que desee en la organización para usar los equipos ponerse en contacto con las personas de empresas específicas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="7fe76-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="7fe76-108">Cualquier persona que desee en el mundo que usa los equipos que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7fe76-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="7fe76-109">Si usted y otro usuario tanto habilitación el acceso externo y permitir que los demás dominios, esto funcionará.</span><span class="sxs-lookup"><span data-stu-id="7fe76-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="7fe76-110">Si no funciona, el otro usuario, debe asegurarse de que su o su configuración no esté bloqueando su dominio.</span><span class="sxs-lookup"><span data-stu-id="7fe76-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="7fe76-111">Esto le permitirá a los usuarios buscar, llamar y enviar mensajes instantáneos, así como configurar reuniones con usted.</span><span class="sxs-lookup"><span data-stu-id="7fe76-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="7fe76-112">Si desea que los usuarios externos tengan acceso a los equipos y los canales, acceso de invitado podría ser una mejor manera para ir.</span><span class="sxs-lookup"><span data-stu-id="7fe76-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="7fe76-113">Siga los pasos descritos en este artículo y asegúrese de que al [activar el acceso de invitado](set-up-guests.md) para que los usuarios puedan comunicarse.</span><span class="sxs-lookup"><span data-stu-id="7fe76-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="7fe76-114">Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="7fe76-114">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="7fe76-115">Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7fe76-115">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="7fe76-116">Paso 1: asegúrese de configurar los puertos y direcciones URL que son necesarios.</span><span class="sxs-lookup"><span data-stu-id="7fe76-116">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="7fe76-117">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="7fe76-117">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="7fe76-118">Paso 2: habilitar la organización para comunicarse con otra organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="7fe76-118">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="7fe76-119">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="7fe76-119">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="7fe76-120">En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-120">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="7fe76-121">En la parte superior de la página de **acceso externo** , haga clic en **acceso externo** a **en**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-121">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="7fe76-122">Si desea permitir que todas las organizaciones de los equipos para comunicarse con los usuarios de su organización, vaya al paso 5.</span><span class="sxs-lookup"><span data-stu-id="7fe76-122">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="7fe76-123">Si desea limitar que las organizaciones pueden comunicarse con los usuarios de la organización puede permitir que todos los pero algunos dominios o permitir sólo las organizaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="7fe76-123">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="7fe76-124">Para permitir que todos los pero algunos dominios, agregue los dominios que desee bloquear, haga clic en **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-124">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="7fe76-125">En el panel **Agregar un dominio** , poner en el nombre de dominio, haga clic en **bloqueado** y, a continuación, en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-125">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="7fe76-126">Para limitar las comunicaciones a organizatioins específica, añada esos dominios a la lista con un estado de **Alowed**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-126">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="7fe76-127">Una vez haya agregado cualquier dominio a la lista Permitir, communications a otras organizaciones se limitará a sólo esas organizaciones cuyos dominios se encuentran en la lista Permitir.</span><span class="sxs-lookup"><span data-stu-id="7fe76-127">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="7fe76-128">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-128">Click **Save**.</span></span> 

   6. <span data-ttu-id="7fe76-129">A continuación, asegúrese de que el Administrador de la organización de los equipos otros estos mismos pasos.</span><span class="sxs-lookup"><span data-stu-id="7fe76-129">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="7fe76-130">Por ejemplo, en su lista de **permitidos dominios** , su administrador debe introducir el dominio para su negocio si limita a que las organizaciones pueden comunicarse con sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="7fe76-130">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="7fe76-131">Paso 3: ponerlo a prueba</span><span class="sxs-lookup"><span data-stu-id="7fe76-131">Step 3 - Test it</span></span>
<span data-ttu-id="7fe76-132">Para probar el programa de instalación, necesita un usuario de los equipos que no está detrás de un firewall.</span><span class="sxs-lookup"><span data-stu-id="7fe76-132">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="7fe76-133">Después de que usted y el Administrador de la organización han cambiado la configuración del **acceso externo** , debe proceder.</span><span class="sxs-lookup"><span data-stu-id="7fe76-133">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="7fe76-134">En la aplicación de los equipos, buscar por dirección de correo electrónico a esa persona y enviar una solicitud de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="7fe76-134">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="7fe76-135">Pida a su contacto de los equipos para enviar una solicitud de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="7fe76-135">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="7fe76-136">Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="7fe76-136">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="7fe76-137">Otra forma de comprobar si el problema es el servidor de seguridad es vaya a una ubicación de wifi no detrás de un firewall, como un cibercafé y use los equipos para enviar una solicitud a su contacto para conversaciones.</span><span class="sxs-lookup"><span data-stu-id="7fe76-137">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="7fe76-138">Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="7fe76-138">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="7fe76-139">Comunicarse con usuarios en un Skype para la organización empresarial en línea</span><span class="sxs-lookup"><span data-stu-id="7fe76-139">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="7fe76-140">Si se establecer para permitir que la búsqueda de los usuarios de los equipos y contacto a los usuarios que se encuentran en un Skype para la organización de empresa que limita quién puede ponerse en contacto con sus usuarios, le pedirá la administración de esa organización que se deben seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7fe76-140">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="7fe76-141">![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Uso de Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="7fe76-141">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="7fe76-142">Tener la administración en que la organización siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7fe76-142">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="7fe76-143">En el centro de administración de Office 365, vaya a **Centros de administrador de** > **equipos & Skype** > **portal heredado**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-143">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="7fe76-144">En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-144">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="7fe76-145">Para establecer la comunicación con un negocio específicos o con los usuarios en otro dominio, en el cuadro de lista desplegable, elija **sólo para permitido dominios**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-145">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="7fe76-146">O bien, si desea habilitar la comunicación con todos los demás en el mundo que tiene abierto Skype para las directivas de negocio, elija **en excepto dominios bloqueados**.</span><span class="sxs-lookup"><span data-stu-id="7fe76-146">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="7fe76-147">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7fe76-147">This is the default setting.</span></span>
    
4. <span data-ttu-id="7fe76-148">En **dominios permitidos o bloqueados**, elija **+** y agregue el nombre del dominio que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="7fe76-148">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="7fe76-149">Asegúrese de que el administrador en la otra organización estos mismos pasos.</span><span class="sxs-lookup"><span data-stu-id="7fe76-149">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="7fe76-150">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="7fe76-150">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="7fe76-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7fe76-151">Related topics</span></span>

<span data-ttu-id="7fe76-152">[Inicie sesión en Microsoft Teams](sign-in-teams.md)
[recursos de aprendizaje para los equipos de usuario final](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="7fe76-152">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

