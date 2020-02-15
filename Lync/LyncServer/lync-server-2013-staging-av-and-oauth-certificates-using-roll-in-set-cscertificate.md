---
title: Almacenamiento provisional de certificados AV y OAuth usando-Roll en Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a85d39fb80075e4de817c4343040d358ad41eeb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="c983d-102">Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="c983d-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c983d-103">_**Última modificación del tema:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="c983d-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="c983d-104">Las comunicaciones de audio y vídeo (A/V) son un componente clave de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c983d-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c983d-105">Características como el uso compartido de aplicaciones y las conferencias de audio y vídeo se basan en los certificados asignados al servicio perimetral a/V, específicamente en el servicio de autenticación A/V.</span><span class="sxs-lookup"><span data-stu-id="c983d-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="c983d-106">Esta nueva característica está diseñada para funcionar para el servicio perimetral A/V y el certificado <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="c983d-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="c983d-107">Se pueden aprovisionar otros tipos de certificados junto con el servicio perimetral A/V y el tipo de certificado OAuth, pero no se beneficiarán del comportamiento de coexistencia que tendrá el certificado del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="c983d-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="c983d-108">Los cmdlets de PowerShell del shell de administración de Lync Server que se usan para administrar certificados de Microsoft Lync Server 2013 hacen referencia al certificado del servicio perimetral A/V como el tipo de certificado <EM>AudioVideoAuthentication</EM> y el certificado OAuthServer como tipo <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="c983d-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="c983d-109">Para el resto de este tema y para identificar de forma exclusiva los certificados, se hará referencia a ellos por el mismo tipo de identificador, <EM>AudioVideoAuthentication</EM> y <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="c983d-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="c983d-110">El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V.</span><span class="sxs-lookup"><span data-stu-id="c983d-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="c983d-111">Los tokens se generan desde atributos del certificado, y cuando el certificado expira, se producirá la pérdida de conexión y el requisito de volverse a unir con un nuevo token generado por el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="c983d-112">Una nueva característica de Lync Server 2013 solucionará este problema: la capacidad de ensayar un nuevo certificado antes de la antigua expiración y permitir que ambos certificados sigan funcionando durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c983d-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="c983d-113">Esta característica usa la funcionalidad actualizada en el cmdlet Set-CsCertificate Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c983d-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="c983d-114">El nuevo parámetro –Roll, con el parámetro existente –EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c983d-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="c983d-115">El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos.</span><span class="sxs-lookup"><span data-stu-id="c983d-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="c983d-116">Comenzando por la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:</span><span class="sxs-lookup"><span data-stu-id="c983d-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="c983d-117">Con los cmdlets del shell de administración de Lync Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c983d-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="c983d-118">El uso del Asistente para certificados en el Asistente para la implementación de Lync Server le ayudará a crear certificados, pero suele ser el tipo <STRONG>predeterminado</STRONG> que une todos los usos de certificados para el servidor perimetral en un único certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="c983d-119">La práctica recomendada si va a usar la característica de certificado en secuencia es desvincular el certificado AudioVideoAuthentication de los demás fines de certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="c983d-120">Puede aprovisionar y organizar un certificado del tipo predeterminado pero solo la parte de AudioVideoAuthentication del certificado combinado se beneficiará del ensayo.</span><span class="sxs-lookup"><span data-stu-id="c983d-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="c983d-121">Un usuario implicado en una conversación de mensajería instantánea (por ejemplo) cuando expire el certificado tendrá que cerrar la sesión y volver a iniciarla para usar el nuevo certificado asociado al servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="c983d-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="c983d-122">Se producirá un comportamiento similar para un usuario implicado en una conferencia Web mediante el servicio perimetral de conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="c983d-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="c983d-123">El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="c983d-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="c983d-124">El certificado se crea y se administra en un solo punto y el certificado se almacena en el almacén de administración central para todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="c983d-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="c983d-125">Se necesitan detalles adicionales para comprender por completo sus opciones y requisitos al usar el cmdlet Set-CsCertificate y al usarlo para organizar certificados anteriores al certificado actual que expira.</span><span class="sxs-lookup"><span data-stu-id="c983d-125">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="c983d-126">El parámetro –Roll es importante pero esencialmente de un solo propósito.</span><span class="sxs-lookup"><span data-stu-id="c983d-126">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="c983d-127">Si lo define como un parámetro, estará indicando a set-CsCertificate que proporcionará información sobre el certificado que se verá afectada por el tipo (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado se convertirá en efectivo definido por – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="c983d-127">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="c983d-128">**-Roll:** El parámetro – roll es obligatorio y tiene dependencias que se deben proporcionar junto con él.</span><span class="sxs-lookup"><span data-stu-id="c983d-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="c983d-129">Parámetros obligatorios para definir por completo qué certificados se verán afectados y cómo se aplicarán:</span><span class="sxs-lookup"><span data-stu-id="c983d-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="c983d-130">**-EffectiveDate:** El parámetro – EffectiveDate define cuándo el nuevo certificado se convertirá en coactivo con el certificado actual.</span><span class="sxs-lookup"><span data-stu-id="c983d-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="c983d-131">El –EffectiveDate puede estar cercano al tiempo de expiración del certificado actual o bien, puede ser un período de tiempo mayor.</span><span class="sxs-lookup"><span data-stu-id="c983d-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="c983d-132">Un –EffectiveDate mínimo recomendado para el certificado AudioVideoAuthentication sería de 8 horas, que es la vigencia de token predeterminada para los tokens de servicio perimetral AV emitidos con el certificado AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="c983d-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="c983d-p109">Al organizar certificados OAuthTokenIssuer, hay diferentes requisitos para el plazo antes de que el certificado se haga efectivo. El tiempo mínimo que el certificado OAuthTokenIssuer debe tener para su plazo es de 24 horas antes del tiempo de expiración del certificado actual. El plazo extendido para la coexistencia es debido a otros roles de servidor que son independientes del certificado OAuthTokenIssuer (Exchange Server, por ejemplo) que tiene un tiempo de retención superior para los materiales clave de cifrado y autenticación creada de certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="c983d-136">**-Thumbprint:** La huella digital es un atributo en el certificado que es único para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="c983d-137">El parámetro –Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="c983d-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="c983d-138">**-Tipo:** El parámetro – type puede aceptar un solo tipo de uso de certificado o una lista separada por comas de tipos de uso de certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="c983d-139">Los tipos de certificado son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="c983d-140">Por ejemplo, escriba AudioVideoAuthentication es para que lo use el servicio perimetral A/V y el servicio de autenticación AV.</span><span class="sxs-lookup"><span data-stu-id="c983d-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="c983d-141">Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el plazo de entrega efectivo mínimo que se necesita para los certificados.</span><span class="sxs-lookup"><span data-stu-id="c983d-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="c983d-142">Por ejemplo, necesita organizar los certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="c983d-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="c983d-143">El valor mínimo de EffectiveDate debe ser el mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="c983d-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="c983d-144">Si no desea ensayar el certificado AudioVideoAuthentication con un tiempo de entrega de 24 horas, guárdelo por separado con un EffectiveDate que sea más importante para sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="c983d-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="c983d-145">Para actualizar o renovar un certificado de servicio perimetral a/V con parámetros – roll y-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="c983d-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="c983d-146">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="c983d-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="c983d-147">Solicite una renovación o un nuevo certificado AudioVideoAuthentication con clave privada exportable para el certificado existente en el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="c983d-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="c983d-148">Importe el nuevo certificado AudioVideoAuthentication en el servidor perimetral y en el resto de servidores perimetrales del grupo de servidores (si tiene un grupo de servidores implementado).</span><span class="sxs-lookup"><span data-stu-id="c983d-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="c983d-149">Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro –Roll con el parámetro –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="c983d-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="c983d-150">La fecha efectiva se debe definir como la hora de expiración del certificado actual (14:00:00 o 2:00:00 PM) menos la vigencia de token (de manera predeterminada, ocho horas).</span><span class="sxs-lookup"><span data-stu-id="c983d-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="c983d-151">Esto nos da el tiempo necesario para establecer el certificado en activo y es la cadena \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 a.m.".</span><span class="sxs-lookup"><span data-stu-id="c983d-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="c983d-152">Para un grupo de servidores perimetrales, debe tener todos los certificados AudioVideoAuthentication implementados y aprovisionados por la fecha y hora definida por el parámetro – EffectiveDate del primer certificado implementado para evitar posibles interrupciones de comunicaciones a/V debido a que el certificado anterior expira antes de que todos los tokens de cliente y consumidor se hayan renovado con el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="c983d-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="c983d-153">El comando Set-CsCertificate con el parámetro –Roll y –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="c983d-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="c983d-154">Un comando Set-CsCertificate de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c983d-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="c983d-p113">La EffectiveDate debe tener el formato que coincida con la configuración regional y de idioma de su servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.)</span><span class="sxs-lookup"><span data-stu-id="c983d-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="c983d-157">Para comprender mejor el proceso que Set-CsCertificate, -Roll y –EffectiveDate usan para organizar un nuevo certificado para emitir nuevos tokens AudioVideoAuthentication a la vez que usan un certificado existente para validar udioVideoAuthentication que usan los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso.</span><span class="sxs-lookup"><span data-stu-id="c983d-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="c983d-158">En el siguiente ejemplo, el administrador determina que el certificado del servicio perimetral A/V debe expirar a las 2:00:00 PM en 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="c983d-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="c983d-159">Solicita y recibe un nuevo certificado y lo importa a cada servidor perimetral en su grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="c983d-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="c983d-160">A las  2 AM del 22/07/2012, comienza a ejecutar Get-CsCertificate con –Roll, -Thumbprint igual a la cadena de huella digital del nuevo certificado y –EffectiveTime establecido en 22/07/2012 6:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="c983d-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="c983d-161">Ejecuta este comando en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c983d-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="c983d-162">![Con los parámetros roll y EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Con los parámetros roll y EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="c983d-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="c983d-p115">Cuando se alcanza la hora de vigencia (22/7/2012 6:00:00 AM), se emiten todos los nuevos tokens por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el antiguo certificado ha expirado (7/22/2012 2:00:00 PM), los tokens solo los validará el nuevo certificado. El antiguo certificado se puede quitar de manera segura mediante el cmdlet Remove-CsCertificate con el parámetro –Previous.</span><span class="sxs-lookup"><span data-stu-id="c983d-p115">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="c983d-169">Para actualizar o renovar un certificado OAuthTokenIssuer con parámetros –Roll y -EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="c983d-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="c983d-170">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="c983d-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="c983d-171">Solicite una renovación o un nuevo certificado OAuthTokenIssuer con clave privada exportable para el certificado existente en el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="c983d-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="c983d-172">Importe el nuevo certificado OAuthTokenIssuer en un servidor front-end del grupo de servidores (si tiene un grupo de servidores implementado).</span><span class="sxs-lookup"><span data-stu-id="c983d-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="c983d-173">El certificado OAuthTokenIssuer se replica globalmente y solo se tiene que replicar y renovar en cualquier servidor de su implementación.</span><span class="sxs-lookup"><span data-stu-id="c983d-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="c983d-174">El servidor front-end se usa como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c983d-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="c983d-p117">Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro –Roll con el parámetro –EffectiveDate. La fecha de vigencia se debe definir como la hora de expiración de certificado actual (14:00:00 o 2:00:00 PM) menos un mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="c983d-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="c983d-177">El comando Set-CsCertificate con el parámetro –Roll y –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="c983d-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="c983d-178">Un comando Set-CsCertificate de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c983d-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="c983d-p118">La EffectiveDate debe tener el formato que coincida con la configuración regional y de idioma de su servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.)</span><span class="sxs-lookup"><span data-stu-id="c983d-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="c983d-p119">Cuando se alcanza la hora efectiva (21.07.12 01:00:00 AM), todos los nuevos tokens se emiten por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el antiguo certificado ha expirado (22/7/2012 2:00:00 PM), los tokens solo los validará el nuevo certificado. El antiguo certificado se puede quitar de manera segura mediante el cmdlet Remove-CsCertificate con el parámetro –Previous.</span><span class="sxs-lookup"><span data-stu-id="c983d-p119">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c983d-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="c983d-187">See Also</span></span>


[<span data-ttu-id="c983d-188">Planeación de certificados de servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c983d-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="c983d-189">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c983d-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="c983d-190">Configurar certificados perimetrales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c983d-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="c983d-191">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c983d-191">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="c983d-192">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c983d-192">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

