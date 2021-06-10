---
title: Preparar el entorno
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo preparar la infraestructura para implementar Salas de Microsoft Teams para que pueda aprovechar todas las características.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117428"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="b67a3-103">Preparar el entorno</span><span class="sxs-lookup"><span data-stu-id="b67a3-103">Prepare your environment</span></span>

<span data-ttu-id="b67a3-104">Esta sección contiene información general sobre los pasos necesarios para preparar el entorno para que pueda usar todas las características de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b67a3-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="b67a3-105">Prepare una cuenta de dispositivo para cada Salas de Microsoft Teams consola.</span><span class="sxs-lookup"><span data-stu-id="b67a3-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="b67a3-106">Vea [Implementar Salas de Microsoft Teams](rooms-deploy.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b67a3-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="b67a3-107">Asegúrese de que las conexiones de red y de Internet funcionen correctamente en el dispositivo que se va a utilizar. </span><span class="sxs-lookup"><span data-stu-id="b67a3-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="b67a3-108">Debe poder recibir una dirección IP mediante DHCP.</span><span class="sxs-lookup"><span data-stu-id="b67a3-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="b67a3-109">(Salas de Microsoft Teams se puede configurar con una dirección IP estática en el primer inicio de la unidad, pero después, una dirección IP estática para el dispositivo podría configurarse en el dispositivo o en el conmutador ascendente o enrutador).</span><span class="sxs-lookup"><span data-stu-id="b67a3-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="b67a3-110">Debe tener estos puertos abiertos (además de abrir los puertos normales para medios):</span><span class="sxs-lookup"><span data-stu-id="b67a3-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="b67a3-111">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="b67a3-111">HTTPS: 443</span></span>
   - <span data-ttu-id="b67a3-112">HTTP: 80</span><span class="sxs-lookup"><span data-stu-id="b67a3-112">HTTP: 80</span></span>

   <span data-ttu-id="b67a3-113">Si su red se ejecuta mediante un proxy, necesitará también la dirección del proxy o la información de script.</span><span class="sxs-lookup"><span data-stu-id="b67a3-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="b67a3-114">Salas de Microsoft Teams no admite la autenticación de proxy, ya que puede interferir con las operaciones regulares de la sala.</span><span class="sxs-lookup"><span data-stu-id="b67a3-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="b67a3-115">Asegúrese de que Salas de Microsoft Teams de autenticación de proxy antes de entrar en producción.</span><span class="sxs-lookup"><span data-stu-id="b67a3-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="b67a3-116">Para poder mejorar su experiencia, Microsoft recopila información.</span><span class="sxs-lookup"><span data-stu-id="b67a3-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="b67a3-117">Para permitir que Microsoft recopile datos, permita que estos sitios:</span><span class="sxs-lookup"><span data-stu-id="b67a3-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="b67a3-118">Punto de conexión de cliente de telemetría: https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="b67a3-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="b67a3-119">Punto de conexión de configuración de telemetría: https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="b67a3-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="b67a3-120">Crear y probar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b67a3-120">Create and test a device account</span></span>

