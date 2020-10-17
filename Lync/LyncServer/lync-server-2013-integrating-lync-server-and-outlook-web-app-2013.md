---
title: 'Lync Server 2013: integración de Lync Server y Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f822afb4ba0f3dabfd133caf92a434eadac82fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534766"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="98e0d-102">Integración de Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="98e0d-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98e0d-103">_**Última modificación del tema:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="98e0d-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="98e0d-104">Además de integrarse con Microsoft Outlook 2013, Microsoft Lync Server 2013 puede integrarse completamente con Microsoft Outlook Web App 2013; entre otras cosas, esto agrega mensajería instantánea y presencia a Outlook Web App y permite que la lista de contactos unificada se comparta entre Outlook Web App y Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="98e0d-105">Para integrar Lync Server 2013 y Outlook Web App, primero debe comprobar que se ha instalado el tiempo de ejecución de la API administrada de comunicaciones unificadas 4,0 en el servidor back-end de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="98e0d-106">Puede hacerlo buscando si existe el siguiente valor del registro:</span><span class="sxs-lookup"><span data-stu-id="98e0d-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="98e0d-107">HKEY \_ local \_ Machine \\ System \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ InstantMessaging \\ ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="98e0d-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="98e0d-108">ImplementationDLLPath debe apuntar a la ubicación de la carpeta para el archivo Microsoft.Rtc.Internal.Ucweb.dll.</span><span class="sxs-lookup"><span data-stu-id="98e0d-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="98e0d-109">Si no es así, o si el valor del registro no existe, debe descargar e instalar el programa de instalación de la ejecución de UCMA desde el centro de descarga de Microsoft en <https://www.microsoft.com/download/details.aspx?id=34992> .</span><span class="sxs-lookup"><span data-stu-id="98e0d-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <https://www.microsoft.com/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="98e0d-110">Encontrará información sobre cómo instalar el tiempo de ejecución de UCMA en la misma página web.</span><span class="sxs-lookup"><span data-stu-id="98e0d-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="98e0d-111">**Compatibilidad con versiones anteriores**</span><span class="sxs-lookup"><span data-stu-id="98e0d-111">**Backward Compatibility**</span></span>

