---
title: 'Lync Server 2013: cifrado'
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
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="c8e0b-102">Cifrado para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8e0b-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8e0b-103">_**Última modificación del tema:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="c8e0b-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="c8e0b-104">Microsoft Lync Server 2013 usa TLS y MTLS para cifrar los mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="c8e0b-105">Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="c8e0b-106">TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="c8e0b-107">Si en este vínculo está configurado TLS, se requiere MTLS.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="c8e0b-108">Por lo tanto, la puerta de enlace debe estar configurada con un certificado de una entidad emisora de confianza en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8e0b-109">En 2014 se publicó un aviso de seguridad sobre SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="c8e0b-110">La opción de deshabilitar SSL 3,0 en Lync Server 2013 es una opción admitida.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="c8e0b-111">Para obtener más información sobre el asesoramiento de seguridad <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, consulte.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="c8e0b-113">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="c8e0b-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c8e0b-114">Para asegurarse de que se usa el protocolo criptográfico más sólido, Lync Server 2013 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="c8e0b-115">TLS es un aspecto crítico de Lync Server 2013 y, por lo tanto, es necesario para mantener un entorno compatible.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="c8e0b-116">Los requisitos para el tráfico de cliente a cliente dependen de si ese tráfico atraviesa el firewall interno de la empresa.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="c8e0b-117">El tráfico estrictamente interno puede usar TLS, en cuyo caso el mensaje instantáneo se cifra, o TCP, en cuyo caso no lo es.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="c8e0b-118">En la tabla siguiente se resumen los requisitos de protocolo para cada tipo de tráfico.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="c8e0b-119">Protección de tráfico</span><span class="sxs-lookup"><span data-stu-id="c8e0b-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8e0b-120">Tipo de tráfico</span><span class="sxs-lookup"><span data-stu-id="c8e0b-120">Traffic type</span></span></th>
<th><span data-ttu-id="c8e0b-121">Protegido por</span><span class="sxs-lookup"><span data-stu-id="c8e0b-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8e0b-122">Servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="c8e0b-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="c8e0b-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e0b-124">Cliente a servidor</span><span class="sxs-lookup"><span data-stu-id="c8e0b-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-125">TLS</span><span class="sxs-lookup"><span data-stu-id="c8e0b-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8e0b-126">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="c8e0b-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-127">TLS (si está configurado para TLS)</span><span class="sxs-lookup"><span data-stu-id="c8e0b-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e0b-128">Audio, vídeo y uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="c8e0b-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="c8e0b-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8e0b-130">Uso compartido de escritorio (señalización)</span><span class="sxs-lookup"><span data-stu-id="c8e0b-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-131">TLS</span><span class="sxs-lookup"><span data-stu-id="c8e0b-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e0b-132">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="c8e0b-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-133">TLS</span><span class="sxs-lookup"><span data-stu-id="c8e0b-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8e0b-134">Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="c8e0b-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="c8e0b-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c8e0b-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="c8e0b-136">Cifrado de medios</span><span class="sxs-lookup"><span data-stu-id="c8e0b-136">Media Encryption</span></span>

<span data-ttu-id="c8e0b-137">El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="c8e0b-138">Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="c8e0b-139">Los medios que fluyen en las dos direcciones entre el servidor de mediación y una puerta de enlace multimedia no están cifrados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="c8e0b-140">El servidor de mediación puede admitir el cifrado hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8e0b-141">El audio/vídeo (A/V) es compatible con la nueva versión de Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="c8e0b-142">Si está implementando la Federación de A/V con Windows Live Messenger, también debe modificar el nivel de cifrado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="c8e0b-143">De manera predeterminada, el nivel de cifrado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="c8e0b-144">Debe cambiar esta configuración para que sea compatible con el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="c8e0b-145">Para obtener más información, vea <A href="lync-server-2013-deploying-external-user-access.md">implementar el acceso de usuarios externos en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c8e0b-146">El tráfico de audio y vídeo no se cifra entre Microsoft Lync 2013 y los clientes de Windows Live.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="c8e0b-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="c8e0b-147">FIPS</span></span>

<span data-ttu-id="c8e0b-148">Lync Server 2013 y Microsoft Exchange Server 2013 funcionan con los algoritmos estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server están configurados para usar los algoritmos FIPS 140-2 para el cifrado de sistema.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="c8e0b-149">Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecute Lync Server 2013 de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="c8e0b-150">Para obtener más información sobre el uso de los algoritmos compatibles con FIPS y cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge base, los efectos de habilitar la configuración de seguridad "criptografía de sistema: usar algoritmos compatibles con FIPS para cifrado, hash y firma" en Windows XP [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)y en versiones posteriores de Windows en.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="c8e0b-151">Para obtener más información sobre las limitaciones y la compatibilidad de FIPS 140-2 en Exchange 2010, consulte Exchange 2010 SP1 y la compatibilidad [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)con los algoritmos compatibles con FIPS en.</span><span class="sxs-lookup"><span data-stu-id="c8e0b-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