<span data-ttu-id="b67a3-121">Una *cuenta de dispositivo* es una cuenta que el cliente Salas de Microsoft Teams usa para obtener acceso a características desde Exchange, como el calendario, y para habilitar Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b67a3-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="b67a3-122">Vea [Implementar Salas de Microsoft Teams](rooms-deploy.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b67a3-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="b67a3-123">Comprobar la disponibilidad de red</span><span class="sxs-lookup"><span data-stu-id="b67a3-123">Check network availability</span></span>

<span data-ttu-id="b67a3-124">Para funcionar correctamente, el Salas de Microsoft Teams dispositivo debe tener acceso a una red cableada que cumpla estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="b67a3-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="b67a3-125">Tener acceso a su instancia de Active Directory o Azure Active Directory (Azure AD), así como a sus servidores de Microsoft Exchange y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b67a3-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="b67a3-126">Tener acceso a un servidor que pueda proporcionar una dirección IP mediante DHCP.</span><span class="sxs-lookup"><span data-stu-id="b67a3-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="b67a3-127">Salas de Microsoft Teams se puede configurar con una dirección IP estática en el primer inicio de la unidad.</span><span class="sxs-lookup"><span data-stu-id="b67a3-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="b67a3-128">Tener acceso a los puertos HTTP 80 y 443.</span><span class="sxs-lookup"><span data-stu-id="b67a3-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="b67a3-129">Puertos TCP y UDP [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) configurados como se describe en Requisitos de puerto y protocolo para servidores para implementaciones de Skype Empresarial Server locales o direcciones URL e [intervalos](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) de direcciones IP de Microsoft 365 y Office 365 para implementaciones en línea de Microsoft Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b67a3-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b67a3-130">Asegúrese de usar una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria. </span><span class="sxs-lookup"><span data-stu-id="b67a3-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="b67a3-131">Las actualizaciones de software Salas de Microsoft Teams se descargan automáticamente desde el Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="b67a3-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="b67a3-132">Consulte [Requisitos previos para Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business) y Educación para comprobar que la consola del salón podrá acceder a la tienda y a la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="b67a3-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="b67a3-133">Certificados</span><span class="sxs-lookup"><span data-stu-id="b67a3-133">Certificates</span></span>

<span data-ttu-id="b67a3-134">El Salas de Microsoft Teams usa certificados para Exchange Web Services, Microsoft Teams o Skype Empresarial, uso de red y autenticación.</span><span class="sxs-lookup"><span data-stu-id="b67a3-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="b67a3-135">En el caso de que los servidores relacionados utilicen certificados públicos, como ocurre con las implementaciones en línea y algunas locales, no será necesario que el administrador realice ninguna otra acción en relación a la instalación de certificados.</span><span class="sxs-lookup"><span data-stu-id="b67a3-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="b67a3-136">Si, por el contrario, la entidad de certificación es una CA privada (habitual en las instalaciones locales), el dispositivo necesita poder confiar en esa CA, lo que implica tener los certificados de la cadena CA + CA instalados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b67a3-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="b67a3-137">Al añadir el dispositivo al dominio, esta tarea se realiza de forma automática.</span><span class="sxs-lookup"><span data-stu-id="b67a3-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="b67a3-138">Los certificados se instalarán del mismo modo en que se instalarían para cualquier otro cliente de Windows. </span><span class="sxs-lookup"><span data-stu-id="b67a3-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b67a3-139">Es posible que se requieran certificados para Salas de Microsoft Teams usar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b67a3-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="b67a3-140">Proxy</span><span class="sxs-lookup"><span data-stu-id="b67a3-140">Proxy</span></span>

<span data-ttu-id="b67a3-141">Salas de Microsoft Teams está diseñado para heredar la configuración de proxy del Windows sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b67a3-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="b67a3-142">Acceda al SO Windows de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b67a3-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="b67a3-143">En la interfaz Salas de Microsoft Teams usuario, haga clic en el icono de engranaje de Configuración donde se le pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es **sfb).**</span><span class="sxs-lookup"><span data-stu-id="b67a3-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="b67a3-144">Pulse en **Configuración** seguido de pulsar en el botón Ir a  Windows y, a continuación,  pulse en el botón Ir a Inicio de sesión de administrador y, a continuación, haga clic en el botón Administrador (si el equipo está unido al dominio, elija Otro usuario **y, a** **continuación,** use .\admin como nombre de usuario).</span><span class="sxs-lookup"><span data-stu-id="b67a3-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="b67a3-145">En el **cuadro Windows** cuadro De búsqueda en la parte inferior izquierda de regedit (presione la pantalla larga o haga clic con el botón derecho y elija Ejecutar **como administrador).**</span><span class="sxs-lookup"><span data-stu-id="b67a3-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="b67a3-146">Haga clic en la carpeta HKEY_USERS (podrá ver una lista de identificadores de seguridad de los usuarios de la máquina), asegúrese de que la carpeta raíz HKEY_USERS esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b67a3-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="b67a3-147">Haga clic en Archivo y, a continuación, **elija Cargar subárbol.**</span><span class="sxs-lookup"><span data-stu-id="b67a3-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="b67a3-148">Vaya a la **carpeta C:\Usuarios\Skype** y escriba en el cuadro Nombre de archivo NTUSER.dat y presione el botón Abrir</span><span class="sxs-lookup"><span data-stu-id="b67a3-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="b67a3-149">Se le pedirá un nombre de clave para el subárbol recién cargado; escriba en Skype (ahora debería ver la configuración del Registro para el Skype usuario).</span><span class="sxs-lookup"><span data-stu-id="b67a3-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="b67a3-150">Abra la Skype y busque HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings asegúrese de que se introducen estas opciones:</span><span class="sxs-lookup"><span data-stu-id="b67a3-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="b67a3-151">Si ProxyServer no existe, es posible que deba agregar esta clave como una cadena, cambie xx.xx.xx.xx:8080 a la dirección IP/host y al puerto de su servidor Proxy.</span><span class="sxs-lookup"><span data-stu-id="b67a3-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="b67a3-152">Si el cliente usa un archivo PAC, la configuración tendría el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b67a3-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="b67a3-153">Cuando haya terminado de hacer los cambios, resalte la clave de usuario de Skype (carpeta raíz de Skype) y elija Descargar subárbol del menú Archivo del registro (se le solicitará confirmación, elija **Sí**).</span><span class="sxs-lookup"><span data-stu-id="b67a3-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="b67a3-154">Ahora puede cerrar el editor del registro y escribir cerrar la sesión en el cuadro de búsqueda de Windows.</span><span class="sxs-lookup"><span data-stu-id="b67a3-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="b67a3-155">Nuevamente en la pantalla de inicio de sesión, elija el usuario de **Skype**.</span><span class="sxs-lookup"><span data-stu-id="b67a3-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="b67a3-156">Si todos los pasos anteriores se completaron correctamente, el Salas de Microsoft Teams inicio de sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="b67a3-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="b67a3-157">Vea el [artículo Seguridad de](./security.md#network-security) red para obtener detalles completos sobre FQDN, puertos e intervalos de direcciones IP necesarios para Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b67a3-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="b67a3-158">Crear paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="b67a3-158">Create provisioning packages</span></span>

<span data-ttu-id="b67a3-159">Usará paquetes de aprovisionamiento para autenticarse Exchange Server, Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b67a3-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="b67a3-160">Administración del grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="b67a3-160">Admin group management</span></span>

<span data-ttu-id="b67a3-161">Después de la unión a un dominio, puede usar la Directiva de grupo o la Administración del equipo local para configurar un Grupo de seguridad como administrador local, tal como lo haría para un PC con Windows en su dominio.</span><span class="sxs-lookup"><span data-stu-id="b67a3-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="b67a3-162">Las personas que formen parte de ese grupo de seguridad podrán introducir sus credenciales y desbloquear Configuración.</span><span class="sxs-lookup"><span data-stu-id="b67a3-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b67a3-163">Si su dispositivo de Sala de Microsoft Teams pierde la confianza en el dominio (por ejemplo, si elimina Sala de Microsoft Teams del dominio tras haberse unido a él), no podrá autenticarse en el dispositivo ni abrir Configuración.</span><span class="sxs-lookup"><span data-stu-id="b67a3-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="b67a3-164">La solución alternativa es iniciar sesión con la cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="b67a3-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="b67a3-165">Cuentas locales</span><span class="sxs-lookup"><span data-stu-id="b67a3-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="b67a3-166">Salas de Microsoft Teams Cuenta de usuario local</span><span class="sxs-lookup"><span data-stu-id="b67a3-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="b67a3-167">Normalmente, la cuenta de dispositivo no requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="b67a3-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="b67a3-168">Es posible asignarle una, pero acarrea consecuencias, como que los usuarios se puedan quedar bloqueados fuera de la aplicación de consola cuando expire la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b67a3-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="b67a3-169">Por lo tanto, el administrador debe garantizar que la contraseña no esté configurada para que expire.</span><span class="sxs-lookup"><span data-stu-id="b67a3-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="b67a3-170">"Administrador": cuenta de administrador local</span><span class="sxs-lookup"><span data-stu-id="b67a3-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="b67a3-171">Salas de Microsoft Teams contraseña predeterminada se establece en "sfb".</span><span class="sxs-lookup"><span data-stu-id="b67a3-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="b67a3-172">La contraseña se puede cambiar localmente yendo Windows Configuración Ir a Windows o en el archivo AutoUnattend.xml (use el Administrador de imágenes del sistema de Windows de ADK para realizar el cambio en el archivo \> xml).</span><span class="sxs-lookup"><span data-stu-id="b67a3-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b67a3-173">Asegúrese de cambiar la Salas de Microsoft Teams contraseña lo antes posible.</span><span class="sxs-lookup"><span data-stu-id="b67a3-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="b67a3-174">Otra manera de administrar la contraseña de administrador local es configurar una directiva de grupo en la que los administradores de dominio se conviertan en administradores locales.</span><span class="sxs-lookup"><span data-stu-id="b67a3-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="b67a3-175">La contraseña del administrador local no se incluye como opción durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="b67a3-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="b67a3-176">Cuenta de equipo</span><span class="sxs-lookup"><span data-stu-id="b67a3-176">Machine Account</span></span>

<span data-ttu-id="b67a3-177">Al igual que Windows dispositivo, el nombre de la máquina se puede cambiar haciendo clic con el botón derecho en **Configuración** \> **Acerca de** cambiar el nombre del \> **equipo.**</span><span class="sxs-lookup"><span data-stu-id="b67a3-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="b67a3-178">Si desea cambiar el nombre del equipo después de unirse a un dominio, use Cambiar nombre **de** equipo , un comando de PowerShell, seguido del nuevo nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="b67a3-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b67a3-179">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b67a3-179">Related topics</span></span>

[<span data-ttu-id="b67a3-180">Plan Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b67a3-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="b67a3-181">Requisitos de las Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b67a3-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="b67a3-182">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b67a3-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="b67a3-183">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b67a3-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="b67a3-184">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b67a3-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="b67a3-185">Requisitos previos para Microsoft Store para Empresas educación</span><span class="sxs-lookup"><span data-stu-id="b67a3-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)