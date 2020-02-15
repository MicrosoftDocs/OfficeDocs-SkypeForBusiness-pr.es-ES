---
title: Configurar la integración de Cloud Connector con el inquilino de Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Obtenga información sobre cómo configurar la integración de Cloud Connector con su inquilino de Office 365.
ms.openlocfilehash: cf683743064ec377c827fe0c52a59e464f65ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050212"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="39ff9-103">Configurar la integración de Cloud Connector con el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="39ff9-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="39ff9-104">Obtenga información sobre cómo configurar la integración de Cloud Connector con su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="39ff9-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="39ff9-105">Una vez completada la instalación de Skype empresarial Cloud Connector Edition, realice los pasos de esta sección para configurar su implementación y conectarla con el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="39ff9-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="39ff9-106">Configurar las opciones del firewall</span><span class="sxs-lookup"><span data-stu-id="39ff9-106">Configure firewall settings</span></span>

<span data-ttu-id="39ff9-107">Configure las opciones de Firewall para la configuración del firewall interno y externo de la red perimetral para abrir los puertos necesarios, tal y como se describe en [puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="39ff9-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="39ff9-108">Configurar puertas de enlace de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="39ff9-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="39ff9-109">Configure los troncos en cada puerta de enlace RTC para que apunten a los servidores de mediación de todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="39ff9-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="39ff9-110">Debido a que el FQDN del grupo de servidores es el mismo para todos los servidores del grupo, cada tronco debe apuntar a un FQDN o dirección IP del servidor de mediación en lugar del FQDN del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="39ff9-111">Los troncos deben configurarse con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="39ff9-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="39ff9-112">Si usa TLS entre los servidores de mediación y las puertas de enlace, tendrá que configurar las puertas de enlace y los servidores de mediación para que admitan MTLS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ff9-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="39ff9-113">Exporte la CA raíz del equipo de Active Directory de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="39ff9-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="39ff9-114">Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la entidad de certificación raíz.</span><span class="sxs-lookup"><span data-stu-id="39ff9-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="39ff9-115">Importe el certificado de CA raíz del certificado emitido a la puerta de enlace en los servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="39ff9-116">Si necesita obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se ejecuta en el equipo de Active Directory de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ff9-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="39ff9-117">Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban.</span><span class="sxs-lookup"><span data-stu-id="39ff9-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="39ff9-118">Para obtener instrucciones detalladas, consulte [plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="39ff9-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="39ff9-119">Solicite un certificado con el complemento de certificado seleccionando la plantilla de servidor Web que ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="39ff9-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="39ff9-120">Asegúrese de agregar un nombre común en asunto y nombre DNS en nombre alternativo con FQDN de la puerta de enlace y confirme que la clave privada que hace que la clave privada sea exportable está seleccionada en opciones de clave.</span><span class="sxs-lookup"><span data-stu-id="39ff9-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="39ff9-121">Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importar el certificado.</span><span class="sxs-lookup"><span data-stu-id="39ff9-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="39ff9-122">Actualizar el dominio de su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="39ff9-122">Update the domain for your tenant</span></span>

<span data-ttu-id="39ff9-123">Asegúrese de que ha completado los pasos para actualizar el dominio en Office 365 y tiene la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="39ff9-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="39ff9-124">Para obtener más información acerca de cómo configurar su dominio en Office 365, consulte [Agregar un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="39ff9-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="39ff9-125">Agregar registros DNS en Office 365 para su perímetro</span><span class="sxs-lookup"><span data-stu-id="39ff9-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="39ff9-126">Agregue los siguientes registros DNS a su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="39ff9-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="39ff9-127">Para obtener información sobre cómo agregar registros DNS a su inquilino de Office 365, vea [Agregar o editar registros DNS personalizados en office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="39ff9-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="39ff9-128">Agregar un registro A de DNS para el servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="39ff9-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="39ff9-129">Los registros SRV se crearán automáticamente con Office 365 y los scripts de implementación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="39ff9-130">Confirme que puede buscar los siguientes dos servicios SIP en el servidor perimetral: _sip y _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="39ff9-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="39ff9-132">Configurar la conectividad híbrida entre la edición de Cloud Connector Edition y Office 365</span><span class="sxs-lookup"><span data-stu-id="39ff9-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="39ff9-133">Para configurar la conectividad híbrida entre su implementación de Skype empresarial Cloud Connector Edition y su inquilino de Office 365, ejecute el siguiente cmdlet en una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39ff9-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="39ff9-134">Para obtener información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="39ff9-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="39ff9-135">El cmdlet establece el FQDN externo del servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="39ff9-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="39ff9-136">En el primero de los comandos, el \<FQDN\> del servidor perimetral de acceso externo debe ser el del rol perimetral de acceso SIP.</span><span class="sxs-lookup"><span data-stu-id="39ff9-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="39ff9-137">De forma predeterminada, debe ser el nombre\<\>del dominio AP.</span><span class="sxs-lookup"><span data-stu-id="39ff9-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="39ff9-138">El FQDN del servidor perimetral de acceso externo usado para el destino del mismo nivel debe establecerse en un sitio RTC que solo se usará como reserva en caso de que un usuario no esté asignado a un sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="39ff9-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="39ff9-139">Para obtener más información, vea [deploy a Single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [deploy Multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="39ff9-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="39ff9-140">Configurar puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="39ff9-140">Set up PSTN gateways</span></span>

<span data-ttu-id="39ff9-141">Configure los troncos en cada puerta de enlace RTC para que apunten a los servidores de mediación de todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="39ff9-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="39ff9-142">Cada tronco debe apuntar a un FQDN o dirección IP del servidor de mediación en lugar del FQDN del grupo de servidores de mediación porque el FQDN del grupo de servidores es el mismo para todos los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="39ff9-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="39ff9-143">Los troncos deben configurarse con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="39ff9-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="39ff9-144">Si usa TLS entre los servidores de mediación y las puertas de enlace, tendrá que configurar las puertas de enlace y los servidores de mediación para que admitan MTLS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ff9-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="39ff9-145">Exporte la CA raíz del equipo de Active Directory de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="39ff9-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="39ff9-146">Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la entidad de certificación raíz.</span><span class="sxs-lookup"><span data-stu-id="39ff9-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="39ff9-147">Importe el certificado de CA raíz del certificado emitido a la puerta de enlace en los servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="39ff9-148">Si necesita obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se ejecuta en el equipo de Active Directory de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ff9-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="39ff9-149">Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban.</span><span class="sxs-lookup"><span data-stu-id="39ff9-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="39ff9-150">Para obtener instrucciones detalladas, consulte [plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="39ff9-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="39ff9-151">Solicite un certificado con el complemento de certificado seleccionando la plantilla de servidor Web que ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="39ff9-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="39ff9-152">Asegúrese de agregar un nombre común en asunto y nombre DNS en nombre alternativo con FQDN de la puerta de enlace y confirme que la clave privada que hace que la clave privada sea exportable está seleccionada en opciones de clave.</span><span class="sxs-lookup"><span data-stu-id="39ff9-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="39ff9-153">Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importar el certificado.</span><span class="sxs-lookup"><span data-stu-id="39ff9-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="39ff9-154">Las puertas de enlace RTC en un sitio RTC solo deben conectarse a los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="39ff9-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="39ff9-155">Configurar los usuarios en Office 365</span><span class="sxs-lookup"><span data-stu-id="39ff9-155">Set up your users in Office 365</span></span>

<span data-ttu-id="39ff9-156">Inicie sesión en el portal de administración de Office 365, agregue los usuarios que se habilitarán para los servicios de voz en línea y asigne una licencia o sistema telefónico de E5 en el complemento de Office 365 a la licencia E3 para estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="39ff9-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="39ff9-157">Para obtener información acerca de cómo agregar usuarios, consulte [Agregar usuarios a Office 365 para empresas](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="39ff9-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="39ff9-158">Habilitar a los usuarios para sistema telefónico en los servicios de voz y voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="39ff9-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="39ff9-159">Después de agregar los usuarios a Office 365, habilite sus cuentas para el sistema telefónico en los servicios de voz de Office 365, incluido el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="39ff9-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="39ff9-160">Para habilitar estas funciones, debe iniciar sesión en el inquilino de Office 365 con una cuenta de un rol de administrador global de Office 365 y poder ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="39ff9-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="39ff9-161">Para obtener información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39ff9-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="39ff9-162">Asigne la Directiva a su usuario y configure el número de teléfono de voz empresarial del usuario, que se especifica con el valor del parámetro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="39ff9-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="39ff9-163">Se puede especificar una identidad de usuario con la dirección SIP del usuario, el nombre principal del usuario (UPN) o el nombre para mostrar de Active Directory del usuario (por ejemplo, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="39ff9-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="39ff9-164">El carácter asterisco\*() también puede usarse con el nombre para mostrar como identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="39ff9-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="39ff9-165">Por ejemplo, la identidad "\*Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".</span><span class="sxs-lookup"><span data-stu-id="39ff9-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="39ff9-166">A continuación, puede comprobar que los usuarios se han agregado y habilitado mediante el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="39ff9-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="39ff9-167">Deberá decidir si los usuarios deben poder realizar llamadas internacionales.</span><span class="sxs-lookup"><span data-stu-id="39ff9-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="39ff9-168">De forma predeterminada, la llamada internacional está habilitada.</span><span class="sxs-lookup"><span data-stu-id="39ff9-168">By default, international calling is enabled.</span></span> <span data-ttu-id="39ff9-169">Puede deshabilitar o habilitar a los usuarios para el marcado internacional mediante el centro de administración de Skype empresarial en línea.</span><span class="sxs-lookup"><span data-stu-id="39ff9-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="39ff9-170">Para deshabilitar las llamadas internacionales en función de cada usuario, ejecute el siguiente cmdlet en PowerShell de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="39ff9-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="39ff9-171">Para volver a habilitar las llamadas internacionales en función de cada usuario después de que se haya deshabilitado, ejecute el mismo cmdlet, pero cambie el valor de **PolicyName** a *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="39ff9-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="39ff9-172">Asignar usuarios a sitios RTC</span><span class="sxs-lookup"><span data-stu-id="39ff9-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="39ff9-173">Use el PowerShell remoto del inquilino para asignar un sitio a los usuarios, incluso si solo implementó un sitio único.</span><span class="sxs-lookup"><span data-stu-id="39ff9-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="39ff9-174">Para obtener información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="39ff9-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="39ff9-175">Si no se ha asignado ningún sitio RTC a un usuario, la conectividad híbrida entre su implementación de Skype empresarial Cloud Connector Edition y el inquilino de Office 365 se revertirá para usar el valor predeterminado del nivel de inquilino (destino del mismo nivel) para que las llamadas se puedan completar.</span><span class="sxs-lookup"><span data-stu-id="39ff9-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="39ff9-176">Configurar las opciones del servidor de mediación híbrida en línea</span><span class="sxs-lookup"><span data-stu-id="39ff9-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="39ff9-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="39ff9-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="39ff9-178">Cuando se escala una llamada P2P a una conferencia RTC, el servidor de conferencia de Skype empresarial online enviará una invitación al servidor de mediación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="39ff9-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="39ff9-179">Para asegurarse de que Office 365 puede redirigir esta invitación correctamente, debe configurar una opción de configuración en su inquilino en línea para cada servidor de mediación de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ff9-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="39ff9-180">Cree un usuario en el portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="39ff9-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="39ff9-181">Use el nombre de usuario que desee, como "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="39ff9-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="39ff9-182">Use el dominio SIP predeterminado de Cloud Connector (el primer dominio SIP del archivo. ini) como dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="39ff9-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="39ff9-183">Tenga en cuenta que la asignación de licencias solo es necesaria para la propagación del usuario en el directorio de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="39ff9-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="39ff9-184">Asigne una licencia de Office 365 (como E5) a la cuenta que cree, deje hasta una hora para que los cambios se propaguen, compruebe que las cuentas de usuario se hayan aprovisionado correctamente en el directorio de Skype empresarial online ejecutando el siguiente cmdlet y, a continuación, quite el licencia de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="39ff9-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="39ff9-185">Inicie una sesión de PowerShell remoto de Azure AD de inquilino con sus credenciales de administrador global o de usuario y, a continuación, ejecute el siguiente cmdlet para establecer el Departamento de la cuenta de usuario de Azure AD configurada en el paso 1 en "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="39ff9-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="39ff9-186">Inicie una sesión de PowerShell remoto de Skype empresarial de inquilino con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para establecer el servidor de mediación \<y\> el FQDN del servidor perimetral en esa cuenta de usuario, reemplazando DisplayName por el nombre para mostrar del usuario para la cuenta que creó en el paso 1:</span><span class="sxs-lookup"><span data-stu-id="39ff9-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="39ff9-187">Para identidad, use el nombre para mostrar de la cuenta de usuario de Office 365 que ha creado para este servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="39ff9-188">Para *MediationServerFQDN* , use el FQDN interno definido para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="39ff9-189">Para *EdgeServerExternalFQDN* , use el FQDN externo definido para el proxy de acceso del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="39ff9-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="39ff9-190">Si hay varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso del servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="39ff9-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="39ff9-191">Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="39ff9-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

