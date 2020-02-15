---
title: Acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e640e227ab15c19e48ed3dc06e4b7b482ab7b3a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="8f56e-102">Acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Lync Server desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f56e-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f56e-103">_**Última modificación del tema:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="8f56e-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="8f56e-104">El proceso de aprovisionamiento de la conectividad de Lync y Skype ha cambiado, en comparación con los métodos anteriores de aprovisionamiento de PIC.</span><span class="sxs-lookup"><span data-stu-id="8f56e-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="8f56e-105">Este proceso de aprovisionamiento puede tardar hasta treinta días en completarse.</span><span class="sxs-lookup"><span data-stu-id="8f56e-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="8f56e-106">Le recomendamos que primero inicie este proceso, antes de completar los pasos restantes de este documento.</span><span class="sxs-lookup"><span data-stu-id="8f56e-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="8f56e-107">Una vez completado el proceso de aprovisionamiento de Lync-Skype para su cuenta, la cuenta se activa y los usuarios elegibles están habilitados para la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="8f56e-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="8f56e-108">Para aprovisionar la conectividad de Lync y Skype, necesita la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="8f56e-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="8f56e-109">Número de contrato de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8f56e-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="8f56e-110">Nombre de dominio completo (FQDN) del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="8f56e-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="8f56e-111">Dominio (s) del Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="8f56e-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="8f56e-112">Todos los FQDN adicionales del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="8f56e-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="8f56e-113">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="8f56e-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="8f56e-114">A partir de abril de 2019, detendremos la recopilación y la retención de la información de contacto para los clientes aprovisionados para la Federación de Skype mediante el sitio web pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8f56e-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="8f56e-115">Se está realizando este cambio para asegurarse de que el sistema de aprovisionamiento de pic.lync.com cumple con las directivas de privacidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f56e-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="8f56e-116">Una vez que este cambio se produzca, ya no podremos proporcionar actualizaciones de correo electrónico en los cambios pendientes de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8f56e-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="8f56e-117">Los cambios de aprovisionamiento de PIC se completan normalmente en un plazo de 24-48 horas tras su entrada.</span><span class="sxs-lookup"><span data-stu-id="8f56e-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="8f56e-118">Si sigue experimentando problemas de Federación de Skype de 48 horas después de enviar una solicitud de aprovisionamiento, comuníquese con el soporte técnico de Microsoft para investigar el problema.</span><span class="sxs-lookup"><span data-stu-id="8f56e-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f56e-119">Como parte de este cambio, toda la información de contacto especificada anteriormente se purgará de nuestro sistema a finales de abril de 2019.</span><span class="sxs-lookup"><span data-stu-id="8f56e-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="8f56e-120">Para iniciar el proceso de aprovisionamiento para la conectividad entre Lync y Skype:</span><span class="sxs-lookup"><span data-stu-id="8f56e-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="8f56e-121">Inicie sesión en el sitio Web <strong>https://pic.lync.com</strong>, y use su Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="8f56e-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="8f56e-122">Seleccione el tipo de contrato de licencia de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f56e-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="8f56e-123">Active la casilla, comprobando que ha leído y aceptado los derechos de uso del producto para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f56e-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="8f56e-124">En la página <strong>iniciar una solicitud de aprovisionamiento</strong> , haga clic en el vínculo correspondiente para iniciar una solicitud de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="8f56e-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="8f56e-125">En la página <strong>especificar información de aprovisionamiento</strong> , escriba el <strong>FQDN del servicio perimetral de acceso</strong>.</span><span class="sxs-lookup"><span data-stu-id="8f56e-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="8f56e-126">Por ejemplo, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="8f56e-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="8f56e-127">Después del 1 de julio de 2017, Microsoft requerirá además que los clientes tengan el registro SRV de DNS de Federación implementado para que la conectividad de mensajería instantánea pública siga funcionando.</span><span class="sxs-lookup"><span data-stu-id="8f56e-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="8f56e-128">Escriba al menos uno de los nombres de dominio SIP y, a continuación, haga clic en <strong>Agregar</strong>.</span><span class="sxs-lookup"><span data-stu-id="8f56e-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="8f56e-129">Se requiere al menos un servidor perimetral de acceso y un dominio SIP para completar el proceso de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8f56e-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="8f56e-130">El dominio SIP y el servidor perimetral de acceso deben estar activos, en funcionamiento y accesibles en la red.</span><span class="sxs-lookup"><span data-stu-id="8f56e-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="8f56e-131">En la lista de <strong>proveedores de servicios públicos de mensajería instantánea</strong>, seleccione <strong>Skype</strong> y haga clic en <strong>siguiente</strong> para agregar información de contacto y enviar la solicitud de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8f56e-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f56e-132">Después de enviar la solicitud de aprovisionamiento, la cuenta puede tardar hasta 30 días en activarse y los usuarios pueden habilitar la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="8f56e-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="8f56e-133">Habilitación de la Federación y la conectividad de mensajería instantánea pública (PIC)</span><span class="sxs-lookup"><span data-stu-id="8f56e-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="8f56e-134">Una vez que haya enviado la solicitud de aprovisionamiento, puede centrarse en el entorno de Lync Server y en las tareas administrativas necesarias para configurar la conectividad de Lync y Skype.</span><span class="sxs-lookup"><span data-stu-id="8f56e-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="8f56e-135">En esta sección, se supone que el administrador de Lync Server ha implementado Lync Server y ha configurado el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="8f56e-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="8f56e-136">Para obtener más información sobre cómo configurar el acceso externo para Lync Server, consulte "planeación para el [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) acceso de usuarios externos" en e "implementar [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)el acceso de usuarios externos" en.</span><span class="sxs-lookup"><span data-stu-id="8f56e-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="8f56e-137">Para preparar el entorno de Lync Server para la conectividad de Lync y Skype, el administrador de Lync Server debe completar las tres tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f56e-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="8f56e-138">1\.</span><span class="sxs-lookup"><span data-stu-id="8f56e-138">1\.</span></span> <span data-ttu-id="8f56e-139">Configurar la Federación y el PIC</span><span class="sxs-lookup"><span data-stu-id="8f56e-139">Configure Federation and PIC</span></span>

