---
title: Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: a1f399f7b127596aaf28c7e22b2c65525c72a8e4
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164829"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="767a5-103">Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="767a5-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="767a5-104">La Federación de Skype empresarial no está disponible para las organizaciones de Microsoft 365 u Office 365 operadas por 21Vianet ni por Microsoft 365 u Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="767a5-104">Skype for Business federation isn't available to Microsoft 365 or Office 365 operated by 21Vianet and Microsoft 365 or Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="767a5-105">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="767a5-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="767a5-p101">Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="767a5-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="767a5-108">Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="767a5-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="767a5-109">Desea que cualquier persona del mundo que use Skype empresarial pueda encontrarse y ponerse en contacto con usted, usando su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="767a5-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="767a5-110">Esto funcionará automáticamente si usted y el otro usuario usan la configuración predeterminada de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="767a5-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="767a5-111">De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.</span><span class="sxs-lookup"><span data-stu-id="767a5-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="767a5-112">Habilitar comunicaciones entre empresas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="767a5-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="767a5-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="767a5-113"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="767a5-114">Para ello, debe tener [permisos de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en Microsoft 365 u Office 365 en ambas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="767a5-114">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="767a5-115">![Un icono que muestra el logotipo](../images/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Teams**</span><span class="sxs-lookup"><span data-stu-id="767a5-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="767a5-116">Inicie sesión con su cuenta de administrador de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="767a5-116">Sign in with your Microsoft 365 or Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="767a5-117">En el centro de administración, vaya a**equipos**del centro de **Administración** > .</span><span class="sxs-lookup"><span data-stu-id="767a5-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Elija el administrador de Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="767a5-119">En el **centro de equipos**, elija **portal** 
 ![heredado de **Skype** > elija el portal heredado de SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="767a5-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="767a5-120">En el **centro de administración de Skype empresarial** , elija**comunicaciones externas**de la **organización** > .</span><span class="sxs-lookup"><span data-stu-id="767a5-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="767a5-121">Para configurar la comunicación con empresas específicas o con usuarios de otros dominios, seleccione en el cuadro desplegable **Activado solo para dominios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="767a5-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="767a5-p103">O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="767a5-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
6. <span data-ttu-id="767a5-124">En **dominios bloqueados o permitidos**, elija **+** y agregue el nombre del dominio que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="767a5-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="767a5-125">Asegúrese de que el administrador de la otra organización Realice estos mismos pasos en el **centro de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="767a5-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="767a5-126">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="767a5-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="767a5-127">Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.</span><span class="sxs-lookup"><span data-stu-id="767a5-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="767a5-128">Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="767a5-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="767a5-129">Esto puede requerir agregar FQDN a la lista de permitidos salientes en la configuración de su infraestructura de proxy o firewall: \* \*\* \*. API.Skype.com\*\*, **. users.Storage.Live.com**y **Graph.Skype.com**.</span><span class="sxs-lookup"><span data-stu-id="767a5-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="767a5-130">Para obtener instrucciones sobre cómo abrir estos puertos en su firewall, consulte la documentación que viene con él.</span><span class="sxs-lookup"><span data-stu-id="767a5-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="767a5-131">Para obtener una lista de todos los puertos que necesita abrir, consulte [Office 365 URL e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="767a5-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="767a5-132">Asegúrese de que el administrador de la organización también haya seguido estos pasos.</span><span class="sxs-lookup"><span data-stu-id="767a5-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="767a5-p106">**AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="767a5-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="767a5-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="767a5-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="767a5-136">Para obtener más información, consulte [permitir que los usuarios de Skype empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="767a5-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="767a5-137">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="767a5-137">Test and troubleshoot</span></span>
<span data-ttu-id="767a5-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="767a5-138"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="767a5-139">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="767a5-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="767a5-140">Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.</span><span class="sxs-lookup"><span data-stu-id="767a5-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="767a5-141">Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.</span><span class="sxs-lookup"><span data-stu-id="767a5-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="767a5-142">En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="767a5-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="767a5-143">Si recibe un mensaje que indica que no se pudo enviar debido a la Directiva de la empresa, debe comprobar las [direcciones URL y los intervalos de direcciones IP de Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="767a5-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="767a5-p108">Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="767a5-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="767a5-p109">Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contrato. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="767a5-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="767a5-148">Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio</span><span class="sxs-lookup"><span data-stu-id="767a5-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="767a5-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="767a5-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="767a5-150">Después de habilitar la comunicación externa con otros usuarios de Skype empresarial, los usuarios pueden buscar usuarios federados de Skype empresarial buscando su nombre de inicio de sesión: por ejemplo, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="767a5-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="767a5-151">Luego deben agregar a la persona a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="767a5-151">Then they will need to add the person to their list of contacts.</span></span>
  
![Para buscar un usuario en una empresa federada, debe buscar su dirección de correo electrónico (suele ser también su nombre de inicio de sesión).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="767a5-153">Sugerencias para configurar las comunicaciones con empresas federadas</span><span class="sxs-lookup"><span data-stu-id="767a5-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="767a5-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="767a5-154"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="767a5-155">Para configurar la Federación entre Skype empresarial 2015 y Skype empresarial online, consulte este artículo: [configurar la Federación con Skype empresarial online](https://technet.microsoft.com/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="767a5-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="767a5-156">Para configurar la Federación entre Lync y Skype empresarial online, consulte este artículo: [configuración de la compatibilidad de Federación para un cliente de Lync Online](https://technet.microsoft.com/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="767a5-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="767a5-157">Cuando dos usuarios de Skype empresarial en Microsoft 365 u Office 365 se comunican entre sí en dominios independientes, solo pueden usar características de Skype empresarial (por ejemplo, conversaciones de vídeo o uso compartido del escritorio) que están activadas en las dos organizaciones.</span><span class="sxs-lookup"><span data-stu-id="767a5-157">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="767a5-158">Si un usuario de Skype empresarial de su organización se coloca en una retención local o por juicio, cualquier conversación de mensajería instantánea entre ese usuario y otros usuarios de Skype empresarial o Skype se guardará en **los elementos recuperables** de su buzón.</span><span class="sxs-lookup"><span data-stu-id="767a5-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="767a5-159">Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.</span><span class="sxs-lookup"><span data-stu-id="767a5-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="767a5-160">Desactivar la comunicación externa para personas específicas</span><span class="sxs-lookup"><span data-stu-id="767a5-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="767a5-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="767a5-161"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="767a5-162">Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.</span><span class="sxs-lookup"><span data-stu-id="767a5-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="767a5-163">Inicie sesión con su cuenta de administrador de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="767a5-163">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>
    
2. <span data-ttu-id="767a5-164">En el centro de administración, vaya **a** > usuarios**activos**.</span><span class="sxs-lookup"><span data-stu-id="767a5-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="767a5-165">En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="767a5-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="767a5-167">En el **centro de administración de Skype empresarial**, elija **comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="767a5-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="767a5-168">En la página **Opciones** , se seleccionarán todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="767a5-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="767a5-169">Borre las comunicaciones que desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="767a5-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="767a5-170">En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.</span><span class="sxs-lookup"><span data-stu-id="767a5-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="767a5-172">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="767a5-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="767a5-173">Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto.</span><span class="sxs-lookup"><span data-stu-id="767a5-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="767a5-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="767a5-174">Related topics</span></span>
<span data-ttu-id="767a5-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="767a5-175"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="767a5-176">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="767a5-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="767a5-177">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="767a5-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
