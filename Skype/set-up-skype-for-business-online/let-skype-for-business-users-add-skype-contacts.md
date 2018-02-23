---
title: Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Consulte cómo permitir que las personas que usan Skype Empresarial se pongan en contacto con otros usuarios externos a la empresa y los agreguen a la lista de contactos. "
ms.openlocfilehash: 8f6ca948434d9b5a63788cbb5bc54ad6297843e2
ms.sourcegitcommit: 46ca433590a4c3aefbe2fb777542bb0b332563bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="6a900-103">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="6a900-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="6a900-104">Con Skype Empresarial, los usuarios pueden buscar a todos los que usen la aplicación gratuita de Skype y comunicarse con ellos con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="6a900-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="6a900-105">En este artículo se explica lo que necesita hacer para que puedan agregar contactos de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a900-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="6a900-106">Para ello, debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a900-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="6a900-107">Inicie sesión con su cuenta de administrador de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="6a900-107">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="6a900-108">En el Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6a900-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Seleccionar el Centro de administración de Skype Empresarial.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="6a900-110">En el **Centro de administración de Skype Empresarial**, elija **Organización** > **Comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="6a900-110">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="6a900-111">De forma predeterminada, sus usuarios se pueden comunicar con el resto de personas del mundo que usen Skype Empresarial (siempre que su firewall se haya configurado para permitirlo).</span><span class="sxs-lookup"><span data-stu-id="6a900-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Seleccione la opción que permite la comunicación mediante Skype Empresarial con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="6a900-113">Si desea que sus usuarios chateen con usuarios de Skype, PERO no quiere que chateen con otras personas que usen Skype Empresarial, seleccione **Activado solo para los dominios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="6a900-113">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="6a900-114">Cuando habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6a900-114">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="6a900-115">Si desea permitir el contacto a todas las empresas del mundo que utilicen Skype Empresarial, salvo a unas concretas, seleccione **Activado excepto para los dominios bloqueados** y seleccione **+** para agregar estos dominios.</span><span class="sxs-lookup"><span data-stu-id="6a900-115">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="6a900-116">Todos podrán contactar con usted a excepción de las personas que se encuentren en esos dominios concretos.</span><span class="sxs-lookup"><span data-stu-id="6a900-116">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="6a900-117">(Algunas empresas podrían necesitar seleccionar esta opción si, por ejemplo, tienen un litigio con otra empresa y deben cerciorarse de que no hay ningún contacto con otra empresa).</span><span class="sxs-lookup"><span data-stu-id="6a900-117">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="6a900-118">Seleccione **Permitir que las personas utilicen Skype Empresarial para comunicarse con usuarios de Skype fuera de la organización**.</span><span class="sxs-lookup"><span data-stu-id="6a900-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="6a900-119">Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.</span><span class="sxs-lookup"><span data-stu-id="6a900-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="6a900-120">Si su organización usa otra solución para restringir la conexión a Internet de los equipos en la red, asegúrese de que los equipos cliente puedan acceder a todas las [direcciones IP y direcciones URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para garantizar la conectividad de Skype y la búsqueda en el directorio de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a900-120">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="6a900-121">Para esto es posible que tenga que agregarlas a la lista de permitidos de salida en la configuración de la infraestructura de proxy o firewall.</span><span class="sxs-lookup"><span data-stu-id="6a900-121">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="6a900-122">**DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.</span><span class="sxs-lookup"><span data-stu-id="6a900-122">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="6a900-123">Cada vez que se modifica la configuración de las comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="6a900-123">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="6a900-124">Muestre a sus usuarios cómo pueden buscar y agregar contactos de Skype a su lista de contactos de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a900-124">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="6a900-125">Indíqueles que consulten [Buscar contactos en Skype Empresarial](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="6a900-125">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="6a900-126">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="6a900-126">Test and troubleshoot</span></span>

<span data-ttu-id="6a900-127">Para probar su instalación, necesita un contacto en Skype que no esté bloqueado por el firewall de su empresa.</span><span class="sxs-lookup"><span data-stu-id="6a900-127">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="6a900-128">Esta persona tendría que haber iniciado sesión en Skype con una cuenta de Gmail, Outlook.com u otro tipo de cuenta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6a900-128">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="6a900-129">Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.</span><span class="sxs-lookup"><span data-stu-id="6a900-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="6a900-130">Cierre la sesión en Skype Empresarial y después vuelva a iniciarla para que pueda ver la opción de buscar en el directorio de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a900-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Cuando se resalte Directorio de Skype, podrá buscar contactos que tengan cuentas de Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="6a900-132">En Skype Empresarial, busque su contacto en Skype y envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="6a900-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="6a900-133">Si se le indica que no se pudo enviar el mensaje debido a la directiva de la empresa, tendrá que volver a comprobar su [configuración del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="6a900-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="6a900-134">Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión Wi-Fi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contacto de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a900-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="6a900-135">**Si ha enviado a su contacto de Skype una solicitud y nunca la ha recibido**, pídale que le envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="6a900-135">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="6a900-136">Si el problema se producía al establecer una conexión entre Skype y Skype Empresarial, esto suele solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="6a900-136">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="6a900-137">Ahora, si el mensaje se envía en la cafetería, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="6a900-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="6a900-138">Qué puede y qué no puede hacer</span><span class="sxs-lookup"><span data-stu-id="6a900-138">What you can and can't do</span></span>

- <span data-ttu-id="6a900-139">**Skype Empresarial en Mac** no permite buscar contactos de Skype ni comunicarse con ellos.</span><span class="sxs-lookup"><span data-stu-id="6a900-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="6a900-140">Cuando la búsqueda en directorios está habilitada, puede buscar y encontrar usuarios de Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a900-140">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="6a900-141">Si por algún motivo no puede encontrarles con las búsquedas en el directorio, podrá enviarles una solicitud de contacto y pedirles que inicien sesión en Skype para aceptarla. De este modo podrán enviarse mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="6a900-141">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="6a900-142">La conectividad de mensajería instantánea no se puede realizar con otros proveedores de mensajería instantánea, como Google o Facebook.</span><span class="sxs-lookup"><span data-stu-id="6a900-142">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="6a900-143">No se puede usar Skype Empresarial para enviar mensajes de texto en teléfonos móviles.</span><span class="sxs-lookup"><span data-stu-id="6a900-143">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="6a900-144">No se pueden grabar llamadas de audio y videollamadas entre un contacto de Skype y un contacto de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a900-144">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="6a900-145">¿Qué características están disponibles cuando se agregan contactos de Skype?</span><span class="sxs-lookup"><span data-stu-id="6a900-145">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="6a900-146">Los contactos de Skype que inicien sesión con su cuenta de Microsoft (anteriormente de Windows Live ID) podrán disfrutar de algunas de las características (aunque no todas) cuando hablen con sus usuarios de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a900-146">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="6a900-147">**Disponible con contactos de Skype**</span><span class="sxs-lookup"><span data-stu-id="6a900-147">**Available with Skype contacts**</span></span>|<span data-ttu-id="6a900-148">**No disponible con contactos de Skype**</span><span class="sxs-lookup"><span data-stu-id="6a900-148">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="6a900-149">Conversaciones de vídeo</span><span class="sxs-lookup"><span data-stu-id="6a900-149">Video conversations</span></span> <br/>  <span data-ttu-id="6a900-150">Mensajes instantáneos entre dos personas</span><span class="sxs-lookup"><span data-stu-id="6a900-150">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="6a900-151">Presencia</span><span class="sxs-lookup"><span data-stu-id="6a900-151">Presence</span></span> <br/> | <span data-ttu-id="6a900-152">Conversaciones de mensajería instantánea con varios participantes</span><span class="sxs-lookup"><span data-stu-id="6a900-152">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="6a900-153">Conversaciones con audio y vídeo con tres o más contactos</span><span class="sxs-lookup"><span data-stu-id="6a900-153">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="6a900-154">Uso compartido de escritorio y programas</span><span class="sxs-lookup"><span data-stu-id="6a900-154">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="6a900-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6a900-155">Related topics</span></span>

[<span data-ttu-id="6a900-156">Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="6a900-156">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="6a900-157">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6a900-157">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
