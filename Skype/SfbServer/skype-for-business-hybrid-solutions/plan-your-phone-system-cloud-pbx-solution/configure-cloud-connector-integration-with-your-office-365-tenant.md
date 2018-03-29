---
title: Configurar la integración de Cloud Connector con el inquilino de Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Aprenda a configurar la integración de la nube de conector con el inquilino de Office 365.
ms.openlocfilehash: c8e74353bc9b1201d8e4ff11f27a3542f24cb373
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="c9c67-103">Configurar la integración de Cloud Connector con el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="c9c67-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="c9c67-104">Aprenda a configurar la integración de la nube de conector con el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9c67-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="c9c67-105">Una vez completada la instalación de Skype Empresarial Cloud Connector Edition, lleve a cabo los pasos detallados en esta sección para configurar su implementación y conectarla con el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9c67-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="c9c67-106">Establecer la configuración del firewall</span><span class="sxs-lookup"><span data-stu-id="c9c67-106">Configure firewall settings</span></span>

<span data-ttu-id="c9c67-107">Configurar el firewall para la configuración del firewall interno y externo para la red perimetral abrir los puertos necesarios según se describe en los [puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en el [Plan de Skype para conector de nube Business Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="c9c67-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="c9c67-108">Configurar las puertas de enlace para la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="c9c67-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="c9c67-p101">Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o el FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.</span><span class="sxs-lookup"><span data-stu-id="c9c67-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="c9c67-112">Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c9c67-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="c9c67-113">Exporte la CA raíz del equipo de Active Directory de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c9c67-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="c9c67-114">Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="c9c67-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="c9c67-p102">Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c9c67-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="c9c67-117">Modificar la plantilla de servidor Web existente para permitir a los usuarios autenticados inscribir o crear una nueva plantilla de servidor Web para configurar otras propiedades y permiten a los usuarios autenticados para inscribirse.</span><span class="sxs-lookup"><span data-stu-id="c9c67-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="c9c67-118">Para obtener instrucciones detalladas, consulte [Plantillas de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9c67-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="c9c67-119">Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado.</span><span class="sxs-lookup"><span data-stu-id="c9c67-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="c9c67-120">Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave.</span><span class="sxs-lookup"><span data-stu-id="c9c67-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="c9c67-121">Para obtener instrucciones detalladas, vea [Solicitar un certificado](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9c67-121">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="c9c67-122">Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.</span><span class="sxs-lookup"><span data-stu-id="c9c67-122">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="c9c67-123">Actualizar el dominio del inquilino</span><span class="sxs-lookup"><span data-stu-id="c9c67-123">Update the domain for your tenant</span></span>

<span data-ttu-id="c9c67-124">Asegúrese de haber completado los pasos para actualizar el dominio en Office 365 y de tener la capacidad para agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="c9c67-124">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="c9c67-125">Para obtener más información acerca de cómo configurar tu dominio en Office 365, consulte [vídeo: configurar tu dominio en Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c9c67-125">For more information about how to set up your domain in Office 365, see [Video: Set up your domain in Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="c9c67-126">Agregar registros DNS en Office 365 desde el perímetro</span><span class="sxs-lookup"><span data-stu-id="c9c67-126">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="c9c67-127">Agregue los siguientes registros DNS a su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9c67-127">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="c9c67-128">Para obtener información acerca de cómo agregar registros DNS para los clientes de Office 365, consulte [Agregar o editar registros DNS personalizados en Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="c9c67-128">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="c9c67-129">Agregar un registro A de DNS para el acceso perimetral.</span><span class="sxs-lookup"><span data-stu-id="c9c67-129">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="c9c67-p107">Office 365 y los scripts de implementación crearán automáticamente registros SRV. Confirme que puede buscar los siguientes dos servicios SIP en el perímetro: _sip y _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="c9c67-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="c9c67-133">Configuración de la conectividad híbrida entre Cloud Connector Edition y Office 365</span><span class="sxs-lookup"><span data-stu-id="c9c67-133">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="c9c67-134">Para configurar la conectividad híbrida entre su Skype para la implementación del conector de nube Business Edition y los inquilinos de Office 365, ejecute el siguiente cmdlet en una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9c67-134">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="c9c67-135">Para aprender a establecer una sesión remota de PowerShell, vea: [Usar Windows PowerShell para administrar Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9c67-135">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="c9c67-136">El cmdlet establece los FQDN externos para el servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="c9c67-136">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="c9c67-137">En el primero de los comandos, el \<nombre completo externo borde de acceso\> debe ser el de la función de servidor perimetral de acceso SIP.</span><span class="sxs-lookup"><span data-stu-id="c9c67-137">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="c9c67-138">De forma predeterminada, éste debe ser ap.\<nombre de dominio\>.</span><span class="sxs-lookup"><span data-stu-id="c9c67-138">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="c9c67-139">El nombre completo externo de borde de acceso de destino del mismo nivel debe establecerse en un sitio PSTN que sólo se utilizará como reserva en caso de que un usuario no está asignado a un sitio de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9c67-139">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="c9c67-140">Para obtener más información, vea [implementar un único sitio en nube conector](deploy-a-single-site-in-cloud-connector.md) e [implementar varios sitios en el conector de la nube](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c9c67-140">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="c9c67-141">Configurar las puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="c9c67-141">Set up PSTN gateways</span></span>

<span data-ttu-id="c9c67-p111">Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o al FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.</span><span class="sxs-lookup"><span data-stu-id="c9c67-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="c9c67-145">Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c9c67-145">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="c9c67-146">Exporte la CA raíz del equipo de Active Directory de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c9c67-146">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="c9c67-147">Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="c9c67-147">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="c9c67-p112">Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c9c67-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="c9c67-150">Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban.</span><span class="sxs-lookup"><span data-stu-id="c9c67-150">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="c9c67-151">Para obtener instrucciones detalladas, consulte [Plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9c67-151">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="c9c67-152">Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado.</span><span class="sxs-lookup"><span data-stu-id="c9c67-152">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="c9c67-153">Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave.</span><span class="sxs-lookup"><span data-stu-id="c9c67-153">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="c9c67-154">Para obtener instrucciones detalladas, vea [Solicitar un certificado](https://technet.microsoft.com/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9c67-154">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="c9c67-155">Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.</span><span class="sxs-lookup"><span data-stu-id="c9c67-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="c9c67-156">Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente con los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="c9c67-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="c9c67-157">Configurar usuarios en Office 365</span><span class="sxs-lookup"><span data-stu-id="c9c67-157">Set up your users in Office 365</span></span>

<span data-ttu-id="c9c67-158">Inicie sesión en el portal de administración de Office 365, agregue los usuarios que estarán habilitados para servicios de voz en línea y asignar una licencia E5 o sistema de teléfono en el complemento de Office 365 a la licencia de E3 a estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="c9c67-158">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="c9c67-159">Para obtener información sobre cómo agregar usuarios, consulte [Adición de usuarios a Office 365 para el negocio](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="c9c67-159">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="c9c67-160">Permitir a los usuarios para el sistema de teléfono de servicios de voz y correo de voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="c9c67-160">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="c9c67-161">Después de agregar los usuarios a Office 365, habilitar sus cuentas para el sistema de teléfono de servicios de voz de Office 365, incluido el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="c9c67-161">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="c9c67-162">Para habilitar estas funcionalidades, debe iniciar sesión en el inquilino de Office 365 con una cuenta que sea del rol de administrador global de Office 365 y debe poder ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="c9c67-162">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="c9c67-163">Para aprender a establecer una sesión remota de PowerShell, vea: [Usar Windows PowerShell para administrar Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c9c67-163">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="c9c67-164">Asignar la directiva al usuario y configure voz número de teléfono profesional el usuario, que se especifica con el valor del parámetro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="c9c67-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="c9c67-165">También puede especificar la identidad de un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Guillermo Rodarte"). </span><span class="sxs-lookup"><span data-stu-id="c9c67-165">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="c9c67-166">Después puede comprobar si se agregaron los usuarios y si se los habilitó con el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="c9c67-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="c9c67-p117">Tendrá que decidir si los usuarios deberán tener la capacidad de realizar llamadas internacionales, lo que está habilitado de manera predeterminada. Puede habilitar o deshabilitar el marcado internacional para los usuarios con el centro de administración en línea de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c9c67-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="c9c67-170">Para deshabilitar las llamadas internacionales para cada usuario en particular, ejecute el siguiente cmdlet en el PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="c9c67-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="c9c67-171">Para volver a habilitar internacional de una llamada a cada usuario una vez que se ha deshabilitado, ejecute el cmdlet de la mismo, pero cambie el valor de **PolicyName** a *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="c9c67-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="c9c67-172">Asignar usuarios a sitios de RTC</span><span class="sxs-lookup"><span data-stu-id="c9c67-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="c9c67-173">Use el PowerShell remoto del inquilino para asignar un sitio a los usuarios, aunque haya implementado solo un único sitio.</span><span class="sxs-lookup"><span data-stu-id="c9c67-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="c9c67-174">Para aprender a establecer una sesión remota de PowerShell, vea: [Usar Windows PowerShell para administrar Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9c67-174">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="c9c67-175">Si no se asigna ningún sitio de RTC a un usuario, la conectividad híbrida entre la implementación de Skype Empresarial Cloud Connector Edition y el inquilino de Office 365 volverá a usar el valor predeterminado uno del nivel del inquilino (Peer Destination) para que puedan completarse las llamadas.</span><span class="sxs-lookup"><span data-stu-id="c9c67-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="c9c67-176">Configuración de las opciones del servidor de mediación híbrido en línea</span><span class="sxs-lookup"><span data-stu-id="c9c67-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="c9c67-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="c9c67-177"></span></span>

<span data-ttu-id="c9c67-178">Cuando una llamada P2P se remite a una conferencia de RTC, el Skype para los negocios en línea conferencing server enviará una invitación para el servidor de mediación de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="c9c67-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="c9c67-179">Para asegurarse de que Office 365 puede enrutar correctamente esta invitación, necesitará configurar una opción en el arrendatario en línea para cada servidor de mediación de conector de nube como sigue:</span><span class="sxs-lookup"><span data-stu-id="c9c67-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="c9c67-180">Cree un usuario en el portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9c67-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="c9c67-181">Utilizar cualquier nombre de usuario que desee, como "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="c9c67-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="c9c67-182">Utilice el dominio SIP predeterminado del conector de la nube (el primer dominio SIP en el archivo .ini) como el dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="c9c67-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="c9c67-p121">No asigne ninguna licencia de Office 365 (como E5) a la cuenta que cree. Espere a que la sincronización de AD de Office 365 se complete.</span><span class="sxs-lookup"><span data-stu-id="c9c67-p121">Do not assign any Office 365 licenses (such as E5) to the account you create. Wait for Office 365 AD sync to complete.</span></span>
    
2. <span data-ttu-id="c9c67-185">Iniciar una sesión de PowerShell remota de inquilinos utilizando sus credenciales de administrador de inquilinos y ejecute el siguiente cmdlet para configurar el servidor de mediación y el FQDN del servidor de borde para que el usuario de cuenta, reemplazar \<DisplayName\> con el nombre para mostrar del usuario para el cuenta creada:</span><span class="sxs-lookup"><span data-stu-id="c9c67-185">Start a tenant remote PowerShell session using your tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created:</span></span>
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    <span data-ttu-id="c9c67-186">Para Identity, use el nombre para mostrar de la cuenta de usuario de Office 365 que haya creado para este servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c9c67-186">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="c9c67-187">Para *MediationServerFQDN* , utilice el FQDN interno definido para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c9c67-187">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="c9c67-188">Para *EdgeServerExternalFQDN* , utilice el nombre completo externo definido para el servidor Proxy de acceso del servidor de borde.</span><span class="sxs-lookup"><span data-stu-id="c9c67-188">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="c9c67-189">Si existen varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso de servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c9c67-189">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
3. <span data-ttu-id="c9c67-190">Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="c9c67-190">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

