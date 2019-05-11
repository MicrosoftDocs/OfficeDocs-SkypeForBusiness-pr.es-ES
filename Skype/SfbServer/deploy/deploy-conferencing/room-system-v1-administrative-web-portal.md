---
title: Implementar SRS v1 administrativas Web Portal en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: El Skype para sistemas de negocio Server Skype salón v1 (v1 SRS, anteriormente conocido como sistema de sala de Lync) administrativas Portal Web es un portal web que las organizaciones pueden usar para mantener las salas de conferencias de sistemas de salón de Skype. Los administradores pueden usar el Portal Web del SRS v1 administrativas para supervisar el estado del dispositivo, por ejemplo mediante la supervisión de dispositivos de audio y vídeo. Con este portal, los administradores también pueden recopilar información de diagnóstico de forma remota para supervisar el estado de las salas de conferencias.
ms.openlocfilehash: ee94db48470747999b2554732bc03d72d129adbd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895071"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="70f31-105">Implementar SRS v1 administrativas Web Portal en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="70f31-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="70f31-106">El Skype para sistemas de negocio Server Skype salón v1 (v1 SRS, anteriormente conocido como sistema de sala de Lync) administrativas Portal Web es un portal web que las organizaciones pueden usar para mantener las salas de conferencias de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="70f31-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="70f31-107">Los administradores pueden usar el Portal Web del SRS v1 administrativas para supervisar el estado del dispositivo, por ejemplo mediante la supervisión de dispositivos de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="70f31-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="70f31-108">Con este portal, los administradores también pueden recopilar información de diagnóstico de forma remota para supervisar el estado de las salas de conferencias.</span><span class="sxs-lookup"><span data-stu-id="70f31-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="70f31-109">Para usar esta característica, el Portal Web del SRS v1 administrativas debe estar implementado en cada Skype para Business Server Front-End Server.</span><span class="sxs-lookup"><span data-stu-id="70f31-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="70f31-110">Esta guía proporciona instrucciones para administradores sobre cómo instalar y configurar el portal web administrativo de SRS.</span><span class="sxs-lookup"><span data-stu-id="70f31-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="70f31-111">Está destinado a los administradores que tienen conocimiento de Skype para la administración de Business Server y que tienen derechos de usuario de administrador para modificar la Skype de topología de servidores de negocio.</span><span class="sxs-lookup"><span data-stu-id="70f31-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="70f31-112">Después de la v1 SRS que administrativas Portal Web se implementa en el servidor, los administradores pueden comprobar el estado SRS v1 para los dispositivos, inicie sesión el sitio desde sus propios equipos o equipos portátiles.</span><span class="sxs-lookup"><span data-stu-id="70f31-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70f31-113">Descargue el [Portal de sistemas v1 Web administrativo para Skype para Business Server 2015 de sala de Microsoft Skype](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="70f31-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="70f31-114">En este tema:</span><span class="sxs-lookup"><span data-stu-id="70f31-114">In this topic:</span></span>

- [<span data-ttu-id="70f31-115">Configurar el entorno para el portal web administrativo de SRS v1</span><span class="sxs-lookup"><span data-stu-id="70f31-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="70f31-116">Instalar el portal web administrativo de SRS v1</span><span class="sxs-lookup"><span data-stu-id="70f31-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="70f31-117">Usar el portal web administrativo de SRS</span><span class="sxs-lookup"><span data-stu-id="70f31-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="70f31-118">Configurar el entorno para el portal web administrativo de SRS v1</span><span class="sxs-lookup"><span data-stu-id="70f31-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="70f31-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="70f31-119"></span></span>

<span data-ttu-id="70f31-120">Para usar el portal web administrativo de SRS v1, tendrá que instalar o configurar los siguientes requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="70f31-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70f31-p104">Si el servidor está configurado con la autenticación Kerberos y NTLM, y se está ejecutando SRS en un equipo que no está unido al dominio, la autenticación Kerberos generará un error y el usuario no verá el estado de SRS en el portal administrativo. Para resolver este problema, configure el servidor con autenticación NTLM o autenticación NTLM y TLS-DSK (sin Kerberos), o una el equipo SRS al dominio.</span><span class="sxs-lookup"><span data-stu-id="70f31-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="70f31-123">Instalar Skype para actualizaciones acumulativas de servidor empresarial en el Skype de topología de servidores de negocio.</span><span class="sxs-lookup"><span data-stu-id="70f31-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="70f31-124">Para obtener la actualización o ver qué se incluye con él, vea [actualizaciones para Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="70f31-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="70f31-125">Cree un usuario de Active Directory habilitado para usar SIP.</span><span class="sxs-lookup"><span data-stu-id="70f31-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="70f31-126">El Portal Web del SRS v1 administrativas usa estas credenciales para consultar la información de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="70f31-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="70f31-127">El nombre de usuario de los ejemplos es LRSApp.</span><span class="sxs-lookup"><span data-stu-id="70f31-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="70f31-128">Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="70f31-p106">Cree el grupo con el ámbito de grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para usar SIP que se agreguen a este grupo estarán autorizados para ver la lista de salones y ejecutar algunos comandos, como la recopilación de registros.</span><span class="sxs-lookup"><span data-stu-id="70f31-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="70f31-131">Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="70f31-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="70f31-p107">Cree el grupo con el ámbito de grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para usar SIP que se agreguen a este grupo estarán autorizados para usar toda la funcionalidad del portal administrativo en una sala de Skype. Para incluir compatibilidad con la administración en masa de salas de Skype, consulte el paso 5. </span><span class="sxs-lookup"><span data-stu-id="70f31-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Lista de grupos de administración con el rol de grupo de seguridad](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="70f31-135">Cree un grupo de seguridad de Active Directory con el nombre LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="70f31-136">Cree el grupo con el ámbito de grupo Global y el tipo de grupo Seguridad.</span><span class="sxs-lookup"><span data-stu-id="70f31-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="70f31-137">Los usuarios habilitados para SIP agregados a este grupo están autorizados a utilizar todas las funciones de portal de administración, incluida la administración masiva de Skype para salas de negocio.</span><span class="sxs-lookup"><span data-stu-id="70f31-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="70f31-138">Agregar LRSFullAccessAdminGroup como un miembro de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Página de miembros de la propiedad LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="70f31-140">Cree un usuario de Active Directory habilitado para usar SIP con el nombre LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="70f31-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="70f31-141">Agregue este usuario a LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Página de miembros de la propiedad LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="70f31-143">Instalar [ASP.NET MVC 4 para Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="70f31-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="70f31-144">Instalar el portal web administrativo de SRS v1</span><span class="sxs-lookup"><span data-stu-id="70f31-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="70f31-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="70f31-145"></span></span>

<span data-ttu-id="70f31-146">Descargue el [Portal de sistemas v1 Web administrativo para Skype para Business Server 2015 de sala de Microsoft Skype](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="70f31-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="70f31-147">Para instalar el portal web administrativo de SRS v1, use los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="70f31-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="70f31-148">Configure el puerto de la aplicación de confianza ejecutando el siguiente cmdlet en Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="70f31-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="70f31-149">Para instalar el portal de salas de reuniones, descargue **MeetingRoomPortalInstaller.msi** y ejecútelo como administrador.</span><span class="sxs-lookup"><span data-stu-id="70f31-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="70f31-150">Abra el archivo Web.config, que se encuentra en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="70f31-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="70f31-151">%Archivos de programa%\Skype Empresarial Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span><span class="sxs-lookup"><span data-stu-id="70f31-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span></span>

4. <span data-ttu-id="70f31-152">En el archivo Web.Config, cambie la PortalUserName para el nombre de usuario creado en el paso 2 en la sección "[Configurar el entorno para el Portal Web del SRS v1 administrativas](room-system-v1-administrative-web-portal.md#Config_Env)" (el nombre recomendado en el paso es LRSApp):</span><span class="sxs-lookup"><span data-stu-id="70f31-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="70f31-p110">Dado que el portal administrativo de SRS v1 es una aplicación de confianza, no es necesario que proporcione la contraseña en la configuración del portal. Si este usuario utiliza un registrador diferente del local, deberá especificar el registrador que utilizará agregando la siguiente línea en el archivo Web.Config: </span><span class="sxs-lookup"><span data-stu-id="70f31-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="70f31-155">Si utiliza un puerto diferente de 5061, agregue la siguiente línea en el archivo Web.Config: </span><span class="sxs-lookup"><span data-stu-id="70f31-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="70f31-156">Verificar la instalación del portal web administrativo de SRS</span><span class="sxs-lookup"><span data-stu-id="70f31-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="70f31-157">Para verificar la instalación del portal web administrativo de SRS v1 haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70f31-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="70f31-158">En un servidor front-end, vaya a la siguiente URL:</span><span class="sxs-lookup"><span data-stu-id="70f31-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="70f31-159">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="70f31-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="70f31-160">No debería ver ningún error, como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="70f31-160">You should not see any errors, as shown in the following image:</span></span>

     ![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="70f31-162">Si no ve ningún error, intente acceder a la siguiente URL desde cualquier otro equipo de la topología:</span><span class="sxs-lookup"><span data-stu-id="70f31-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="70f31-163">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="70f31-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="70f31-164">Para obtener acceso a la página, necesita agregar los registros DNS, tal como se describe en "[necesario registros DNS para automático inicio de sesión de los clientes](https://go.microsoft.com/fwlink/p/?LinkId=318056)".</span><span class="sxs-lookup"><span data-stu-id="70f31-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="70f31-165">Usar el portal web administrativo de SRS</span><span class="sxs-lookup"><span data-stu-id="70f31-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="70f31-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="70f31-166"></span></span>

<span data-ttu-id="70f31-167">Después de implementar SRS en el servidor, puede comprobar el estado de todas las salas de SRS iniciando sesión en el portal web administrativo de SRS v1 desde un explorador.</span><span class="sxs-lookup"><span data-stu-id="70f31-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="70f31-168">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="70f31-168">Sign in</span></span>

1. <span data-ttu-id="70f31-169">Vaya a la siguiente dirección URL:</span><span class="sxs-lookup"><span data-stu-id="70f31-169">Browse to the following URL:</span></span>

    <span data-ttu-id="70f31-170">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="70f31-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="70f31-171">Escriba las credenciales de la cuenta LRSSupport o de una cuenta que se haya agregado a su grupo de seguridad LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="70f31-173">Página de resumen del portal web administrativo de SRS</span><span class="sxs-lookup"><span data-stu-id="70f31-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="70f31-174">La página de resumen ofrece la siguiente información sobre todas las salas de SRS implementadas en el servidor:</span><span class="sxs-lookup"><span data-stu-id="70f31-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="70f31-175">**Etiqueta** El nombre personalizado que proporciona el administrador a la sala.</span><span class="sxs-lookup"><span data-stu-id="70f31-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="70f31-176">La etiqueta se puede establecer en el portal de haciendo clic en el nombre del salón.</span><span class="sxs-lookup"><span data-stu-id="70f31-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="70f31-177">**Mantenimiento** El estado de mantenimiento de la sala, que se deriva el estado de mantenimiento de agregado de la sala, que se muestra en la sección estado de la página de configuración de la sala.</span><span class="sxs-lookup"><span data-stu-id="70f31-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="70f31-178">**Próxima reunión** La fecha y hora de la próxima reunión está programada.</span><span class="sxs-lookup"><span data-stu-id="70f31-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="70f31-179">**SRS versión, fabricante, modelo** Estos valores están predefinidos en SRS.</span><span class="sxs-lookup"><span data-stu-id="70f31-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="70f31-180">Según el fabricante, estos campos pueden dejarse en blanco.</span><span class="sxs-lookup"><span data-stu-id="70f31-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="70f31-181">**Última actualización** Muestra la última vez que se actualiza la página web.</span><span class="sxs-lookup"><span data-stu-id="70f31-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Vista resumida del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="70f31-183">Sólo se verá el menú de administración de forma masiva si forma parte del grupo de seguridad LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="70f31-184">Información sobre salas de SRS</span><span class="sxs-lookup"><span data-stu-id="70f31-184">SRS Room Information</span></span>

<span data-ttu-id="70f31-p113">La sección de información sobre salas del portal le permite ver y configurar salas de SRS individuales. Contiene cuatro secciones: Configuración, Detalles, Registro y Mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="70f31-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="70f31-187">Configuración</span><span class="sxs-lookup"><span data-stu-id="70f31-187">Settings</span></span>

<span data-ttu-id="70f31-p114">En la sección de configuración, puede establecer la contraseña, la etiqueta de la sala y los valores de volumen predeterminados de la sala. Si configura estas opciones, los cambios solo se replican al reiniciar la consola de SRS. Solo verá los ajustes Actualizaciones del sistema para dispositivos de SRS que utilicen la versión 15.12 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="70f31-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Configuración de salones del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="70f31-192">Detalles</span><span class="sxs-lookup"><span data-stu-id="70f31-192">Details</span></span>

<span data-ttu-id="70f31-193">La sección detalles de proporciona un resumen de solo lectura de configuraciones de la sala SRS, incluido: la hora de última actualización; próxima reunión; última actualizaciones, mantenimiento y calibración; configuración del timbre; micrófono y altavoz de forma predeterminada versión; URI DE SIP; número de pantallas y obtener información detallada sobre cada pantalla; estado y la actividad.</span><span class="sxs-lookup"><span data-stu-id="70f31-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Vista en detalle del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="70f31-195">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="70f31-195">Troubleshooting</span></span>

<span data-ttu-id="70f31-p115">La sección de solución de problemas se puede usar para recopilar remotamente registros y guardarlos en una ubicación especificada. También puede reiniciar la consola de SRS (interfaz de usuario de SRS) o el sistema completo. Para recopilar registros, proporcione la ruta a una carpeta en el formato especificado y asegúrese de que la cuenta del equipo de SRS tiene permisos de escritura en esta carpeta. Si el tamaño de los registros es muy grande, la recopilación de registros puede tardar hasta 5 minutos. Actualice la página para ver el estado actualizado.</span><span class="sxs-lookup"><span data-stu-id="70f31-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="70f31-201">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="70f31-201">Health</span></span>

<span data-ttu-id="70f31-202">La sección Mantenimiento proporciona una indicación visual del estado de la Skype para Business Server connection, dispositivo de audio, dispositivo de vídeo, estado de resistencia y el dispositivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="70f31-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Estado de los salones del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="70f31-204">Notas adicionales sobre el portal web administrativo</span><span class="sxs-lookup"><span data-stu-id="70f31-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="70f31-205">Cambios en la configuración se aplican sólo después de que el sistema SRS es reiniciado .> si caduca la contraseña de la cuenta LRSApp, no podrá ver el estado de las salas.</span><span class="sxs-lookup"><span data-stu-id="70f31-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="70f31-206">Configurar la contraseña de la cuenta LRSAppuser para que nunca caduca o asegúrese de actualizar la contraseña cuando está cerca de expiration.> el SRS administrativas portal web es compatible con las implementaciones locales únicamente.</span><span class="sxs-lookup"><span data-stu-id="70f31-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="70f31-207">Administración en masa </span><span class="sxs-lookup"><span data-stu-id="70f31-207">Bulk management</span></span>

<span data-ttu-id="70f31-208">La administración en masa de salas de SRS es una característica diseñada para los administradores de TI avanzados, con la finalidad de simplificar su flujo de trabajo y ofrecerles una herramienta práctica y rápida para administrar remotamente varias salas de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="70f31-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="70f31-209">Para ver esta característica, el usuario debe ser miembro del grupo de seguridad especial, **LRSPowerUserAdminsGroup**.  </span><span class="sxs-lookup"><span data-stu-id="70f31-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="70f31-p117">No hay límite en el número de salas de SRS que se puede seleccionar para la administración en masa. Sin embargo, no se puede realizar más de una operación en masa a la vez.</span><span class="sxs-lookup"><span data-stu-id="70f31-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="70f31-212">Para realizar una operación de administración en masa, seleccione las salas que quiera supervisar y haga clic en el menú Administración de masa. </span><span class="sxs-lookup"><span data-stu-id="70f31-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="70f31-213">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="70f31-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="70f31-214">¿Por qué no puedo iniciar sesión en el portal web administrativas?</span><span class="sxs-lookup"><span data-stu-id="70f31-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="70f31-215">Cuando se abre https://localhost/lrs, podrá ver la página de inicio de sesión, pero cuando se escribe en sus credenciales, no puede iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="70f31-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="70f31-216">En este caso, debe abrir el https://FQDNofFEserver/SRS para iniciar sesión en el portal web administrativo.</span><span class="sxs-lookup"><span data-stu-id="70f31-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="70f31-217">¿Por qué no puedo ver v1 SRS en el portal web administrativa?</span><span class="sxs-lookup"><span data-stu-id="70f31-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="70f31-218">Asegúrese de que su implementación tiene cuentas de SRS y de que estas se han creado según las recomendaciones de implementación del portal web administrativo de SRS.</span><span class="sxs-lookup"><span data-stu-id="70f31-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="70f31-219">Asegúrese de que las cuentas SRS se aprovisionan con Enable-CsMeetingRoom, no habilitar-CsUser, en la Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="70f31-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="70f31-220">Si ha creado las cuentas SRS y no se puede ver las cuentas en el portal web administrativa, recopilar los registros del servidor mediante el Skype para la herramienta de registro de servidor empresarial con el componente de **MeetingPortal** seleccionado y, a continuación, enviarlos a su contacto de soporte técnico SRS.</span><span class="sxs-lookup"><span data-stu-id="70f31-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="70f31-p120">Si ha creado cuentas de SRS y no las ve en el portal web administrativo, recopile los registros de cliente usando Fiddler, copie el registro de la consola de las herramientas de desarrollo del explorador y luego envíe esta información a su contacto de soporte técnico de SRS. También puede modificar el valor del nivel de seguimiento en el archivo Web.Config para obtener un registro más detallado.</span><span class="sxs-lookup"><span data-stu-id="70f31-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="70f31-223">¿Por qué no puedo ver el estado de SRS en el portal web administrativa?</span><span class="sxs-lookup"><span data-stu-id="70f31-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="70f31-224">Asegúrese de que la cuenta de usuario LRSApp esté habilitada para SIP.</span><span class="sxs-lookup"><span data-stu-id="70f31-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="70f31-225">Si sigue teniendo problemas, recopilar el archivo **Trace.log** en el sistema SRS de D:\Tracing\LRSAdminLogs\, y, a continuación, envíelo a su contacto de soporte técnico SRS.</span><span class="sxs-lookup"><span data-stu-id="70f31-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="70f31-226">¿¿Por qué no puedo ver los menús de administración de forma masiva para SRS en el portal web administrativa?</span><span class="sxs-lookup"><span data-stu-id="70f31-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="70f31-227">Asegúrese de que la cuenta de usuario LRSApp está habilitado para SIP y que forma parte del grupo de seguridad LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="70f31-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="70f31-228">¿Funciona el portal de web administrativa v1 SRS con salas de equipos de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="70f31-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="70f31-229">No.</span><span class="sxs-lookup"><span data-stu-id="70f31-229">No.</span></span>


