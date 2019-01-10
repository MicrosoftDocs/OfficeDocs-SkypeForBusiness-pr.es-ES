---
title: Administrar características de Microsoft Teams en su organización de Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a activar o desactivar las aplicaciones de Microsoft Teams en su organización de Office 365, incluidos los conectores, las fichas, los bots o cualquier combinación de los tres.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a36c0a23076c5aa172824fe85103c57a8494dbf
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458481"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="294c1-103">Administrar características de Microsoft Teams en su organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="294c1-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

<span data-ttu-id="294c1-p101">Todas las configuraciones de Teams se migrarán pronto al nuevo Centro de administración de Microsoft Teams y Skype Empresarial. La única característica que se administra en el Centro de administración de Office 365 es Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="294c1-p101">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center. The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="294c1-106">A menos que se indique lo contrario, el valor predeterminado para una opción es **Activado**.</span><span class="sxs-lookup"><span data-stu-id="294c1-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="294c1-107">Configuración de todos los inquilinos en Office 365</span><span class="sxs-lookup"><span data-stu-id="294c1-107">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="294c1-108">En **Configuración de todos los inquilinos** puede activar o desactivar Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="294c1-108">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="294c1-p102">Para editar **Configuración de todos los inquilinos** para Teams, vaya al Centro de administración de Microsoft Teams y Skype Empresarial y seleccione **Portal anterior**. Elija **Configuración** > **Servicios y complementos** > **Microsoft Teams**. Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:</span><span class="sxs-lookup"><span data-stu-id="294c1-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft Teams & Skype for Business Admin Center, and select **Legacy portal**. Choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="294c1-112">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="294c1-112">Apps</span></span>

<span data-ttu-id="294c1-p103">Las aplicaciones son fichas, conectores, bots o cualquier combinación de estos tres elementos que proporciona un servicio de terceros. Hay directivas de administración de Microsoft Teams que se pueden configurar en el Centro de administración de Office 365 para controlar qué aplicaciones externas de terceros están permitidas. Estas directivas permiten especificar qué aplicaciones están permitidas y cuáles no, el comportamiento de las aplicaciones nuevas externas y si se permite la instalación de prueba de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="294c1-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="294c1-116">La sección **Aplicaciones** le permite establecer la siguiente configuración para su organización:</span><span class="sxs-lookup"><span data-stu-id="294c1-116">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Captura de pantalla de la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="294c1-118">**Permitir aplicaciones externas en Microsoft Teams:** si este conmutador está activado, los usuarios pueden agregar las fichas y los bots que estén disponibles al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="294c1-118">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Captura de pantalla del control para permitir aplicaciones externas en la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="294c1-p104">**Habilitar nuevas aplicaciones externas de manera predeterminada**: si este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams. Desactive este conmutador si quiere controlar las aplicaciones nuevas. Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés.</span><span class="sxs-lookup"><span data-stu-id="294c1-p104">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this switch if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="294c1-123">**Permitir la instalación de prueba de aplicaciones externas:** si este conmutador está activado, los usuarios pueden instalar y activar bots y fichas personalizados.</span><span class="sxs-lookup"><span data-stu-id="294c1-123">**Allow sideloading of external apps**: When this switch is turned on, users can install and turn on custom bots and tabs.</span></span> 

