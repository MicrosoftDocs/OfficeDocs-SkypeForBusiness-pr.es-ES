---
title: Permitir a los usuarios ponerse en contacto con los usuarios de los equipos externos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 'Vea cómo configurar los equipos para permitir a los usuarios comunicarse con usuarios de otra organización, o permita que fuera talk de contactos a ellos. '
ms.openlocfilehash: af4b6a61117e96fdbdf869b2bf7fc54c286b42f0
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2018
ms.locfileid: "19863401"
---
# <a name="allow-users-to-contact-external-teams-users"></a><span data-ttu-id="ceff3-103">Permitir a los usuarios ponerse en contacto con los usuarios de los equipos externos</span><span class="sxs-lookup"><span data-stu-id="ceff3-103">Allow users to contact external Teams users</span></span>
  
<span data-ttu-id="ceff3-104">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="ceff3-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="ceff3-p101">Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="ceff3-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="ceff3-107">Las personas que desee en la organización para usar los equipos ponerse en contacto con las personas de empresas específicas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="ceff3-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="ceff3-108">Cualquier persona que desee en el mundo que usa los equipos que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ceff3-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="ceff3-109">Si usted y se usa la configuración predeterminada, esto funcionará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ceff3-109">If you and they use the default settings, this will work automatically.</span></span> <span data-ttu-id="ceff3-110">De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.</span><span class="sxs-lookup"><span data-stu-id="ceff3-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="ceff3-111">Habilitar comunicaciones entre empresas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="ceff3-111">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="ceff3-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ceff3-112"></span></span>

<span data-ttu-id="ceff3-113">Debe tener [permisos de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en Office 365 en ambas organizaciones para ello.</span><span class="sxs-lookup"><span data-stu-id="ceff3-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="ceff3-114">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png)**utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**.</span><span class="sxs-lookup"><span data-stu-id="ceff3-114">![teams-logo-30x30.png](media/teams-logo-30x30.png)**Using the Microsoft Teams and Skype for Business Admin Center**.</span></span>
1. <span data-ttu-id="ceff3-115">En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="ceff3-115">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

2. <span data-ttu-id="ceff3-116">En la parte superior de la página de **acceso externo** , activar **el acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="ceff3-116">At the top of the **External access** page, turn on **External access**.</span></span> 

3. <span data-ttu-id="ceff3-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ceff3-117">Click **Save**.</span></span> 

4. <span data-ttu-id="ceff3-118">Asegúrese de que el administrador en la otra organización sigue los mismos pasos y entra en el dominio para su negocio como un dominio permitido.</span><span class="sxs-lookup"><span data-stu-id="ceff3-118">Make sure the admin in the other organization follows the same steps and enters the domain for your business as an allowed domain.</span></span>
 
5. <span data-ttu-id="ceff3-p103">**AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="ceff3-p103">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="ceff3-121">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="ceff3-121">Test and troubleshoot</span></span>
<span data-ttu-id="ceff3-122"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ceff3-122"></span></span>

 <span data-ttu-id="ceff3-123">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="ceff3-123">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="ceff3-124">Para probar el programa de instalación, necesita un contacto en los equipos que no está detrás de un firewall de la compañía.</span><span class="sxs-lookup"><span data-stu-id="ceff3-124">To test your setup, you need a contact on Teams who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="ceff3-125">Después de cambiar la configuración del acceso externo, **esperar hasta 24 horas para prueba**.</span><span class="sxs-lookup"><span data-stu-id="ceff3-125">After you change your External Access settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="ceff3-126">Buscar su contacto en los equipos y enviar una solicitud de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="ceff3-126">Search for your contact in Teams, and send a request to chat.</span></span>
    
    <span data-ttu-id="ceff3-127">Si recibe un mensaje que se han podido enviar debido a la directiva de empresa, debe comprobar su [URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="ceff3-127">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="ceff3-128">Pida a su contacto para enviar una solicitud de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="ceff3-128">Ask your contact to send you a request to chat.</span></span> <span data-ttu-id="ceff3-129">Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="ceff3-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="ceff3-130">Otra forma de comprobar si el problema es el servidor de seguridad es vaya a una ubicación de wifi no detrás de un firewall, como un cibercafé y use los equipos para enviar una solicitud a su contacto para conversaciones.</span><span class="sxs-lookup"><span data-stu-id="ceff3-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="ceff3-131">Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="ceff3-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="ceff3-132">Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio</span><span class="sxs-lookup"><span data-stu-id="ceff3-132">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="ceff3-133"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ceff3-133"></span></span>

<span data-ttu-id="ceff3-134">Después de habilitar el acceso externo con otros usuarios de los equipos, los usuarios puedan encontrar los usuarios federados de los equipos mediante la búsqueda de su nombre de inicio de sesión: por ejemplo, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ceff3-134">After you enable External Access with other Teams users, your users can find federated Teams users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="ceff3-135">A continuación, deben agregar a la persona a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="ceff3-135">Then they will need to add the person to their list of contacts.</span></span>
  
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="ceff3-136">Sugerencias para configurar las comunicaciones con empresas federadas</span><span class="sxs-lookup"><span data-stu-id="ceff3-136">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="ceff3-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ceff3-137"></span></span>
    
- <span data-ttu-id="ceff3-138">Cuando dos usuarios de los equipos con Office 365 dominios se comuniquen entre sí en dominios independientes, sólo pueden utilizar características de los equipos (por ejemplo, las conversaciones de vídeo o uso compartido de escritorio) que están activadas en ambas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="ceff3-138">When two Teams users with Office 365 domains are communicating with each other on separate domains, they can only use Teams features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="ceff3-139">Si los usuarios de los equipos de la organización se pone en un juicio o en contexto, se guardarán todas las conversaciones de mensajería instantánea entre ese usuario y otro Skype para los usuarios empresariales o de Skype en **Elementos recuperables** en su buzón.</span><span class="sxs-lookup"><span data-stu-id="ceff3-139">If Teams users in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="ceff3-140">Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.</span><span class="sxs-lookup"><span data-stu-id="ceff3-140">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
  
<span data-ttu-id="ceff3-141"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ceff3-141"></span></span>
 
