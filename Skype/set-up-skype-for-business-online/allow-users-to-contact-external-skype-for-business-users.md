---
title: Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: f1dd146a507a1cf6a70b4e30c7da0f2c18d722e7
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="47410-103">Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="47410-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="47410-104">Skype para federación empresarial no está disponible para Office 365 operado por 21Vianet y organizaciones de Alemania de Office 365.</span><span class="sxs-lookup"><span data-stu-id="47410-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="47410-105">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="47410-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="47410-p101">Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="47410-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="47410-108">Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="47410-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="47410-109">-Desea que cualquier persona del mundo que utiliza Skype para el negocio para que pueda buscar y ponerse en contacto con usted, con su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="47410-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="47410-110">Esto funcionará automáticamente si usted y el otro usuario usan la configuración predeterminada de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="47410-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="47410-111">De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.</span><span class="sxs-lookup"><span data-stu-id="47410-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="47410-112">Habilitar comunicaciones entre empresas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="47410-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="47410-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="47410-113"></span></span>

<span data-ttu-id="47410-114">Debe tener [Acerca de los roles de administrador de Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en Office 365 para realizar esta acción.</span><span class="sxs-lookup"><span data-stu-id="47410-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="47410-115">Inicie sesión con su cuenta de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="47410-115">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="47410-116">En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="47410-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="47410-118">En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="47410-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="47410-119">Para establecer la comunicación con una empresa específica o con usuarios de otro dominio, en el cuadro de lista desplegable, elija **sólo permiten dominios**.</span><span class="sxs-lookup"><span data-stu-id="47410-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="47410-p103">O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47410-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
5. <span data-ttu-id="47410-122">Bajo **dominios permitidos o bloqueados**, seleccione **+** y agregue el nombre del dominio que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="47410-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="47410-123">Asegúrese de que el administrador en la otra organización hace estos mismos pasos en su **Skype para el centro de administración de negocios**.</span><span class="sxs-lookup"><span data-stu-id="47410-123">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="47410-124">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="47410-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="47410-125">Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.</span><span class="sxs-lookup"><span data-stu-id="47410-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="47410-126">Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="47410-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="47410-127">Esto puede requerir agregar el FQDN para el saliente permiten lista en el firewall o el proxy la configuración de la infraestructura: ** \*. api.skype.com**, \* **. users.storage.live.com**y **graph.skype.com**. Para obtener instrucciones acerca de cómo abrir estos puertos en el firewall, consulte la documentación que lo acompaña.</span><span class="sxs-lookup"><span data-stu-id="47410-127">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="47410-128">Para obtener una lista de todos los puertos que debe abrir, consulte [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="47410-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
8. <span data-ttu-id="47410-p106">**AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="47410-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="47410-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="47410-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="47410-132">Para obtener más información, vea [Permitir Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="47410-132">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="47410-133">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="47410-133">Test and troubleshoot</span></span>
<span data-ttu-id="47410-134"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="47410-134"></span></span>

 <span data-ttu-id="47410-135">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="47410-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="47410-136">Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.</span><span class="sxs-lookup"><span data-stu-id="47410-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="47410-137">Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.</span><span class="sxs-lookup"><span data-stu-id="47410-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="47410-138">En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="47410-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="47410-139">Si aparece un mensaje que se no se ha podido enviar debido a la directiva de empresa, debe comprobar las [direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="47410-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="47410-p108">Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="47410-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="47410-p109">Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contrato. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="47410-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="47410-144">Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio</span><span class="sxs-lookup"><span data-stu-id="47410-144">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="47410-145"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="47410-145"></span></span>

<span data-ttu-id="47410-146">Después de habilitar las comunicaciones externas con otro Skype para usuarios profesionales, los usuarios puedan encontrar federado Skype para usuarios de negocios buscando su nombre de inicio de sesión: por ejemplo, Rob@contoso.com. A continuación, necesitará agregar a esa persona a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="47410-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![Para buscar un usuario en una empresa federada, debe buscar su dirección de correo electrónico (normalmente es también su nombre de inicio de sesión).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="47410-148">Sugerencias para configurar las comunicaciones con empresas federadas</span><span class="sxs-lookup"><span data-stu-id="47410-148">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="47410-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="47410-149"></span></span>

- <span data-ttu-id="47410-150">Para configurar la federación entre Skype Empresarial 2015 y Skype Empresarial Online, consulte este artículo de Technet: [Configurar la federación con Skype Empresarial Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="47410-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="47410-151">Para configurar la federación entre Lync y Skype Empresarial Online, consulte este artículo de Technet: [Configuración de la compatibilidad de federación para un cliente de Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="47410-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="47410-152">Cuando dos usuarios de Skype Empresarial en Office 365 se comunican entre sí en dominios distintos, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o compartir escritorio) que estén activadas en las dos organizaciones.</span><span class="sxs-lookup"><span data-stu-id="47410-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="47410-153">Si se coloca un Skype para usuarios de empresa de la organización en un puesto o retención para litigios, se guardarán las conversaciones de mensajería instantánea entre ese usuario y otro Skype para usuarios de negocios o de Skype en los **Elementos recuperables** en su buzón.</span><span class="sxs-lookup"><span data-stu-id="47410-153">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="47410-154">Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.</span><span class="sxs-lookup"><span data-stu-id="47410-154">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="47410-155">Desactivar la comunicación externa para personas específicas</span><span class="sxs-lookup"><span data-stu-id="47410-155">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="47410-156"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="47410-156"></span></span>

<span data-ttu-id="47410-157">Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.</span><span class="sxs-lookup"><span data-stu-id="47410-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="47410-158">Inicie sesión con su cuenta de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="47410-158">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="47410-159">En el centro de administración de Office 365, vaya a **usuarios** > **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="47410-159">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="47410-160">En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="47410-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="47410-162">En el **Skype para el centro de administración de negocios**, elija **comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="47410-162">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="47410-163">En la página de **Opciones** , se seleccionarán todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="47410-163">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="47410-164">Desactive las comunicaciones que va a deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="47410-164">Clear the communications you want to disable.</span></span> <span data-ttu-id="47410-165">En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.</span><span class="sxs-lookup"><span data-stu-id="47410-165">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="47410-167">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47410-167">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="47410-168">Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto.</span><span class="sxs-lookup"><span data-stu-id="47410-168">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="47410-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47410-169">Related topics</span></span>
<span data-ttu-id="47410-170"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="47410-170"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="47410-171">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="47410-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="47410-172">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="47410-172">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  

