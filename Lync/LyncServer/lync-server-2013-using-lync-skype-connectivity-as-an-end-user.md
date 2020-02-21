---
title: 'Lync Server 2013: usar la conectividad de Lync y Skype como usuario final'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6971ef2d6fb08838a4fcf71f4fec8097a7f9e47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="11905-102">Usar la conectividad de Lync y Skype en Lync Server 2013 como un usuario final</span><span class="sxs-lookup"><span data-stu-id="11905-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11905-103">_**Última modificación del tema:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="11905-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="11905-104">Lync: la conectividad de Skype permite a los usuarios de Skype y a los usuarios de Lync agregarse entre sí como contactos, intercambiar mensajes instantáneos y realizar llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="11905-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="11905-105">Cuando un usuario de Skype agrega un usuario de Lync, un usuario de Skype creará un contacto en Skype que contendrá el identificador uniforme de recursos (URI) del Protocolo de inicio de sesión (SIP) del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="11905-106">Por el contrario, cuando un usuario de Lync agrega un contacto de Skype, el usuario de Lync creará un contacto en Lync que contendrá la cuenta de Microsoft (MSA) del usuario de Skype y no el nombre de usuario de Skype.</span><span class="sxs-lookup"><span data-stu-id="11905-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="11905-107">**¿Qué es una MSA?**</span><span class="sxs-lookup"><span data-stu-id="11905-107">**What is an MSA?**</span></span> <span data-ttu-id="11905-108">Los usuarios de Skype deben iniciar sesión en Skype con una cuenta de Microsoft (anteriormente denominada Windows Live ID) para poder comunicarse con los contactos de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="11905-109">Una cuenta de Microsoft consta de la combinación de una dirección de correo electrónico y una contraseña, que también puede usar para iniciar sesión en servicios como la tecnología de almacenamiento de Microsoft OneDrive, Windows Phone, el servicio de juegos de Microsoft Xbox LIVE online y la mensajería de Microsoft Outlook. y el cliente de colaboración (y, anteriormente, el servicio de correo electrónico basado en Web de Microsoft hotmail o Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="11905-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="11905-110">Si usa una dirección de correo electrónico y una contraseña para iniciar sesión en estos u otros servicios, ya tiene una cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11905-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="11905-111">Para obtener más información sobre cómo crear una cuenta de Microsoft, vea la página de registro [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)de la cuenta de Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="11905-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="11905-112">Puede combinar la cuenta de Skype existente con la cuenta de Microsoft para el inicio de sesión único en una amplia variedad de aplicaciones y servicios.</span><span class="sxs-lookup"><span data-stu-id="11905-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="11905-113">Una vez que se combina la cuenta, un usuario de Skype puede enviar una solicitud de contacto a los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11905-114">Para que los usuarios de Lync y Skype se comuniquen completamente entre sí, deben cumplirse los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="11905-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="11905-115">Los usuarios de Skype deben iniciar sesión en su cliente de Skype con una cuenta de Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="11905-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="11905-116">Los usuarios de Lync deben estar habilitados para la conectividad de mensajería instantánea pública por parte del administrador de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="11905-117">Cuando un usuario de Skype agrega un contacto de Lync, compruebe que la palabra Lync aparece debajo del nombre del contacto.</span><span class="sxs-lookup"><span data-stu-id="11905-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="11905-118">Esto indica que se ha encontrado un URI de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="11905-119">Cuando un usuario de Skype agrega un contacto de Lync y se devuelven cero resultados de búsqueda para ese dominio de Lync, es posible que el proceso de aprovisionamiento de PIC no haya finalizado o que aún no se haya configurado el dominio de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="11905-120">En función de la configuración de privacidad de los usuarios de Lync y Skype, la mensajería instantánea, el vídeo y la presencia pueden no funcionar hasta que cada usuario acepte los nuevos contactos.</span><span class="sxs-lookup"><span data-stu-id="11905-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="11905-121">**Para agregar un contacto de Skype a Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="11905-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="11905-122">En Lync, haga clic en **Agregar un contacto y agregue un contacto que no se encuentra en mi organización**.</span><span class="sxs-lookup"><span data-stu-id="11905-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="11905-123">En la lista de proveedores de contactos disponibles, seleccione **Skype**.</span><span class="sxs-lookup"><span data-stu-id="11905-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="11905-124">En el campo **dirección de mensajería instantánea** , escriba la cuenta de Microsoft (MSA) del usuario de Skype.</span><span class="sxs-lookup"><span data-stu-id="11905-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="11905-125">En el cuadro de lista desplegable **Agregar al grupo de contactos** , seleccione un grupo de contactos al que agregar el usuario.</span><span class="sxs-lookup"><span data-stu-id="11905-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="11905-126">En el cuadro desplegable **establecer relación de privacidad** , seleccione la configuración de contacto adecuada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11905-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="11905-127">El usuario aparecerá ahora como un contacto en Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="11905-128">Seleccione el usuario, haga clic con el botón derecho en el nombre de usuario y haga clic en **Ver tarjeta de contacto** para ver las propiedades de usuario.</span><span class="sxs-lookup"><span data-stu-id="11905-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="11905-129">Ahora puede establecer una llamada de audio o vídeo con el usuario de Skype que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="11905-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="11905-130">Para obtener más información sobre la compatibilidad con los contactos, consulte [Agregar un contacto en Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="11905-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="11905-131">Cuando una cuenta de Microsoft de usuario de Skype usa un nombre de dominio personalizado, como <strong>Bob@contoso.com</strong> , un usuario de Lync puede agregar esa cuenta Microsoft a Lync de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="11905-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="11905-132">Use el icono **Agregar un contacto** o</span><span class="sxs-lookup"><span data-stu-id="11905-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="11905-133">Use el campo buscar a un **participante o un salón, o marcar un número** .</span><span class="sxs-lookup"><span data-stu-id="11905-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="11905-134">En cada instancia, el usuario de Lync debe escribir el correo electrónico del usuario de Skype con el siguiente formato: <strong>usuario (nombre de dominio) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="11905-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11905-135">Este paso no es necesario para las cuentas de Microsoft que usan los siguientes nombres de dominio: <STRONG>@live. com, @hotmail. com o @outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="11905-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="11905-136">Para obtener más información sobre los nombres de dominio personalizados admitidos, consulte <A href="https://support.microsoft.com/kb/897567">dominios de mensajería instantánea pública admitidos</A>.</span><span class="sxs-lookup"><span data-stu-id="11905-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="11905-137">**Para agregar un contacto de Skype a Lync cuando se usa un nombre de dominio personalizado**</span><span class="sxs-lookup"><span data-stu-id="11905-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="11905-138">En Lync, haga clic en **Agregar un contacto y agregue un contacto que no se encuentra en mi organización**.</span><span class="sxs-lookup"><span data-stu-id="11905-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="11905-139">En la lista de proveedores de contactos disponibles, seleccione **Skype**.</span><span class="sxs-lookup"><span data-stu-id="11905-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="11905-140">En el campo **dirección de mensajería instantánea** , escriba la cuenta de Microsoft (MSA) del usuario de Skype con el formato <strong>usuario (nombre de dominio) @msn. com</strong>.</span><span class="sxs-lookup"><span data-stu-id="11905-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="11905-141">Por lo tanto, para el usuario bob@contoso.com, <strong>la entrada sería Bob (contoso. com)<strong> @msn. com.</span><span class="sxs-lookup"><span data-stu-id="11905-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="11905-142">En el cuadro de lista desplegable **Agregar al grupo de contactos** , seleccione un grupo de contactos al que agregar el usuario.</span><span class="sxs-lookup"><span data-stu-id="11905-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="11905-143">En el cuadro de lista desplegable **establecer relación de privacidad** , seleccione la configuración de contacto adecuada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11905-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="11905-144">Un usuario de Lync también puede usar el campo **buscar a alguien o un salón o marcar un número** en Lync y agregar una dirección similar al siguiente <strong>usuario (nombre de dominio) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="11905-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="11905-145">Por lo tanto, para la cuenta de Microsoft bob@contoso.com, la entrada sería <strong>Bob (contoso. com) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="11905-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="11905-146">Siga los pasos 4 y 5 descritos anteriormente en este procedimiento para agregar el contacto a un grupo de contactos y para seleccionar la relación de privacidad adecuada.</span><span class="sxs-lookup"><span data-stu-id="11905-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="11905-147">**Para agregar un contacto de Lync a Skype**</span><span class="sxs-lookup"><span data-stu-id="11905-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="11905-148">Inicie sesión en Skype.</span><span class="sxs-lookup"><span data-stu-id="11905-148">Sign in to Skype.</span></span> <span data-ttu-id="11905-149">El usuario de Skype debe iniciar sesión en su cliente de Skype con una cuenta de Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="11905-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="11905-150">Seleccione el icono Agregar contactos.</span><span class="sxs-lookup"><span data-stu-id="11905-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="11905-151">Escriba el URI del SIP del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="11905-152">Por ejemplo, bernardo@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="11905-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="11905-153">Cuando Skype encuentre la coincidencia en los resultados de la búsqueda, busque la palabra **Lync** debajo del nombre del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="11905-154">Esto indica que Skype ha encontrado correctamente el URI del SIP del cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="11905-155">Haga clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="11905-155">Click the name.</span></span>

5.  <span data-ttu-id="11905-156">En la esquina superior derecha de la ventana, haga clic en Agregar a contactos.</span><span class="sxs-lookup"><span data-stu-id="11905-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="11905-157">El nuevo contacto ahora se agrega a la lista de contactos, pero verá un signo de interrogación en lugar de su icono de estado hasta que acepte la solicitud.</span><span class="sxs-lookup"><span data-stu-id="11905-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="11905-158">Cuando el nuevo contacto acepte su solicitud, podrá ver cuándo están en línea, iniciar conversaciones de mensajería instantánea y realizar llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="11905-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="11905-159">El administrador de Lync Server debe configurar las opciones de directiva del usuario de Lync para permitir las solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="11905-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="11905-160">De lo contrario, el usuario de Lync no recibirá las solicitudes de contacto del usuario de Skype.</span><span class="sxs-lookup"><span data-stu-id="11905-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="11905-161">En función de la configuración de la Directiva del usuario de Lync, la solicitud para agregar el usuario de Skype aparecerá en la pestaña <STRONG>nuevo</STRONG> del cliente de Lync. Para empezar a comunicarse con el usuario de Skype, el usuario de Lync debe agregar el usuario de Skype a la lista Favoritos o a una lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="11905-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="11905-162">La imagen siguiente muestra la ubicación de la <STRONG>nueva</STRONG> pestaña en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="11905-163">Un usuario de Lync debe configurar las alertas de Lync para asegurarse de que las solicitudes enviadas desde un usuario de Skype se muestren y puedan ser detectadas por el usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="11905-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="11905-164">Para configurar las alertas de Lync, siga el procedimiento que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="11905-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="11905-165">**Para configurar las alertas de Lync**</span><span class="sxs-lookup"><span data-stu-id="11905-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="11905-166">En el cliente de Lync, haga clic en el icono **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="11905-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="11905-167">Seleccione **alertas**.</span><span class="sxs-lookup"><span data-stu-id="11905-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="11905-168">En **alertas generales**, Active **informar cuando alguien me agregue a su lista de contactos**.</span><span class="sxs-lookup"><span data-stu-id="11905-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="11905-169">En **contactos que no usan Lync**, seleccione **permitir invitaciones pero bloquear todas las demás comunicaciones**.</span><span class="sxs-lookup"><span data-stu-id="11905-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="11905-170">Haga clic en **Aceptar** para cerrar la ventana Opciones.</span><span class="sxs-lookup"><span data-stu-id="11905-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

