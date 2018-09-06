---
title: Comunicarse con los usuarios de los equipos de otra organización.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Vea cómo configurar los equipos para permitir a los usuarios comunicarse con usuarios de otra organización.
ms.openlocfilehash: 3eaffac3571abc70d4964ea4a8955f187d1e988f
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844640"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="97069-103">Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="97069-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="97069-104">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="97069-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="97069-105">Tienen los usuarios en diferentes dominios en su negocio.</span><span class="sxs-lookup"><span data-stu-id="97069-105">You have users in different domains in your business.</span></span> <span data-ttu-id="97069-106">Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="97069-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="97069-107">Las personas que desee en la organización para usar los equipos ponerse en contacto con las personas de empresas específicas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="97069-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="97069-108">Cualquier persona que desee en el mundo que usa los equipos que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="97069-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="97069-109">Si usted y otro usuario tanto habilitación el acceso externo y permitir que los demás dominios, esto funcionará.</span><span class="sxs-lookup"><span data-stu-id="97069-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="97069-110">Si no funciona, el otro usuario, debe asegurarse de que su o su configuración no esté bloqueando su dominio.</span><span class="sxs-lookup"><span data-stu-id="97069-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="97069-111">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="97069-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="97069-112">Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="97069-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="97069-113">Paso 1: asegúrese de configurar los puertos y direcciones URL que son necesarios.</span><span class="sxs-lookup"><span data-stu-id="97069-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="97069-114">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="97069-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="97069-115">Paso 2: habilitar la organización para comunicarse con otra organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="97069-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="97069-116">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="97069-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="97069-117">En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="97069-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="97069-118">En la parte superior de la página de **acceso externo** , haga clic en **acceso externo** a **en**.</span><span class="sxs-lookup"><span data-stu-id="97069-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="97069-119">Agregar dominio de la otra organización a la lista permitida, haga clic en **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="97069-119">Add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="97069-120">En el panel **Agregar un dominio** , coloque en el nombre de dominio, haga clic en **permitidos** y, a continuación, en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="97069-120">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="97069-121">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97069-121">Click **Save**.</span></span> 

   5. <span data-ttu-id="97069-122">A continuación, asegúrese de que el Administrador de la organización de los equipos otros estos mismos pasos.</span><span class="sxs-lookup"><span data-stu-id="97069-122">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="97069-123">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="97069-123">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

### <a name="step-3---test-it"></a><span data-ttu-id="97069-124">Paso 3: ponerlo a prueba</span><span class="sxs-lookup"><span data-stu-id="97069-124">Step 3 - Test it</span></span>
<span data-ttu-id="97069-125">Para probar el programa de instalación, necesita un usuario de los equipos que no está detrás de un firewall.</span><span class="sxs-lookup"><span data-stu-id="97069-125">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="97069-126">Después de que usted y el Administrador de la organización han cambiado la configuración del **acceso externo** , debe proceder.</span><span class="sxs-lookup"><span data-stu-id="97069-126">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="97069-127">En la aplicación de los equipos, buscar por dirección de correo electrónico a esa persona y enviar una solicitud de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="97069-127">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="97069-128">Pida a su contacto de los equipos para enviar una solicitud de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="97069-128">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="97069-129">Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="97069-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="97069-130">Otra forma de comprobar si el problema es el servidor de seguridad es vaya a una ubicación de wifi no detrás de un firewall, como un cibercafé y use los equipos para enviar una solicitud a su contacto para conversaciones.</span><span class="sxs-lookup"><span data-stu-id="97069-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="97069-131">Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="97069-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="97069-132">Comunicarse con usuarios en un Skype para la organización empresarial en línea</span><span class="sxs-lookup"><span data-stu-id="97069-132">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="97069-133">Si va a establecer hasta permiten a los usuarios de los equipos buscan y ponerse en contacto con los usuarios que se encuentran en un Skype para la organización empresarial, será el Administrador de esa organización que se deben seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="97069-133">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization, you will the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="97069-134">![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Uso de Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="97069-134">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="97069-135">Tener la administración en que la organización siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="97069-135">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="97069-136">En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="97069-136">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
  
2. <span data-ttu-id="97069-137">En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="97069-137">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="97069-138">Para establecer la comunicación con un negocio específicos o con los usuarios en otro dominio, en el cuadro de lista desplegable, elija **sólo para permitido dominios**.</span><span class="sxs-lookup"><span data-stu-id="97069-138">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="97069-p107">O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97069-p107">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
4. <span data-ttu-id="97069-141">En **dominios permitidos o bloqueados**, elija **+** y agregue el nombre del dominio que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="97069-141">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="97069-142">Asegúrese de que el administrador en la otra organización estos mismos pasos.</span><span class="sxs-lookup"><span data-stu-id="97069-142">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="97069-143">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="97069-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="97069-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="97069-144">Related topics</span></span>

<span data-ttu-id="97069-145">[Inicie sesión en los equipos](sign-in-teams.md)
[recursos de aprendizaje para los equipos de usuario final](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="97069-145">[Sign in teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

