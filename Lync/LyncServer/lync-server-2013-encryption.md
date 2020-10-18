---
title: 'Lync Server 2013: cifrado'
description: 'Lync Server 2013: cifrado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575656"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="93276-103">Cifrado para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93276-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93276-104">_**Última modificación del tema:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="93276-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="93276-105">Microsoft Lync Server 2013 usa TLS y MTLS para cifrar los mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="93276-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="93276-106">Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o atraviesa el perímetro de la red interna.</span><span class="sxs-lookup"><span data-stu-id="93276-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="93276-107">TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia.</span><span class="sxs-lookup"><span data-stu-id="93276-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="93276-108">Si se configura TLS en este vínculo, se requiere MTLS.</span><span class="sxs-lookup"><span data-stu-id="93276-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="93276-109">Por lo tanto, la puerta de enlace debe estar configurada con un certificado de una entidad de certificación que sea de confianza para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="93276-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93276-110">Se publicó un aviso de seguridad sobre SSL 3,0 en 2014.</span><span class="sxs-lookup"><span data-stu-id="93276-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="93276-111">La deshabilitación de SSL 3,0 en Lync Server 2013 es una opción admitida.</span><span class="sxs-lookup"><span data-stu-id="93276-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="93276-112">Para obtener más información sobre el aviso de seguridad, consulte <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="93276-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="93276-114">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="93276-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="93276-115">Para asegurarse de que se usa el protocolo criptográfico más seguro, Lync Server 2013 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="93276-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="93276-116">TLS es un aspecto crítico de Lync Server 2013 y, por lo tanto, es necesario para mantener un entorno compatible.</span><span class="sxs-lookup"><span data-stu-id="93276-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="93276-p104">Los requisitos para el tráfico entre clientes dependen de si el tráfico atraviesa el firewall interno de la empresa. El tráfico estrictamente interno puede utilizar TLS, en cuyo caso se cifran los mensajes instantáneos, o TCP, en cuyo caso no se cifran.</span><span class="sxs-lookup"><span data-stu-id="93276-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="93276-119">En la tabla siguiente, se resumen los requisitos de protocolo para cada tipo de tráfico.</span><span class="sxs-lookup"><span data-stu-id="93276-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="93276-120">Protección de tráfico</span><span class="sxs-lookup"><span data-stu-id="93276-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93276-121">Tipo de tráfico</span><span class="sxs-lookup"><span data-stu-id="93276-121">Traffic type</span></span></th>
<th><span data-ttu-id="93276-122">Protegido por</span><span class="sxs-lookup"><span data-stu-id="93276-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93276-123">De servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="93276-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="93276-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="93276-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93276-125">Cliente a servidor</span><span class="sxs-lookup"><span data-stu-id="93276-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="93276-126">TLS</span><span class="sxs-lookup"><span data-stu-id="93276-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93276-127">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="93276-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="93276-128">TLS (si se ha configurado para TLS)</span><span class="sxs-lookup"><span data-stu-id="93276-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93276-129">Audio, vídeo y uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="93276-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="93276-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="93276-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93276-131">Uso compartido de escritorio (señalización)</span><span class="sxs-lookup"><span data-stu-id="93276-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="93276-132">TLS</span><span class="sxs-lookup"><span data-stu-id="93276-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93276-133">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="93276-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="93276-134">TLS</span><span class="sxs-lookup"><span data-stu-id="93276-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93276-135">Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="93276-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="93276-136">HTTPS</span><span class="sxs-lookup"><span data-stu-id="93276-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="93276-137">Cifrado de medios</span><span class="sxs-lookup"><span data-stu-id="93276-137">Media Encryption</span></span>

<span data-ttu-id="93276-138">El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción.</span><span class="sxs-lookup"><span data-stu-id="93276-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="93276-139">Además, el contenido multimedia que fluye en ambas direcciones entre el servidor de mediación y el próximo salto interno también se cifra con SRTP.</span><span class="sxs-lookup"><span data-stu-id="93276-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="93276-140">Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia no están cifrados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93276-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="93276-141">El servidor de mediación puede admitir el cifrado de los medios que fluyen hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.</span><span class="sxs-lookup"><span data-stu-id="93276-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93276-142">El audio y vídeo (A/V) es compatible con la nueva versión de Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="93276-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="93276-143">Si va a implementar la Federación de A/V con Windows Live Messenger, también debe modificar el nivel de cifrado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93276-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="93276-144">De forma predeterminada, el nivel de cifrado es Requerido.</span><span class="sxs-lookup"><span data-stu-id="93276-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="93276-145">Debe cambiar esta configuración a compatible con el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93276-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="93276-146">Para obtener más información, consulte <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="93276-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="93276-147">El tráfico de medios de audio y vídeo no está cifrado entre los clientes de Microsoft Lync 2013 y Windows Live.</span><span class="sxs-lookup"><span data-stu-id="93276-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="93276-148">FIPS</span><span class="sxs-lookup"><span data-stu-id="93276-148">FIPS</span></span>

<span data-ttu-id="93276-149">Lync Server 2013 y Microsoft Exchange Server 2013 operan con compatibilidad con algoritmos estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server están configurados para usar los algoritmos FIPS 140-2 para la criptografía de sistema.</span><span class="sxs-lookup"><span data-stu-id="93276-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="93276-150">Para implementar la compatibilidad con FIPS, debe configurar todos los servidores que ejecuten Lync Server 2013 para que lo admitan.</span><span class="sxs-lookup"><span data-stu-id="93276-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="93276-151">Para obtener más información sobre el uso de los algoritmos compatibles con FIPS y cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge base, los efectos de habilitar la configuración de seguridad "criptografía de sistema: usar algoritmos compatibles FIPS para cifrado, hash y firma" en Windows XP y en versiones posteriores de Windows en [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="93276-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="93276-152">Para obtener más información sobre las limitaciones y la compatibilidad de FIPS 140-2 en Exchange 2010, consulte Exchange 2010 SP1 y la compatibilidad con algoritmos compatibles con FIPS en [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .</span><span class="sxs-lookup"><span data-stu-id="93276-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