<span data-ttu-id="294c1-124">Para obtener más información, consulte [Configurar la administración para aplicaciones en Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="294c1-124">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings"></a><span data-ttu-id="294c1-125">Configuración de toda la organización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="294c1-125">Teams org-wide settings</span></span>

<span data-ttu-id="294c1-126">Puede controlar la configuración del usuario de toda la organización en el Centro de administración de Microsoft Teams y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="294c1-126">You can control organization-wide user settings in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="294c1-127">Para editar la configuración de toda la organización, vaya al Centro de administración de Microsoft Teams y Skype Empresarial y seleccione **Configuración de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="294c1-127">To edit org-wide settings, go to the Microsoft Skype for Business Admin Center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="294c1-128">Puede configurar las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="294c1-128">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="294c1-129">Acceso externo</span><span class="sxs-lookup"><span data-stu-id="294c1-129">External access</span></span>

<span data-ttu-id="294c1-p106">**Acceso externo** permite que los usuarios de Teams y Skype Empresarial se comuniquen con usuarios de fuera de la organización. Para configurar el acceso externo, vaya a [Permitir que los usuarios de Teams chateen y se comuniquen con usuarios de otra organización de Teams](let-your-teams-users-communicate-with-other-people.md).</span><span class="sxs-lookup"><span data-stu-id="294c1-p106">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

### <a name="guest-access"></a><span data-ttu-id="294c1-132">Acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="294c1-132">Guest access</span></span>

<span data-ttu-id="294c1-p107">**Acceso de invitado** en Microsoft Teams permite que los equipos de su organización puedan colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales. Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo. Para obtener más información, consulte [Acceso de invitado de Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="294c1-p107">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="294c1-136">Configuración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="294c1-136">Teams settings</span></span>

<span data-ttu-id="294c1-137">En **Configuración de Microsoft Teams** puede configurar la integración del correo electrónico, las opciones de almacenamiento en nube, la interoperabilidad de Skype Empresarial y los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="294c1-137">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="294c1-138">Integración del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="294c1-138">Email integration</span></span>

<span data-ttu-id="294c1-p108">Active esta característica para que los usuarios puedan enviar un correo electrónico a un canal en Microsoft Teams mediante la dirección de correo electrónico del canal. Los usuarios pueden hacer esto para cualquier canal que pertenezca a un equipo que sea de su posesión. Los usuarios también pueden enviar correos electrónicos a cualquier canal de un equipo que tenga conectores activados para los miembros del equipo. Para activar la integración del correo electrónico, asegúrese de que **Permitir que los usuarios puedan enviar correos electrónicos a la dirección de correo electrónico de un canal** esté **Activado**.</span><span class="sxs-lookup"><span data-stu-id="294c1-p108">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="294c1-143">Archivos</span><span class="sxs-lookup"><span data-stu-id="294c1-143">Files</span></span>

<span data-ttu-id="294c1-144">Aquí puede activar o desactivar las opciones de uso compartido de archivos y de almacenamiento de archivos en la nube.</span><span class="sxs-lookup"><span data-stu-id="294c1-144">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="294c1-p109">Los usuarios pueden cargar y compartir archivos de los servicios de almacenamiento en nube en los canales y chats de Teams. Las opciones de almacenamiento en nube en Microsoft Teams actualmente incluyen ShareFile, Dropbox, Box y Google Drive. Active el conmutador de los proveedores de almacenamiento en nube que quiera usar su organización.</span><span class="sxs-lookup"><span data-stu-id="294c1-p109">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="294c1-148">Organización</span><span class="sxs-lookup"><span data-stu-id="294c1-148">Organization</span></span>

<span data-ttu-id="294c1-p110">Aquí puede activar la ficha **Organización**, que muestra el organigrama detallado de la organización del usuario. Si desea más información, consulte [Usar la ficha Organización en Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span><span class="sxs-lookup"><span data-stu-id="294c1-p110">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="skype-for-business-interop"></a><span data-ttu-id="294c1-151">Interoperabilidad de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="294c1-151">Skype for Business interop</span></span>

<span data-ttu-id="294c1-p111">Use esta configuración para que los usuarios de Teams puedan chatear con los usuarios de Skype Empresarial. Para obtener información detallada sobre la interoperabilidad entre Teams y Skype Empresarial, vaya a [Descripción de la coexistencia y la interoperabilidad de Skype Empresarial y Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="294c1-p111">Use this setting to let Teams users chat with Skype for Business users. For detailed information about interoperability between Teams and Skype for Business, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="devices"></a><span data-ttu-id="294c1-154">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="294c1-154">Devices</span></span>

<span data-ttu-id="294c1-p112">Esta configuración controla el comportamiento de la cuenta del recurso para los dispositivos Surface Hub que asisten a las reuniones de Microsoft Teams. Use estas opciones para configurar los requisito de autenticación, requerir un PIN de contenido y activar las cuentas de recurso de Surface Hub para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="294c1-p112">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="294c1-157">**Requerir un método secundario de autenticación para acceder al contenido de la reunión**: Seleccione el nivel de acceso que tienen los usuarios cuando especifican el PIN de contenido.</span><span class="sxs-lookup"><span data-stu-id="294c1-157">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="294c1-p113">**Establecer el PIN de contenido**: Requiera que los usuarios especifiquen este PIN para impedir el acceso no autorizado a los documentos. Con esto se impide que los usuarios no autorizados se unan a reuniones futuras y vean los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="294c1-p113">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="294c1-160">**Las cuentas de recursos pueden enviar mensajes**: **Active** esta opción para permitir que se envíen mensajes desde la cuenta del recurso de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="294c1-160">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search"></a><span data-ttu-id="294c1-161">Buscar</span><span class="sxs-lookup"><span data-stu-id="294c1-161">Search</span></span>

<span data-ttu-id="294c1-p114">La búsqueda de directorios enfocada de Microsoft Teams usa la directiva de libretas de direcciones (APB) de Exchange para permitir que las organizaciones puedan crear límites virtuales que controlen la forma en que los usuarios pueden encontrar a otros usuarios de la organización y comunicarse con ellos. Sería conveniente usar la búsqueda de directorios enfocada en estas situaciones:</span><span class="sxs-lookup"><span data-stu-id="294c1-p114">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="294c1-164">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="294c1-164">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="294c1-165">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="294c1-165">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="294c1-166">**Active** esta opción para activar las búsquedas de directorios enfocadas.</span><span class="sxs-lookup"><span data-stu-id="294c1-166">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="294c1-167">Actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="294c1-167">Teams upgrade</span></span>

<span data-ttu-id="294c1-168">Puede usar esta opción para configurar la forma en que los usuarios actualizan de Skype Empresarial a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="294c1-168">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="294c1-169">Modo de coexistencia</span><span class="sxs-lookup"><span data-stu-id="294c1-169">Coexistence mode</span></span>
<span data-ttu-id="294c1-p115">Puede especificar un modo de coexistencia: **Microsoft Teams solo**, **Aplicaciones aisladas** (coexistencia de Teams y Skype Empresarial) o **Skype Empresarial solo**. El modo de coexistencia que elija determina el enrutamiento de las llamadas entrantes y de los chats, así como la aplicación que utiliza el usuario para iniciar los chats y las llamadas, o para programar reuniones. Para obtener más información sobre los modos de coexistencia, vaya a [Descripción de la coexistencia y la interoperabilidad de Skype Empresarial y Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="294c1-p115">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="294c1-173">Preferencias de la aplicación</span><span class="sxs-lookup"><span data-stu-id="294c1-173">App preferences</span></span>

<span data-ttu-id="294c1-p116">Aquí puede elegir la aplicación que utilizarán los usuarios para unirse a las reuniones de Skype Empresarial (Skype Empresarial o la [Aplicación Reuniones de Skype](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Esta opción no depende de la configuración del modo de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="294c1-p116">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="294c1-176">¿Cómo puedo saber qué características están disponibles?</span><span class="sxs-lookup"><span data-stu-id="294c1-176">How can I tell which features are available?</span></span>

<span data-ttu-id="294c1-p117">Lea el [Mapa de ruta de Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para ver información sobre las nuevas características de Microsoft Teams. Para obtener más información acerca de las nuevas y las próximas características, vea la página de [Novedades](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) de Teams y el [blog de la comunidad tecnológica de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531).</span><span class="sxs-lookup"><span data-stu-id="294c1-p117">See the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="294c1-179">Más información</span><span class="sxs-lookup"><span data-stu-id="294c1-179">More information</span></span>

<span data-ttu-id="294c1-180">Para obtener información sobre qué roles pueden realizar funciones de administración, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="294c1-180">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