<span data-ttu-id="8f56e-140">La Federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Lync de la organización.</span><span class="sxs-lookup"><span data-stu-id="8f56e-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="8f56e-141">Public Instant Messaging Connectivity (PIC) es una clase de Federación y debe configurarse para permitir que los usuarios de Lync se comuniquen con los usuarios de Skype.</span><span class="sxs-lookup"><span data-stu-id="8f56e-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="8f56e-142">La Federación y el PIC se configuran mediante el panel de control de Lync Server, que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="8f56e-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8f56e-143">La Federación de PIC ya no es compatible con Live Communication Server 2005 SP1 o con Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8f56e-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="8f56e-144">Las plataformas compatibles para la Federación de PIC incluyen Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8f56e-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="8f56e-145">2\.</span><span class="sxs-lookup"><span data-stu-id="8f56e-145">2\.</span></span> <span data-ttu-id="8f56e-146">Configurar al menos una directiva para admitir el acceso de usuarios federados</span><span class="sxs-lookup"><span data-stu-id="8f56e-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="8f56e-147">Mediante el panel de control de Lync Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de Skype pueden colaborar con los usuarios internos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f56e-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="8f56e-148">3\.</span><span class="sxs-lookup"><span data-stu-id="8f56e-148">3\.</span></span> <span data-ttu-id="8f56e-149">Configurar la configuración del proveedor de PIC de Skype para Lync</span><span class="sxs-lookup"><span data-stu-id="8f56e-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="8f56e-150">Mediante el shell de administración de Lync Server, un administrador debe configurar la Directiva de cliente Lync para mostrar Skype como un proveedor de PIC adicional.</span><span class="sxs-lookup"><span data-stu-id="8f56e-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8f56e-151">Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en mensajería instantánea o conferencias en su organización hasta que también configure al menos una directiva (paso 2, anteriormente en este procedimiento) para que admita la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="8f56e-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="8f56e-152">Para configurar la Federación y PIC, consulte "habilitar o deshabilitar la Federación y la conectividad <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>de mensajería instantánea pública" en.</span><span class="sxs-lookup"><span data-stu-id="8f56e-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="8f56e-153">Para configurar al menos una directiva para admitir el acceso de usuarios federados, vea "configuración de directivas para controlar el acceso <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>de usuarios públicos" en.</span><span class="sxs-lookup"><span data-stu-id="8f56e-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="8f56e-154">En un servidor front-end de Lync Server, abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f56e-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="8f56e-155">Ejecute los dos comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f56e-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="8f56e-156">Si todavía no tiene un proveedor PIC en el entorno y está creando un nuevo proveedor PIC, no es necesario que ejecute el cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="8f56e-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="8f56e-157">Agregado en Lync Server 2013 CU5 &amp; Lync Desktop Client en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" Dominios que no son de Microsoft para identificarlos y enrutarlos a Skype (el formato de: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="8f56e-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="8f56e-158">Esta nueva configuración permitirá el formato automático de la dirección del usuario en el cuadro de diálogo "agregar contacto de Skype" con la NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios en el NameDecorationExcludedDomainList ( Actualmente, podemos admitir msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="8f56e-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="8f56e-159">Desde un cliente de Lync, ahora puede seleccionar Skype como proveedor de PIC y agregar un cliente de Skype especificando su cuenta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f56e-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="8f56e-160">Además, un usuario de Skype que haya combinado y haya iniciado sesión con su cuenta Microsoft puede enviar una solicitud de contacto a los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="8f56e-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="8f56e-161">Para obtener más información acerca de las cuentas de Microsoft, vea [¿Qué es una cuenta de Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="8f56e-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="8f56e-162">Para obtener más información sobre cómo agregar clientes a Lync, consulte [uso de la conectividad de Lync y Skype en Lync Server 2013 como usuario final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="8f56e-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="8f56e-163">Para obtener información detallada sobre cómo modificar proveedores hospedados, vea "crear o editar proveedores federados de SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" en.</span><span class="sxs-lookup"><span data-stu-id="8f56e-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="8f56e-164">Esto completa las tareas administrativas que deben realizarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8f56e-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="8f56e-165">Ya está configurado para la conectividad entre Lync y Skype.</span><span class="sxs-lookup"><span data-stu-id="8f56e-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="8f56e-166">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8f56e-166">Additional Resources</span></span>

[<span data-ttu-id="8f56e-167">Usar la conectividad de Lync y Skype en Lync Server 2013 como un usuario final</span><span class="sxs-lookup"><span data-stu-id="8f56e-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="8f56e-168">Guía de aprovisionamiento para Lync-conectividad de Skype en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f56e-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

