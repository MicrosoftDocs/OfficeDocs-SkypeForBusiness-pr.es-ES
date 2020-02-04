---
title: Almacenamiento provisional de certificados de AV y OAuth con el rollo en Set-CsCertificate
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
ms.openlocfilehash: 583ab13e50cac7c7a8b345a2ea2cf4c4e1e38d7f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="8cdfa-102">Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usar-Roll en Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="8cdfa-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cdfa-103">_**Última modificación del tema:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="8cdfa-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="8cdfa-104">Las comunicaciones de audio/vídeo (A/V) son un componente clave de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8cdfa-105">Características como el uso compartido de aplicaciones y las conferencias de audio y vídeo dependen de los certificados asignados al servicio perimetral de A/V, específicamente el servicio de autenticación A/V.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="8cdfa-106">Esta nueva característica está diseñada para que funcione con el servicio a/V Edge y el certificado <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="8cdfa-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="8cdfa-107">Se pueden aprovisionar otros tipos de certificados junto con el servicio perimetral A/V y el tipo de certificado OAuth, pero no se beneficiará del comportamiento de coexistencia del certificado de servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="8cdfa-108">Los cmdlets de PowerShell del shell de administración de Lync Server que se usan para administrar certificados de Microsoft Lync Server 2013 se refiere al certificado de servicio perimetral a/V como el tipo de certificado <EM>AudioVideoAuthentication</EM> y el certificado de OAuthServer como tipo <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="8cdfa-109">Para el resto de este tema y para identificar de forma exclusiva los certificados, se les hará referencia mediante el mismo tipo de identificador, <EM>AudioVideoAuthentication</EM> y <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="8cdfa-110">El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="8cdfa-111">Los tokens se generan a partir de atributos del certificado y, cuando el certificado expira, se produce la pérdida de conexión y es necesario volver a unirse con un nuevo token generado por el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="8cdfa-112">Una nueva característica de Lync Server 2013 mejorará este problema: la capacidad de ensayar un nuevo certificado antes de que venza el antiguo y de permitir que ambos certificados sigan funcionando durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="8cdfa-113">Esta característica usa la funcionalidad actualizada en el cmdlet del shell de administración Set-CsCertificate de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="8cdfa-114">El nuevo parámetro –Roll, con el parámetro existente –EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="8cdfa-115">El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="8cdfa-116">A partir de la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:</span><span class="sxs-lookup"><span data-stu-id="8cdfa-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="8cdfa-117">Usar los cmdlets del shell de administración de Lync Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="8cdfa-118">Usar el Asistente para certificados en el Asistente para la implementación de Lync Server le ayuda a crear certificados, pero suele ser del tipo <STRONG>predeterminado</STRONG> que une todos los usos de certificados para el servidor perimetral en un solo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="8cdfa-119">La práctica recomendada si va a usar la característica de certificado rodante es desacoplar el certificado de AudioVideoAuthentication de los otros propósitos del certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="8cdfa-120">Puede aprovisionar y ensayar un certificado del tipo predeterminado, pero solo la parte AudioVideoAuthentication del certificado combinado se beneficiará del almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="8cdfa-121">Un usuario implicado en una conversación de mensajería instantánea, por ejemplo, en el momento en que expira el certificado, deberá cerrar sesión e iniciarla de nuevo para usar el nuevo certificado asociado con el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="8cdfa-122">Se producirá un comportamiento similar para un usuario implicado en una conferencia web con el servicio perimetral de conferencias web.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="8cdfa-123">El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="8cdfa-124">Cree y administre el certificado en un solo lugar y el certificado se almacena en el almacén de administración central para todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="8cdfa-125">Es necesario más detalles para comprender completamente sus opciones y requisitos al usar el cmdlet Set-CsCertificate y su uso para organizar certificados antes de que expire el certificado actual.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-125">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="8cdfa-126">El parámetro – roll es importante, pero esencialmente un único fin.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-126">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="8cdfa-127">Si lo define como un parámetro, está indicando a set-CsCertificate que le proporcionará información sobre el certificado que se verá afectado por tipo (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado se convierta en efectivo definido por – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-127">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="8cdfa-128">**-Roll:** El parámetro – roll es obligatorio y tiene dependencias que deben proporcionarse con él.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="8cdfa-129">Parámetros obligatorios para definir completamente Qué certificados se verán afectados y cómo se aplicarán:</span><span class="sxs-lookup"><span data-stu-id="8cdfa-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="8cdfa-130">**-EffectiveDate:** El parámetro-EffectiveDate define cuándo el nuevo certificado volverá a estar activo con el certificado actual.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="8cdfa-131">El – EffectiveDate puede estar cerca de la hora de expiración del certificado actual o puede ser un período de tiempo más largo.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="8cdfa-132">Un mínimo recomendado: EffectiveDate para el certificado de AudioVideoAuthentication sería de 8 horas, que es el token de vigencia predeterminado para los tokens del servicio de borde AV emitido con el certificado de AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="8cdfa-133">Al ensayar certificados de OAuthTokenIssuer, existen diferentes requisitos para el tiempo de adelanto antes de que el certificado pueda ser efectivo.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-133">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective.</span></span> <span data-ttu-id="8cdfa-134">El tiempo mínimo que el certificado de OAuthTokenIssuer debería tener por su tiempo de adelanto es de 24 horas antes de la fecha de expiración del certificado actual.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-134">The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate.</span></span> <span data-ttu-id="8cdfa-135">El tiempo de adelanto ampliado de la coexistencia se debe a que existen otros roles de servidor que dependen del certificado OAuthTokenIssuer (Exchange Server, por ejemplo), lo que tiene un mayor tiempo de retención para la autenticación y la clave de cifrado del certificado cosecha.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-135">The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="8cdfa-136">**-Huella digital:** La huella digital es un atributo en el certificado que es exclusivo de ese certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="8cdfa-137">El parámetro – Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="8cdfa-138">**-Escriba:** El parámetro – type puede aceptar un único tipo de uso de certificado o una lista separada por comas de tipos de uso de certificados.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="8cdfa-139">Los tipos de certificado son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="8cdfa-140">Por ejemplo, escriba AudioVideoAuthentication es para que lo use el servicio A/V Edge y el servicio de autenticación de AV.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="8cdfa-141">Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el tiempo de adelanto mínimo mínimo requerido para los certificados.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="8cdfa-142">Por ejemplo, necesita organizar los certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="8cdfa-143">El mínimo: EffectiveDate debe ser el mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="8cdfa-144">Si no desea ensayar el certificado de AudioVideoAuthentication con un tiempo de adelanto de 24 horas, hágalo por separado con un EffectiveDate que sea más conveniente para sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="8cdfa-145">Para actualizar o renovar un certificado de servicio perimetral a/V con parámetros-roll y-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="8cdfa-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="8cdfa-146">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="8cdfa-147">Solicite una renovación o un certificado de AudioVideoAuthentication nuevo con una clave privada exportable para el certificado existente en el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="8cdfa-148">Importe el nuevo certificado AudioVideoAuthentication al servidor perimetral y a todos los demás servidores perimetrales de su grupo (si tiene un grupo implementado).</span><span class="sxs-lookup"><span data-stu-id="8cdfa-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="8cdfa-149">Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro-roll con el parámetro – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="8cdfa-150">La fecha de vigencia debe definirse como la hora de caducidad del certificado actual (14:00:00 o 2:00:00 P.M.) menos vigencia del token (de forma predeterminada ocho horas).</span><span class="sxs-lookup"><span data-stu-id="8cdfa-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="8cdfa-151">Esto nos da la ocasión de que el certificado deba establecerse en activo y es la cadena \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 a.m.".</span><span class="sxs-lookup"><span data-stu-id="8cdfa-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8cdfa-152">Para un grupo perimetral, debe tener todos los certificados de AudioVideoAuthentication implementados y aprovisionados por la fecha y hora definida por el parámetro – EffectiveDate del primer certificado implementado para evitar posibles interrupciones en las comunicaciones a/V debido a que el certificado más antiguo vence antes de que todos los tokens del cliente y del consumidor se hayan renovado con el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="8cdfa-153">El comando set-CsCertificate con el parámetro-roll y-EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="8cdfa-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="8cdfa-154">Un ejemplo del comando set-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="8cdfa-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8cdfa-155">El EffectiveDate debe tener el formato para que coincida con la configuración regional y de idioma del servidor.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-155">The EffectiveDate must be formatted to match your server’s region and language settings.</span></span> <span data-ttu-id="8cdfa-156">El ejemplo usa la región de inglés norteamericano y la configuración de idioma</span><span class="sxs-lookup"><span data-stu-id="8cdfa-156">The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="8cdfa-157">Para obtener más información sobre el proceso que establece-CsCertificate,-roll y – EffectiveDate usar para ensayar un nuevo certificado para emitir nuevos tokens de AudioVideoAuthentication mientras se sigue usando un certificado existente para validar AudioVideoAuthentication que se están usando por los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="8cdfa-158">En el siguiente ejemplo, el administrador determina que el certificado de servicio perimetral A/V debe expirar a los 2:00:00 PM en 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="8cdfa-159">Solicita y recibe un nuevo certificado y lo importa a cada servidor perimetral de su grupo.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="8cdfa-160">A la 2 de la 07/22/2012, comienza a ejecutar Get-CsCertificate con – roll,-Thumbprint es igual a la cadena de la huella digital del nuevo certificado, y-EffectiveTime se establece en 07/22/2012 6:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="8cdfa-161">Este comando se ejecuta en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="8cdfa-162">![Usar los parámetros Roll y EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usar los parámetros Roll y EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="8cdfa-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="8cdfa-163">Cuando se alcance el tiempo de vigencia (7/22/2012 6:00:00 A.M.), el nuevo certificado emitirá todos los tokens nuevos.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-163">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="8cdfa-164">Cuando se validan los tokens, los tokens se validan en primer lugar con el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-164">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="8cdfa-165">Si se produce un error en la validación, se intenta el certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-165">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="8cdfa-166">El proceso de prueba del nuevo y del certificado anterior continuará hasta la fecha de vencimiento del certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-166">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="8cdfa-167">Una vez que el certificado antiguo haya expirado (7/22/2012 2:00:00 PM), los tokens solo se validarán con el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-167">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="8cdfa-168">El certificado antiguo se puede eliminar de forma segura con el cmdlet Remove-CsCertificate con el parámetro-Previous.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-168">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="8cdfa-169">Para actualizar o renovar un certificado de OAuthTokenIssuer con parámetros-roll y-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="8cdfa-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="8cdfa-170">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="8cdfa-171">Solicite una renovación o un certificado de OAuthTokenIssuer nuevo con una clave privada exportable para el certificado existente en el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="8cdfa-172">Importe el nuevo certificado OAuthTokenIssuer a un servidor front-end de su grupo (si tiene un grupo implementado).</span><span class="sxs-lookup"><span data-stu-id="8cdfa-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="8cdfa-173">El certificado OAuthTokenIssuer se replica de forma global y solo es necesario actualizarlo y renovarlo en cualquier servidor de la implementación.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="8cdfa-174">El servidor front-end se usa como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="8cdfa-175">Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro-roll con el parámetro – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-175">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="8cdfa-176">La fecha de vigencia debe definirse como la hora de caducidad del certificado actual (14:00:00 o 2:00:00 P.M.) menos un mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-176">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="8cdfa-177">El comando set-CsCertificate con el parámetro-roll y-EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="8cdfa-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="8cdfa-178">Un ejemplo del comando set-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="8cdfa-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8cdfa-179">El EffectiveDate debe tener el formato para que coincida con la configuración regional y de idioma del servidor.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-179">The EffectiveDate must be formatted to match your server’s region and language settings.</span></span> <span data-ttu-id="8cdfa-180">El ejemplo usa la región de inglés norteamericano y la configuración de idioma</span><span class="sxs-lookup"><span data-stu-id="8cdfa-180">The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="8cdfa-181">Cuando se alcance el tiempo de vigencia (7/21/2012 1:00:00 A.M.), el nuevo certificado emitirá todos los tokens nuevos.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-181">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="8cdfa-182">Cuando se validan los tokens, los tokens se validan en primer lugar con el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-182">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="8cdfa-183">Si se produce un error en la validación, se intenta el certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-183">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="8cdfa-184">El proceso de prueba del nuevo y del certificado anterior continuará hasta la fecha de vencimiento del certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-184">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="8cdfa-185">Una vez que el certificado antiguo haya expirado (7/22/2012 2:00:00 PM), los tokens solo se validarán con el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-185">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="8cdfa-186">El certificado antiguo se puede eliminar de forma segura con el cmdlet Remove-CsCertificate con el parámetro-Previous.</span><span class="sxs-lookup"><span data-stu-id="8cdfa-186">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8cdfa-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cdfa-187">See Also</span></span>


[<span data-ttu-id="8cdfa-188">Plan para certificados de servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cdfa-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="8cdfa-189">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cdfa-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="8cdfa-190">Configurar certificados perimetrales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cdfa-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="8cdfa-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8cdfa-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="8cdfa-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8cdfa-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

