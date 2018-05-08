---
title: Configurar la integración de Cloud Connector con el inquilino de Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Obtenga información sobre cómo configurar la integración de conector en la nube con el inquilino de Office 365.
ms.openlocfilehash: 62caf2cd70b16f0a8e85a38b381478d49e4ee37c
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="206cc-103">Configurar la integración de Cloud Connector con el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="206cc-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="206cc-104">Obtenga información sobre cómo configurar la integración de conector en la nube con el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="206cc-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="206cc-105">Una vez completada la instalación de Skype Empresarial Cloud Connector Edition, lleve a cabo los pasos detallados en esta sección para configurar su implementación y conectarla con el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="206cc-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="206cc-106">Establecer la configuración del firewall</span><span class="sxs-lookup"><span data-stu-id="206cc-106">Configure firewall settings</span></span>

<span data-ttu-id="206cc-107">Configurar el firewall para la configuración del firewall interno y externo para la red perimetral abrir los puertos requeridos, tal como se describe en [los puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="206cc-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="206cc-108">Configurar las puertas de enlace para la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="206cc-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="206cc-p101">Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o el FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.</span><span class="sxs-lookup"><span data-stu-id="206cc-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="206cc-112">Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="206cc-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="206cc-113">Exporte la CA raíz del equipo de Active Directory de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="206cc-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="206cc-114">Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="206cc-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="206cc-p102">Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="206cc-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="206cc-117">Modificar la plantilla de servidor Web existente para permitir a los usuarios autenticados inscribirse o crear una nueva plantilla de servidor Web para configurar otras propiedades y permiten a los usuarios autenticados inscribirse.</span><span class="sxs-lookup"><span data-stu-id="206cc-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="206cc-118">Para obtener instrucciones detalladas, consulte [Plantillas de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="206cc-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="206cc-119">Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado.</span><span class="sxs-lookup"><span data-stu-id="206cc-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="206cc-120">Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave.</span><span class="sxs-lookup"><span data-stu-id="206cc-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="206cc-121">Para obtener instrucciones detalladas, vea [Solicitar un certificado](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="206cc-121">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="206cc-122">Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.</span><span class="sxs-lookup"><span data-stu-id="206cc-122">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="206cc-123">Actualizar el dominio del inquilino</span><span class="sxs-lookup"><span data-stu-id="206cc-123">Update the domain for your tenant</span></span>

<span data-ttu-id="206cc-124">Asegúrese de haber completado los pasos para actualizar el dominio en Office 365 y de tener la capacidad para agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="206cc-124">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="206cc-125">Para obtener más información acerca de cómo configurar el dominio en Office 365, vea [vídeo: configurar el dominio en Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="206cc-125">For more information about how to set up your domain in Office 365, see [Video: Set up your domain in Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="206cc-126">Agregar registros DNS en Office 365 desde el perímetro</span><span class="sxs-lookup"><span data-stu-id="206cc-126">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="206cc-127">Agregue los siguientes registros DNS a su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="206cc-127">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="206cc-128">Para obtener información acerca de cómo agregar registros DNS en su inquilino de Office 365, vea [Agregar o editar registros DNS personalizados en Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="206cc-128">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="206cc-129">Agregar un registro A de DNS para el acceso perimetral.</span><span class="sxs-lookup"><span data-stu-id="206cc-129">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="206cc-p107">Office 365 y los scripts de implementación crearán automáticamente registros SRV. Confirme que puede buscar los siguientes dos servicios SIP en el perímetro: _sip y _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="206cc-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="206cc-133">Configuración de la conectividad híbrida entre Cloud Connector Edition y Office 365</span><span class="sxs-lookup"><span data-stu-id="206cc-133">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="206cc-134">Para configurar la conectividad híbrida entre su Skype para la implementación de Business Edition de conector en la nube y el inquilino de Office 365, ejecute el siguiente cmdlet en una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="206cc-134">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="206cc-135">Para obtener información sobre cómo establecer una sesión remota de PowerShell, vea: [Uso de Windows PowerShell para administrar Skype para profesionales en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="206cc-135">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="206cc-136">El cmdlet establece los FQDN externos para el servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="206cc-136">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="206cc-137">En el primero de los comandos, el \<FQDN perimetral de acceso externo\> debe ser el uno para el rol de servidor perimetral de acceso SIP.</span><span class="sxs-lookup"><span data-stu-id="206cc-137">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="206cc-138">De forma predeterminada, debe ser ap.\<nombre de dominio\>.</span><span class="sxs-lookup"><span data-stu-id="206cc-138">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="206cc-139">El FQDN externo de perimetral de acceso de destino del mismo nivel debe establecerse en un sitio de RTC que solo se usará como reserva en caso de que un usuario no está asignado a un sitio de RTC.</span><span class="sxs-lookup"><span data-stu-id="206cc-139">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="206cc-140">Para obtener más información, vea [implementar un sitio de conector en la nube](deploy-a-single-site-in-cloud-connector.md) e [implementar varios sitios de conector en la nube](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="206cc-140">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="206cc-141">Configurar las puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="206cc-141">Set up PSTN gateways</span></span>

<span data-ttu-id="206cc-p111">Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o al FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.</span><span class="sxs-lookup"><span data-stu-id="206cc-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="206cc-145">Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="206cc-145">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="206cc-146">Exporte la CA raíz del equipo de Active Directory de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="206cc-146">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="206cc-147">Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="206cc-147">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="206cc-p112">Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="206cc-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="206cc-150">Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban.</span><span class="sxs-lookup"><span data-stu-id="206cc-150">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="206cc-151">Para obtener instrucciones detalladas, consulte [Plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="206cc-151">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="206cc-152">Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado.</span><span class="sxs-lookup"><span data-stu-id="206cc-152">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="206cc-153">Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave.</span><span class="sxs-lookup"><span data-stu-id="206cc-153">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="206cc-154">Para obtener instrucciones detalladas, vea [Solicitar un certificado](https://technet.microsoft.com/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="206cc-154">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="206cc-155">Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.</span><span class="sxs-lookup"><span data-stu-id="206cc-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="206cc-156">Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente con los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="206cc-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="206cc-157">Configurar usuarios en Office 365</span><span class="sxs-lookup"><span data-stu-id="206cc-157">Set up your users in Office 365</span></span>

<span data-ttu-id="206cc-158">Inicie sesión en el portal de administración de Office 365, agregue los usuarios que va a estar habilitados para los servicios de voz en línea y asignación una licencia E5 o un sistema de teléfono en el complemento de Office 365 a la licencia E3 a estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="206cc-158">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="206cc-159">Para obtener información acerca de cómo agregar usuarios, vea [Agregar usuarios a Office 365 para la empresa](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="206cc-159">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="206cc-160">Permitir a los usuarios para el sistema telefónico en servicios de voz y correo de voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="206cc-160">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="206cc-161">Después de agregar los usuarios a Office 365, habilitar sus cuentas para el sistema telefónico en servicios de voz de Office 365, incluido el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="206cc-161">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="206cc-162">Para habilitar estas funcionalidades, debe iniciar sesión en el inquilino de Office 365 con una cuenta que sea del rol de administrador global de Office 365 y debe poder ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="206cc-162">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="206cc-163">Para obtener información sobre cómo establecer una sesión remota de PowerShell, vea: [Uso de Windows PowerShell para administrar Skype para profesionales en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="206cc-163">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="206cc-164">Asigne la directiva para el usuario y configuración voz número de teléfono profesional del usuario, que se especifica con el valor del parámetro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="206cc-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="206cc-165">También puede especificar la identidad de un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Guillermo Rodarte"). </span><span class="sxs-lookup"><span data-stu-id="206cc-165">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="206cc-166">Después puede comprobar si se agregaron los usuarios y si se los habilitó con el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="206cc-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="206cc-p117">Tendrá que decidir si los usuarios deberán tener la capacidad de realizar llamadas internacionales, lo que está habilitado de manera predeterminada. Puede habilitar o deshabilitar el marcado internacional para los usuarios con el centro de administración en línea de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="206cc-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="206cc-170">Para deshabilitar las llamadas internacionales para cada usuario en particular, ejecute el siguiente cmdlet en el PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="206cc-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="206cc-171">Para volver a habilitar internacional al llamar a cada usuario una vez se ha deshabilitado, ejecute el cmdlet de la misma, pero cambie el valor de **PolicyName** a *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="206cc-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="206cc-172">Asignar usuarios a sitios de RTC</span><span class="sxs-lookup"><span data-stu-id="206cc-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="206cc-173">Use el PowerShell remoto del inquilino para asignar un sitio a los usuarios, aunque haya implementado solo un único sitio.</span><span class="sxs-lookup"><span data-stu-id="206cc-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="206cc-174">Para obtener información sobre cómo establecer una sesión remota de PowerShell, vea: [Uso de Windows PowerShell para administrar Skype para profesionales en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="206cc-174">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="206cc-175">Si no se asigna ningún sitio de RTC a un usuario, la conectividad híbrida entre la implementación de Skype Empresarial Cloud Connector Edition y el inquilino de Office 365 volverá a usar el valor predeterminado uno del nivel del inquilino (Peer Destination) para que puedan completarse las llamadas.</span><span class="sxs-lookup"><span data-stu-id="206cc-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="206cc-176">Configuración de las opciones del servidor de mediación híbrido en línea</span><span class="sxs-lookup"><span data-stu-id="206cc-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="206cc-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="206cc-177"></span></span>

<span data-ttu-id="206cc-178">Cuando una llamada de P2P se remite a una conferencia de RTC, la Skype para servidor de conferencia en línea de negocio enviará una invitación al servidor de mediación de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="206cc-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="206cc-179">Para asegurarse de que Office 365 puede enrutar este invitar correctamente, debe configurar una opción de configuración en el inquilino en línea para cada servidor de mediación de conector en la nube de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="206cc-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="206cc-180">Cree un usuario en el portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="206cc-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="206cc-181">Usar los nombres de usuario que desee, como "MediationServer1."</span><span class="sxs-lookup"><span data-stu-id="206cc-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="206cc-182">Usar el dominio SIP predeterminado del conector en la nube (el primer dominio SIP en el archivo. ini) como el dominio de usuario.</span><span class="sxs-lookup"><span data-stu-id="206cc-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="206cc-p121">No asigne ninguna licencia de Office 365 (como E5) a la cuenta que cree. Espere a que la sincronización de AD de Office 365 se complete.</span><span class="sxs-lookup"><span data-stu-id="206cc-p121">Do not assign any Office 365 licenses (such as E5) to the account you create. Wait for Office 365 AD sync to complete.</span></span>
    
2. <span data-ttu-id="206cc-185">Iniciar una sesión de PowerShell remota de inquilino con sus credenciales de administrador de inquilinos y, a continuación, ejecute el siguiente cmdlet para establecer el servidor de mediación y el FQDN del servidor perimetral a ese usuario de cuenta, reemplazar \<DisplayName\> con el nombre para mostrar del usuario para el cuenta que ha creado:</span><span class="sxs-lookup"><span data-stu-id="206cc-185">Start a tenant remote PowerShell session using your tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created:</span></span>
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    <span data-ttu-id="206cc-186">Para Identity, use el nombre para mostrar de la cuenta de usuario de Office 365 que haya creado para este servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="206cc-186">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="206cc-187">Para *MediationServerFQDN* , use el FQDN interno definido para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="206cc-187">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="206cc-188">Para *EdgeServerExternalFQDN* , use el FQDN externo definido para el servidor Proxy de acceso de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="206cc-188">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="206cc-189">Si existen varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso de servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="206cc-189">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
3. <span data-ttu-id="206cc-190">Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="206cc-190">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

