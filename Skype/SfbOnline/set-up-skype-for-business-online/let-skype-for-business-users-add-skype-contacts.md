---
title: Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: d68fc27dfb1c77935ce74e278092f6ed4ae3d7dc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239839"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="ee5ac-103">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="ee5ac-103">Let Skype for Business users add Skype contacts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ee5ac-p101">Con Skype Empresarial, los usuarios pueden buscar a todos los que usen la aplicación gratuita de Skype (la aplicación gratuita) y comunicarse con ellos con mensajería instantánea. En este artículo se explica lo que necesita hacer para que puedan agregar contactos de Skype.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="ee5ac-106">Debe tener permisos [de administrador en](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) Microsoft 365 o Office 365 para ello.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="ee5ac-107">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="ee5ac-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="ee5ac-108">Inicie sesión con su cuenta Microsoft 365 o Office 365 de administrador en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .</span><span class="sxs-lookup"><span data-stu-id="ee5ac-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="ee5ac-109">En el centro de administración, vaya a Centros **de**  >  **administración Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="ee5ac-111">En el **Centro de administración de Skype Empresarial**, seleccione **Organización** > **Comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="ee5ac-112">De forma predeterminada, sus usuarios se pueden comunicar con el resto de personas del mundo que usen Skype Empresarial (siempre que su firewall se haya configurado para permitirlo).</span><span class="sxs-lookup"><span data-stu-id="ee5ac-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="ee5ac-p102">Si desea que sus usuarios chateen con usuarios de Skype, PERO no quiere que chateen con otras personas que usen Skype Empresarial, seleccione **Activado solo para los dominios permitidos**. Cuando habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="ee5ac-p103">Si desea permitir el contacto a todas las empresas del mundo que utilicen Skype Empresarial, salvo a unas concretas, seleccione **Activado excepto para los dominios bloqueados** y seleccione **+** para agregar estos dominios. Todos podrán contactar con usted a excepción de las personas que se encuentren en esos dominios concretos. (Algunas empresas podrían necesitar seleccionar esta opción si, por ejemplo, tienen un litigio con otra empresa y deben cerciorarse de que no hay ningún contacto con otra empresa).</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="ee5ac-119">Seleccione **Permitir que las personas utilicen Skype Empresarial para comunicarse con usuarios de Skype fuera de la organización**.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="ee5ac-120">Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="ee5ac-121">Si su organización usa otra solución para impedir que los equipos de su red se conecten a Internet, asegúrese de que los equipos cliente puedan tener acceso a todas las direcciones IP y direcciones [URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Skype conectividad y Skype directorio.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="ee5ac-122">Esto puede requerir agregar estas direcciones a la lista de permitidos de salida en la configuración de infraestructura de proxy o firewall.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="ee5ac-p105">**AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="ee5ac-p106">Muestre a los usuarios cómo encontrar y agregar contactos de Skype a la lista de contactos de Skype Empresarial. Pídales que lean [Buscar contactos en Skype Empresarial](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="ee5ac-127">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="ee5ac-127">Test and troubleshoot</span></span>

<span data-ttu-id="ee5ac-p107">Para probar su instalación, necesita un contacto en Skype que no esté bloqueado por el firewall de su empresa. Esta persona tendría que haber iniciado sesión en Skype con una cuenta de Gmail, Outlook.com u otro tipo de cuenta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="ee5ac-130">Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="ee5ac-131">Cierre la sesión en Skype Empresarial y después vuelva a iniciarla para que pueda ver la opción de buscar en el directorio de Skype.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="ee5ac-133">En Skype Empresarial, busque su contacto en Skype y envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="ee5ac-134">Si recibe el mensaje que no se pudo enviar debido a la directiva de la empresa, debe comprobar dos vez la configuración [del firewall.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="ee5ac-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="ee5ac-135">Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contacto de Skype.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="ee5ac-p108">**Si ha enviado a su contacto de Skype una solicitud y nunca la recibe**, pídale que le envíe una solicitud para chatear. Si el problema se producía al establecer una conexión entre Skype y Skype Empresarial, esto suele solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="ee5ac-138">Ahora, si el mensaje se envía en la cafetería, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="ee5ac-139">Lo que se puede hacer y lo que no</span><span class="sxs-lookup"><span data-stu-id="ee5ac-139">What you can and can't do</span></span>

- <span data-ttu-id="ee5ac-140">**Skype Empresarialpara Mac** no permite buscar contactos de Skype ni comunicarse con ellos.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="ee5ac-141">Cuando la búsqueda de directorios está habilitada, puede buscar y buscar Skype y Skype Empresarial usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="ee5ac-142">Si por algún motivo no puede encontrarlos buscando en el directorio, puede enviarles una solicitud de contacto y, a continuación, hacer que inicien sesión en Skype y lo acepten, para que pueda enviar por mensajería instantánea con ellos.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="ee5ac-p110">No es posible permitir la conectividad de mensajería instantánea con otros proveedores de mensajería instantánea como Google o Facebook. No puede utilizar Skype Empresarial para enviar mensajes de texto a teléfonos móviles.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="ee5ac-145">No es posible grabar llamadas de audio o vídeo entre un contacto Skype y Skype Empresarial contacto.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="ee5ac-146">¿Cuáles son las características disponibles al agregar contactos de Skype?</span><span class="sxs-lookup"><span data-stu-id="ee5ac-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="ee5ac-147">Skype contactos que han iniciado sesión con su cuenta de Microsoft (anteriormente Windows Live ID) pueden obtener algunas características, pero no todas, cuando están hablando con sus Skype Empresarial usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee5ac-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="ee5ac-148">**Disponible con los contactos de Skype**</span><span class="sxs-lookup"><span data-stu-id="ee5ac-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="ee5ac-149">**No disponible con los contactos de Skype**</span><span class="sxs-lookup"><span data-stu-id="ee5ac-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="ee5ac-150">Conversaciones de vídeo</span><span class="sxs-lookup"><span data-stu-id="ee5ac-150">Video conversations</span></span> <br/>  <span data-ttu-id="ee5ac-151">Mensajería instantánea de persona a persona</span><span class="sxs-lookup"><span data-stu-id="ee5ac-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="ee5ac-152">Presencia</span><span class="sxs-lookup"><span data-stu-id="ee5ac-152">Presence</span></span> <br/> | <span data-ttu-id="ee5ac-153">Conversaciones de MI con varios participantes</span><span class="sxs-lookup"><span data-stu-id="ee5ac-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="ee5ac-154">Conversaciones de audio y vídeo con tres o más personas</span><span class="sxs-lookup"><span data-stu-id="ee5ac-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="ee5ac-155">Uso compartido de escritorio y programas</span><span class="sxs-lookup"><span data-stu-id="ee5ac-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="ee5ac-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ee5ac-156">Related topics</span></span>

[<span data-ttu-id="ee5ac-157">Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ee5ac-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="ee5ac-158">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ee5ac-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
