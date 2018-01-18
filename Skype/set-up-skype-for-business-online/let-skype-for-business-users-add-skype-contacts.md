---
title: Permitir Skype para usuarios de negocios agregar contactos de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Consulte cómo permitir que las personas que utilizan Skype para el contacto profesional Skype para usuarios empresariales desde fuera de su organización y agregan a su lista de contactos. "
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="daa9f-103">Permitir Skype para usuarios de negocios agregar contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="daa9f-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="daa9f-104">Con Skype para el negocio, los usuarios pueden buscar y mensajes Instantáneos con cualquier persona que utilice Skype, la aplicación gratuita!</span><span class="sxs-lookup"><span data-stu-id="daa9f-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="daa9f-105">Este artículo explica lo que debe hacer para que pueden agregar contactos de Skype.</span><span class="sxs-lookup"><span data-stu-id="daa9f-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="daa9f-106">Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) en Office 365 para ello.</span><span class="sxs-lookup"><span data-stu-id="daa9f-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="daa9f-107">Inicie sesión con su cuenta de administración de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="daa9f-107">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="daa9f-108">En el centro de administración de Office 365, vaya a **Centros de Admin** > **Skype para el negocio**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Elija el Skype para el centro de administración de negocios.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="daa9f-110">En el **Skype para el centro de administración de negocios**, seleccione **organización** > **comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-110">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="daa9f-111">De forma predeterminada, los usuarios pueden comunicarse con todas las otras personas en el mundo que utilizan Skype para empresas (suponiendo que el firewall se ha configurado para ello).</span><span class="sxs-lookup"><span data-stu-id="daa9f-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Elija permitirme personas utilizan Skype para empresas para comunicarse con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="daa9f-113">Si desea que los usuarios de charla con usuarios de Skype, pero no desea charlar con otras personas que utilizan Skype para el negocio, elija **sólo permiten dominios**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-113">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="daa9f-114">Cuando se habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido entre bastidores.</span><span class="sxs-lookup"><span data-stu-id="daa9f-114">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="daa9f-115">Si desea permitir el contacto de todos los otros negocios del mundo mediante Skype para el negocio, excepto en algunos específicos, elija **en excepto dominios bloqueados**y seleccione **+** para agregar esos dominios.</span><span class="sxs-lookup"><span data-stu-id="daa9f-115">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="daa9f-116">Todos los usuarios podrán ponerse en contacto con usted excepto los usuarios de esos dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="daa9f-116">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="daa9f-117">(Algunas empresas pueden elegir esta opción, por ejemplo, si se encuentran en litigios y necesite asegurarse de no hay ningún contacto con el otro negocio).</span><span class="sxs-lookup"><span data-stu-id="daa9f-117">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="daa9f-118">Elija **permiten a los usuarios utilizar Skype para empresas para comunicarse con usuarios de Skype fuera de su organización**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="daa9f-119">Si utiliza Firewall de Windows, Skype para empresas abre los puertos necesarios automáticamente.</span><span class="sxs-lookup"><span data-stu-id="daa9f-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="daa9f-120">Si su organización utiliza otra solución para impedir que los equipos de la red conecta a Internet, asegúrese de que los equipos cliente tienen acceso a todas las [direcciones URL y direcciones IP](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para la conectividad de Skype y Skype Directory Search.</span><span class="sxs-lookup"><span data-stu-id="daa9f-120">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="daa9f-121">Esto puede requerir agregándolos a la salida lista de admitidos en la configuración de infraestructura de firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="daa9f-121">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="daa9f-122">**Esperar hasta 24 horas para probar**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-122">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="daa9f-123">Cada vez que cambie la configuración de comunicaciones externas, puede tardar hasta 24 horas para que los cambios rellenar a través de todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="daa9f-123">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="daa9f-124">Enseñe a los usuarios buscar y agregar contactos de Skype a su lista de Skype para contactos profesionales.</span><span class="sxs-lookup"><span data-stu-id="daa9f-124">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="daa9f-125">Remítales a [Buscar personas en Skype para el negocio](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="daa9f-125">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="daa9f-126">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="daa9f-126">Test and troubleshoot</span></span>

<span data-ttu-id="daa9f-127">Para probar la configuración, es necesario un contacto en Skype que no está detrás de su firewall de la compañía.</span><span class="sxs-lookup"><span data-stu-id="daa9f-127">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="daa9f-128">Puede iniciar sesión en Skype con una cuenta de Gmail, Outlook.com cuenta u otro tipo de cuenta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="daa9f-128">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="daa9f-129">Después de cambiar la configuración de comunicaciones externas, **esperar hasta 24 horas a prueba**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="daa9f-130">Cerrar la sesión de Skype para el negocio y, a continuación, iniciar sesión de nuevo para ver la opción de buscar en el directorio de Skype.</span><span class="sxs-lookup"><span data-stu-id="daa9f-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Cuando esté resaltado el directorio Skype, puede buscar personas que tengan cuentas de Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="daa9f-132">En Skype para el negocio, buscar el contacto en Skype y enviar una solicitud de charla.</span><span class="sxs-lookup"><span data-stu-id="daa9f-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="daa9f-133">Si recibe el mensaje que se no se ha podido enviar debido a la directiva de empresa, debe comprobar la [Configuración del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="daa9f-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="daa9f-134">Póngase en contacto con la otra forma de comprobar si el problema es el servidor de seguridad es ir a una ubicación de wifi no detrás del servidor de seguridad como una cafetería y usar Skype para empresas para enviar una solicitud a su Skype para charlar.</span><span class="sxs-lookup"><span data-stu-id="daa9f-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="daa9f-135">**Si ha enviado su contacto de Skype una solicitud y que nunca ha llegado**, pídale que envíe una solicitud de charla.</span><span class="sxs-lookup"><span data-stu-id="daa9f-135">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="daa9f-136">Si el problema era establecer una conexión entre Skype y Skype para el negocio, a menudo resuelve.</span><span class="sxs-lookup"><span data-stu-id="daa9f-136">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="daa9f-137">Ahora si el mensaje pasa por en la cafetería, pero no cuando está en el trabajo, entonces usted sabe el problema es el servidor de seguridad.</span><span class="sxs-lookup"><span data-stu-id="daa9f-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="daa9f-138">Lo que puede y no puede hacer</span><span class="sxs-lookup"><span data-stu-id="daa9f-138">What you can and can't do</span></span>

- <span data-ttu-id="daa9f-139">**Skype para el negocio en Mac** no tiene la capacidad de buscar y comunicarse con los contactos de Skype.</span><span class="sxs-lookup"><span data-stu-id="daa9f-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="daa9f-140">Mientras que puede buscar y buscar usuarios de Skype, ellos no se pueden buscar y encontrar Skype para usuarios profesionales.</span><span class="sxs-lookup"><span data-stu-id="daa9f-140">While you can search for and find Skype users, they cannot search for and find Skype for Business users.</span></span> <span data-ttu-id="daa9f-141">Tienes que enviarles una solicitud de contacto, y tienen que iniciar sesión en Skype y aceptarla para poder IM con ellos.</span><span class="sxs-lookup"><span data-stu-id="daa9f-141">You have to send them a contact request, and they have to sign in to Skype and accept it, before you can IM with them.</span></span> 
    
- <span data-ttu-id="daa9f-142">No es posible permitir la conectividad de mensajería instantánea con otros proveedores de mensajería instantánea como Google o Facebook.</span><span class="sxs-lookup"><span data-stu-id="daa9f-142">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="daa9f-143">No puede utilizar Skype para empresas para enviar mensajes de texto de teléfono celular.</span><span class="sxs-lookup"><span data-stu-id="daa9f-143">You can't use Skype for Business to send cell phone text messages.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="daa9f-144">¿Qué funciones están disponibles al agregar contactos de Skype?</span><span class="sxs-lookup"><span data-stu-id="daa9f-144">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="daa9f-145">Contactos de Skype que has iniciado sesión con su cuenta de Microsoft (anteriormente Windows Live ID) pueden obtener algunos, pero no todas, las características cuando están hablando con su Skype para usuarios de negocios.</span><span class="sxs-lookup"><span data-stu-id="daa9f-145">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="daa9f-146">**Disponible con contactos de Skype**</span><span class="sxs-lookup"><span data-stu-id="daa9f-146">**Available with Skype contacts**</span></span>|<span data-ttu-id="daa9f-147">**No disponible con contactos de Skype**</span><span class="sxs-lookup"><span data-stu-id="daa9f-147">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="daa9f-148">Conversaciones de vídeo</span><span class="sxs-lookup"><span data-stu-id="daa9f-148">Video conversations</span></span> <br/>  <span data-ttu-id="daa9f-149">Mensajería instantánea persona-a-persona</span><span class="sxs-lookup"><span data-stu-id="daa9f-149">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="daa9f-150">Presence</span><span class="sxs-lookup"><span data-stu-id="daa9f-150">Presence</span></span> <br/> | <span data-ttu-id="daa9f-151">Conversaciones de mensajería instantánea con varios usuarios</span><span class="sxs-lookup"><span data-stu-id="daa9f-151">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="daa9f-152">Conversaciones de audio y vídeo con tres o más personas</span><span class="sxs-lookup"><span data-stu-id="daa9f-152">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="daa9f-153">Escritorio y uso compartido de programas</span><span class="sxs-lookup"><span data-stu-id="daa9f-153">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="daa9f-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="daa9f-154">Related topics</span></span>

[<span data-ttu-id="daa9f-155">Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="daa9f-155">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="daa9f-156">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="daa9f-156">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