<span data-ttu-id="98e0d-112">Lync Server 2013 puede integrarse con las versiones de Microsoft Exchange Server 2010 de mensajería unificada y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="98e0d-113">Para obtener más información, vea el artículo Deploying on-premises Exchange UM to proporcionar Lync Server 2010 voice mail en [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) .</span><span class="sxs-lookup"><span data-stu-id="98e0d-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="98e0d-114">Si se integra con Exchange 2010, no tendrá características específicas de Lync Server, como el almacén de contactos unificado y el archivado de Lync a Exchange.</span><span class="sxs-lookup"><span data-stu-id="98e0d-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="98e0d-115">Microsoft Lync 2013 también se puede usar junto con Exchange 2010 y Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="98e0d-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="98e0d-116">De nuevo, sin embargo, las nuevas funciones, como el almacén de contactos unificado y las fotos de alta resolución, no estarán disponibles para los usuarios de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="98e0d-117">Estas nuevas funciones requieren tanto Lync Server 2013 como Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="98e0d-118">**Creación de un grupo de aplicaciones de confianza para Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="98e0d-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="98e0d-119">Si ha instalado el servicio de enrutador de llamadas de mensajería unificada de Microsoft Exchange y el servicio de mensajería unificada de Microsoft Exchange en el mismo equipo, no es necesario crear un grupo de aplicaciones de confianza para Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="98e0d-120">(Esto supone que el servidor en cuestión hospeda un plan de marcado de mensajería unificada de SipName). Si usa un solo equipo para hospedar ambos servicios, puede ir a la sección de este documento titulada habilitación de la **mensajería instantánea en Outlook Web App**.</span><span class="sxs-lookup"><span data-stu-id="98e0d-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="98e0d-121">Lync Server 2013 puede detectar automáticamente cualquier servidor de Exchange que hospede un plan de marcado de mensajería unificada de SipName; Estos servidores se agregan automáticamente a la lista de servidores conocidos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98e0d-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="98e0d-122">No es necesario crear un grupo de aplicaciones de confianza y agregar estos servidores a la lista de servidores conocidos.</span><span class="sxs-lookup"><span data-stu-id="98e0d-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="98e0d-123">De hecho, esto hará que la integración de Outlook Web App deje de funcionar.</span><span class="sxs-lookup"><span data-stu-id="98e0d-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98e0d-124">Esto se debe al hecho de que la topología de Lync Server ahora tendrá dos entradas para el mismo equipo: la entrada de detección automática y la entrada agregada manualmente.</span><span class="sxs-lookup"><span data-stu-id="98e0d-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="98e0d-125">Para solucionar el problema y volver a funcionar Outlook Web App, use Windows PowerShell para quitar las entradas del grupo de confianza y de la aplicación de confianza para el servidor.</span><span class="sxs-lookup"><span data-stu-id="98e0d-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="98e0d-126">Consulte los temas de ayuda de los cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="98e0d-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="98e0d-127">Si estos dos servicios se ejecutan en equipos independientes, después de haber comprobado que se ha instalado el tiempo de ejecución de la API administrada de comunicaciones unificadas 4,0, debe crear un grupo de aplicaciones de confianza de Lync Server y una aplicación de confianza asociada con Outlook Web App; de este se agregará el servidor a la lista de servidores conocidos.</span><span class="sxs-lookup"><span data-stu-id="98e0d-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="98e0d-128">Para ello, primero ejecute un comando similar a este desde dentro del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="98e0d-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="98e0d-129">En el comando anterior, atl-owa-001.litwareinc.com es el nombre de dominio completo del grupo de Outlook Web App; debe ser el mismo nombre que aparece en los campos nombre de sujeto y nombre alternativo de sujeto (SAN) del certificado que proporciona acceso a Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="98e0d-130">Del mismo modo, atl-cs-001.litwareinc.com es el nombre de dominio completo del grupo de servidores de Lync 2013 que hospedará el nuevo grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="98e0d-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="98e0d-131">Tenga en cuenta que el sitio especificado, Redmond, representa el SiteID del sitio de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98e0d-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="98e0d-132">El SiteID no es necesariamente el mismo que el DisplayName del sitio; puede recuperar SiteIDs para los sitios de Lync Server ejecutando el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="98e0d-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="98e0d-133">Después de crear el grupo de aplicaciones de confianza, use un comando similar al siguiente para configurar una identidad de aplicación y un puerto para Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="98e0d-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="98e0d-p110">En el comando anterior, ApplicationID simplemente es un identificador fácil de usar usado para distinguir las aplicaciones de confianza. ApplicationID puede ser cualquier cadena de texto que no incluya espacios en blanco u otros caracteres prohibidos. (Para garantizar la creación de un identificador válido, se recomienda que use solo letras y números al especificar un ApplicationID). El valor asignado al parámetro Port también queda a discreción del administrador: puede ser cualquier puerto disponible de la red.</span><span class="sxs-lookup"><span data-stu-id="98e0d-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="98e0d-137">Después de crear la aplicación de confianza, debe ejecutar el siguiente comando para habilitar los cambios en la topología de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="98e0d-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="98e0d-138">Tenga en cuenta que también debe agregar su servidor de buzones y de acceso de cliente de Exchange a todos los planes de marcado de URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="98e0d-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="98e0d-139">A su vez, se configurarán los servidores como interlocutores SIP de confianza con la topología ExUmRouting para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98e0d-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="98e0d-140">**Habilitación de la mensajería instantánea en Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="98e0d-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="98e0d-141">Con Lync Server correctamente configurado puede empezar a configurar Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="98e0d-142">El primer paso de ese proceso es habilitar la mensajería instantánea en todos los directorios virtuales de Outlook Web App en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="98e0d-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="98e0d-143">(No es necesario habilitar la mensajería instantánea para los directorios virtuales de los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="98e0d-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="98e0d-144">De hecho, se recomienda no habilitar la mensajería instantánea en los servidores back-end. La mensajería instantánea se puede habilitar en los servidores de acceso de cliente mediante la ejecución del siguiente comando desde el shell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="98e0d-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="98e0d-145">De forma predeterminada, la mensajería instantánea está habilitada al instalar Outlook Web App; es decir, la propiedad InstantMessagingEnabled se establece en true.</span><span class="sxs-lookup"><span data-stu-id="98e0d-145">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="98e0d-146">Sin embargo, aún debe ejecutar el comando anterior para establecer el tipo de mensajería instantánea en OCS.</span><span class="sxs-lookup"><span data-stu-id="98e0d-146">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="98e0d-147">De forma predeterminada, InstantMessagingType se establece en none.</span><span class="sxs-lookup"><span data-stu-id="98e0d-147">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="98e0d-148">A continuación, debe agregar las dos líneas siguientes al archivo de Web.config de Outlook Web App (este archivo suele estar en la carpeta C: \\ archivos de programa \\ Microsoft \\ Exchange Server \\ inquilino V15 \\ ClientAccess \\ OWA).</span><span class="sxs-lookup"><span data-stu-id="98e0d-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="98e0d-149">Estas dos líneas deben agregarse en el \<AppSettings\> nodo del archivo Web.config, y este procedimiento solo debe realizarse en los servidores back-end donde se haya instalado Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="98e0d-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="98e0d-150">En el ejemplo anterior, el valor de IMCertificateThumbprint debe ser la huella digital del certificado de Exchange 2013 que está instalado en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="98e0d-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="98e0d-151">Puede recuperar dicha información si ejecuta el siguiente comando desde el shell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="98e0d-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="98e0d-152">Tenga en cuenta que el valor asignado a inservername es el nombre de dominio completo del grupo de servidores de Lync Server en el que se creó el grupo de aplicaciones de confianza para Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="98e0d-153">El certificado que use para Outlook Web App debe ser un certificado que sea de confianza para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98e0d-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="98e0d-154">Una forma de garantizar que el certificado sea de confianza tanto para Lync Server como para Exchange es usar la entidad de certificación interna para crear un certificado en el servidor de buzones de correo, asegurándose de que el FQDN del servidor se use para el nombre del sujeto y que este FQDN aparezca en el campo Nombre alternativo del certificado.</span><span class="sxs-lookup"><span data-stu-id="98e0d-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="98e0d-155">Una vez creado el certificado, se puede importar a los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="98e0d-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="98e0d-156">El resultado de la red es que el mismo certificado se usa para dos propósitos: 1) comunicación entre la mensajería unificada de Exchange y Lync Server; y 2) la integración entre Outlook Web App y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98e0d-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="98e0d-157">Después de actualizar el archivo de Web.config, debe ejecutar el siguiente comando en el servidor back-end de Exchange para reciclar el grupo de Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="98e0d-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="98e0d-158">Si la operación de reciclaje se realiza correctamente, verá el siguiente mensaje en el shell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="98e0d-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="98e0d-159">**Configuración de directivas de buzón de Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="98e0d-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="98e0d-160">En este momento, puede usar el siguiente comando para configurar la mensajería instantánea en la Directiva de buzones de correo de Outlook Web App correspondiente (o directivas).</span><span class="sxs-lookup"><span data-stu-id="98e0d-160">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="98e0d-161">Por ejemplo, este comando, que se ejecuta en uno de los servidores de buzones de correo, habilita la mensajería instantánea en la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="98e0d-161">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="98e0d-162">Y este comando permite la mensajería instantánea para todas las directivas de buzón de Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="98e0d-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="98e0d-163">Una vez habilitada la Directiva de buzón, todos los usuarios administrados por esa Directiva tendrán una integración completa entre Lync Server y Outlook Web App, siempre que:</span><span class="sxs-lookup"><span data-stu-id="98e0d-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="98e0d-164">El usuario tiene un buzón en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="98e0d-165">El usuario se ha habilitado para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="98e0d-166">El usuario tiene una dirección de proxy SIP válida.</span><span class="sxs-lookup"><span data-stu-id="98e0d-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="98e0d-167">**Deshabilitar la mensajería instantánea en Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="98e0d-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="98e0d-168">Como se indicó anteriormente, la mensajería instantánea está habilitada de forma predeterminada en Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="98e0d-169">Esto significa que, si no integra Outlook Web App con Lync Server, los usuarios verán iconos de presencia en blanco y un mensaje de error cada vez que inicien sesión en Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="98e0d-170">Para evitar este problema, use el siguiente comando de Shell de administración de Exchange para deshabilitar la mensajería instantánea en Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="98e0d-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="98e0d-171">**Comprobación de la integración con Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="98e0d-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="98e0d-172">Para comprobar que la mensajería instantánea y la presencia se han integrado con Outlook Web App, inicie sesión en Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="98e0d-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="98e0d-173">En la esquina superior derecha de la pantalla, verá su nombre para mostrar de Exchange.</span><span class="sxs-lookup"><span data-stu-id="98e0d-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="98e0d-174">Si aparece un icono de presencia junto a su nombre (por ejemplo, un icono verde que indica que su estado actual es disponible) que indica que ha integrado correctamente Lync Server y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="98e0d-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="98e0d-175">Después del inicio de sesión inicial en Outlook Web App, compruebe si se ha escrito un evento con el identificador de evento 112 (y el origen de MSExchange OWA) en el registro de eventos del servidor de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="98e0d-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="98e0d-176">Este evento indica que el administrador de extremos de mensajería instantánea se inicializó correctamente.</span><span class="sxs-lookup"><span data-stu-id="98e0d-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="98e0d-177">Si la mensajería instantánea no parece funcionar, en el servidor de buzones de correo, busque archivos de registro en la carpeta C: \\ archivos de programa \\ Microsoft \\ Exchange Server \\ inquilino V15 registro de \\ \\ OWA \\ InstantMessaging.</span><span class="sxs-lookup"><span data-stu-id="98e0d-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="98e0d-178">Si no existen las carpetas Logging o InstantMessaging que indican que se ha producido un error en la integración.</span><span class="sxs-lookup"><span data-stu-id="98e0d-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="98e0d-179">En ese caso, puede usar el seguimiento de SIPStack en Lync Server (todos los niveles y todos los indicadores) para probar y determinar por qué se produjo un error en la integración.</span><span class="sxs-lookup"><span data-stu-id="98e0d-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

