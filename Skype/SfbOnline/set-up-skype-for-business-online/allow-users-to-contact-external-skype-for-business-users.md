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
description: 'Vea cómo configurar Skype Empresarial para permitir que los usuarios hablen con los usuarios de otra organización o que los contactos externos hablen con ellos. '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625056"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="e246f-103">Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e246f-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="e246f-104">Siga los pasos de este artículo cuando:</span><span class="sxs-lookup"><span data-stu-id="e246f-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="e246f-p101">Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.</span><span class="sxs-lookup"><span data-stu-id="e246f-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="e246f-107">Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="e246f-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="e246f-p102">Desea que cualquier otra persona del mundo que use Skype Empresarial pueda buscarlo y ponerse en contacto con usted mediante su dirección de correo electrónico. Si usted y ellos usan la configuración predeterminada de Skype Empresarial, esto funcionará automáticamente. Si no es así, deben asegurarse de que la configuración no está bloqueando el dominio.</span><span class="sxs-lookup"><span data-stu-id="e246f-p102">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address. If you and they use the default Skype for Business settings, this will work automatically. If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="e246f-111">Habilitar comunicaciones entre empresas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="e246f-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="e246f-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e246f-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="e246f-113">Debe tener permisos [de administrador en](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Microsoft 365 u Office 365 en ambas organizaciones para realizar esta comunicación.</span><span class="sxs-lookup"><span data-stu-id="e246f-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="e246f-114">![Icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Con el Centro de administración de Teams**</span><span class="sxs-lookup"><span data-stu-id="e246f-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="e246f-115">Inicie sesión con su cuenta de administrador de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="e246f-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="e246f-116">En el centro de administración, vaya a **Equipos de centros de**  >  **administración.**</span><span class="sxs-lookup"><span data-stu-id="e246f-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Elija el administrador de Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="e246f-118">En el **Centro de equipos,** elija **Skype** > **(portal** 
  ![ heredado) Elija el portal heredado de SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="e246f-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="e246f-119">En el **Centro de administración de Skype Empresarial**, seleccione **Organización** > **Comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="e246f-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="e246f-120">Para configurar la comunicación con empresas específicas o con usuarios de otros dominios, seleccione en el cuadro desplegable **Activado solo para dominios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="e246f-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="e246f-p103">O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e246f-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>

6. <span data-ttu-id="e246f-123">En **Dominios bloqueados o permitidos,** elija y agregue el nombre del **+** dominio que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="e246f-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="e246f-124">Asegúrese de que el administrador de la otra organización realiza estos mismos pasos en su **Centro de administración de Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="e246f-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="e246f-125">Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.</span><span class="sxs-lookup"><span data-stu-id="e246f-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="e246f-126">Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.</span><span class="sxs-lookup"><span data-stu-id="e246f-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="e246f-127">Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="e246f-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="e246f-128">Esto puede requerir agregar los FQDN a la lista de permitidos de salida en la configuración de infraestructura de proxy o firewall: **\* .api.skype.com,** \* **.users.storage.live.com** **y graph.skype.com.**</span><span class="sxs-lookup"><span data-stu-id="e246f-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="e246f-129">Para obtener instrucciones sobre cómo abrir estos puertos en el firewall, consulta la documentación proporcionada.</span><span class="sxs-lookup"><span data-stu-id="e246f-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="e246f-130">Para obtener una lista de todos los puertos que debe abrir, vea las URL de [Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)y los intervalos de direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="e246f-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="e246f-131">Asegúrese de que el administrador de la organización también ha seguido estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e246f-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="e246f-132">**AGUARDE HASTA 24 HORAS PARA LA PRUEBA**.</span><span class="sxs-lookup"><span data-stu-id="e246f-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="e246f-133">Cuando cambia la configuración de comunicaciones externas, los cambios pueden tardar hasta 24 horas en completarse en todos los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="e246f-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="e246f-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="e246f-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="e246f-135">Para obtener más información, vea Permitir que los [usuarios de Skype Empresarial agreguen contactos de Skype.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="e246f-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="e246f-136">Probar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="e246f-136">Test and troubleshoot</span></span>

<span data-ttu-id="e246f-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e246f-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="e246f-138">**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**</span><span class="sxs-lookup"><span data-stu-id="e246f-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="e246f-139">Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.</span><span class="sxs-lookup"><span data-stu-id="e246f-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="e246f-140">Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.</span><span class="sxs-lookup"><span data-stu-id="e246f-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="e246f-141">En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.</span><span class="sxs-lookup"><span data-stu-id="e246f-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="e246f-142">Si recibe un mensaje que indica que no se pudo enviar debido a la directiva de la empresa, tendrá que volver a comprobar sus direcciones URL e intervalos de direcciones IP de [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="e246f-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="e246f-p108">Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).</span><span class="sxs-lookup"><span data-stu-id="e246f-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="e246f-145">Otra forma de comprobar si el problema es del firewall es ir a un lugar que no esté bloqueado por el firewall, como una cafetería.</span><span class="sxs-lookup"><span data-stu-id="e246f-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="e246f-146">Use Skype Empresarial para enviar una solicitud a su contacto para chatear.</span><span class="sxs-lookup"><span data-stu-id="e246f-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="e246f-147">Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.</span><span class="sxs-lookup"><span data-stu-id="e246f-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="e246f-148">Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio</span><span class="sxs-lookup"><span data-stu-id="e246f-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="e246f-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e246f-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="e246f-150">Después de habilitar la comunicación externa con otros usuarios de Skype Empresarial, los usuarios pueden buscar usuarios federados de Skype Empresarial buscando sus nombres de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e246f-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="e246f-151">Un ejemplo es Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e246f-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="e246f-152">Luego deben agregar a la persona a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="e246f-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Para buscar un usuario en una empresa federada, debe buscar su dirección de correo electrónico (normalmente también es su nombre de inicio de sesión).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="e246f-154">Sugerencias para configurar las comunicaciones con empresas federadas</span><span class="sxs-lookup"><span data-stu-id="e246f-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="e246f-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e246f-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="e246f-156">Para configurar la federación entre Skype Empresarial 2015 y Skype Empresarial Online, consulte este artículo: Configurar la federación [con Skype Empresarial Online.](https://technet.microsoft.com/library/jj205126.aspx)</span><span class="sxs-lookup"><span data-stu-id="e246f-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>

- <span data-ttu-id="e246f-157">Para configurar la federación entre Lync y Skype Empresarial Online, consulte este artículo: Configurar la compatibilidad de federación [para un cliente de Lync Online.](https://technet.microsoft.com/library/hh202193.aspx)</span><span class="sxs-lookup"><span data-stu-id="e246f-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>

- <span data-ttu-id="e246f-158">Cuando dos usuarios de Skype Empresarial en Microsoft 365 u Office 365 se comunican entre sí en dominios independientes, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o uso compartido del escritorio) que están activadas en ambas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="e246f-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="e246f-159">Si un usuario de Skype Empresarial de su organización se pone en retención por juicio o In-Place, todas las  conversaciones de mensajería instantánea entre ese usuario y otros usuarios de Skype Empresarial o Skype se guardarán en Elementos recuperables de su buzón.</span><span class="sxs-lookup"><span data-stu-id="e246f-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="e246f-160">Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.</span><span class="sxs-lookup"><span data-stu-id="e246f-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="e246f-161">Desactivar la comunicación externa para personas específicas</span><span class="sxs-lookup"><span data-stu-id="e246f-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="e246f-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e246f-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="e246f-163">Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.</span><span class="sxs-lookup"><span data-stu-id="e246f-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="e246f-164">Inicie sesión con su cuenta de administrador de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="e246f-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="e246f-165">En el centro de administración, vaya a **Usuarios**  >  **activos.**</span><span class="sxs-lookup"><span data-stu-id="e246f-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e246f-166">En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="e246f-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="e246f-168">En el **Centro de administración de Skype Empresarial,** elija **Comunicaciones externas.**</span><span class="sxs-lookup"><span data-stu-id="e246f-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="e246f-169">En la **página** Opciones, se seleccionarán todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="e246f-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="e246f-170">Desactive las comunicaciones que desee deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="e246f-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="e246f-171">En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.</span><span class="sxs-lookup"><span data-stu-id="e246f-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="e246f-173">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e246f-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e246f-174">Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto.</span><span class="sxs-lookup"><span data-stu-id="e246f-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="e246f-175">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e246f-175">Related topics</span></span>

<span data-ttu-id="e246f-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e246f-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="e246f-177">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e246f-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="e246f-178">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="e246f-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  