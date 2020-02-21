---
title: 'Lync Server 2013: compatibilidad y requisitos de servidor adicionales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7b83f900a5d6ccca9932b68e012d5c0dbbd6d23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="e7057-102">Compatibilidad de servidor adicional y requisitos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7057-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7057-103">_**Última modificación del tema:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="e7057-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="e7057-104">Además de la compatibilidad de software que se describe en las otras secciones de esta documentación de compatibilidad, Lync Server 2013 tiene las siguientes limitaciones de compatibilidad:</span><span class="sxs-lookup"><span data-stu-id="e7057-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="e7057-105">Lync Server 2013 admite el sistema de nombres de dominio (DNS) y el equilibrio de carga de hardware para roles de servidor específicos.</span><span class="sxs-lookup"><span data-stu-id="e7057-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="e7057-106">También admite, si corresponde, el equilibrio de carga de aplicaciones para servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="e7057-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="e7057-107">Para obtener información detallada acerca de cuándo usar cada uno de ellos, consulte la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="e7057-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="e7057-108">Lync Server 2013 usa el protocolo de expansión de listas de distribución (DLX) para expandir las listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="e7057-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="e7057-109">Este protocolo también especifica el método de servicio web que se usa para obtener la pertenencia de una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="e7057-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="e7057-110">Microsoft Exchange Server admite grupos dinámicos que no tienen miembros asignados estáticamente.</span><span class="sxs-lookup"><span data-stu-id="e7057-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="e7057-111">En lugar de ello, almacenan consultas que se evalúan al expandir el grupo.</span><span class="sxs-lookup"><span data-stu-id="e7057-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="e7057-112">DLX no es compatible con listas de distribución dinámicas.</span><span class="sxs-lookup"><span data-stu-id="e7057-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="e7057-113">Esta limitación de DLX se aplica a todas las versiones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7057-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="e7057-114">El Asistente para habilitar usuarios no permite la conversión automática de caracteres que no sean ingleses a un URI compatible con SIP, por lo que la dirección SIP debe modificarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="e7057-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="e7057-115">Para los servidores que ejecutan software antivirus, consulte [exclusiones de análisis antivirus para Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) para conocer las exclusiones de virus sugeridas y otras recomendaciones relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7057-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="e7057-116">Si usa IPsec, se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="e7057-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="e7057-117">Para obtener más información, consulte [excepciones de IPSec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="e7057-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="e7057-118">Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.</span><span class="sxs-lookup"><span data-stu-id="e7057-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="e7057-119">Para obtener información detallada sobre la implementación de QoS, consulte [Administración de calidad de servicio (QoS) en Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e7057-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="e7057-120">Se admite el uso del firewall del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e7057-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="e7057-121">Lync Server 2013 administra las excepciones de Firewall para el firewall del sistema operativo, excepto para el software de base de datos de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7057-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="e7057-122">Para obtener más información acerca de firewall de los requisitos de SQL Server, consulte la documentación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7057-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="e7057-123">Las interfaces externas que se usan para permitir el acceso de usuarios externos deben estar en una subred independiente, *no* en la misma red que las interfaces internas.</span><span class="sxs-lookup"><span data-stu-id="e7057-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="e7057-124">La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="e7057-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="e7057-125">Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="e7057-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="e7057-126">Con el lanzamiento de las actualizaciones acumulativas de Lync Server 2013:2013 de julio de 2007, Lync Server 2013 ahora es compatible con la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="e7057-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="e7057-127">Para obtener más información, vea [autenticación en dos fases en Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e7057-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="e7057-128">La mayoría de los servidores internos necesitan un tipo de certificado definido como **autenticación abierta** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="e7057-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="e7057-129">Debe solicitar y asignar un certificado de OAuth durante la **solicitud, instalar y asignar certificados** en la fase del Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7057-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="e7057-130">El tamaño mínimo de una clave de certificado de OAuth es de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="e7057-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="e7057-131">Se puede mostrar una advertencia si solicita un certificado con una longitud de clave inferior a 2048 bits de longitud.</span><span class="sxs-lookup"><span data-stu-id="e7057-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="e7057-132">Para evitar posibles problemas en el caso de que se aplique una longitud de clave de 2048 en lugar de advertencias, se recomienda encarecidamente usar siempre una longitud de clave de 2048 para los certificados de OAuth.</span><span class="sxs-lookup"><span data-stu-id="e7057-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="e7057-133">Lync Server 2013 y Microsoft Exchange Server 2010 Service Pack 1 (SP1) funcionan con los algoritmos estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server 2008 R2 están configurados para usar los algoritmos FIPS 140-2 para criptografía de sistema.</span><span class="sxs-lookup"><span data-stu-id="e7057-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="e7057-134">Para implementar la compatibilidad con FIPS, debe configurar todos los servidores que ejecuten Lync Server 2013 para que lo admitan.</span><span class="sxs-lookup"><span data-stu-id="e7057-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="e7057-135">Para obtener más información sobre los algoritmos compatibles con FIPS y cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge base, "criptografía de sistema: usar algoritmos compatibles con FIPS para cifrado, hashing y configuración de seguridad de firma en [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)Windows XP y en versiones posteriores de Windows en.</span><span class="sxs-lookup"><span data-stu-id="e7057-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="e7057-136">Para obtener más información acerca de la compatibilidad y las limitaciones de FIPS 140-2 en Exchange 2010, consulte "Exchange 2010 SP1 y la compatibilidad [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)con algoritmos compatibles con FIPS" en.</span><span class="sxs-lookup"><span data-stu-id="e7057-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="e7057-137">Lync Server 2013 requiere la instalación de otro software en componentes específicos antes o durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="e7057-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="e7057-138">Esto incluye el software que está disponible con el sistema operativo, el software descargable y el software que se instala automáticamente durante la instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7057-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="e7057-139">A continuación se muestra una lista del software adicional que puede ser necesario:</span><span class="sxs-lookup"><span data-stu-id="e7057-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="e7057-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e7057-140">Windows Update</span></span>

  - <span data-ttu-id="e7057-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="e7057-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="e7057-142">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e7057-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="e7057-143">Paquete redistribuible de Microsoft Visual C++ 2012</span><span class="sxs-lookup"><span data-stu-id="e7057-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7057-144">El redistribuible de Microsoft Visual C++ 2012 se instala automáticamente al instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7057-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="e7057-145">No debe instalar ni usar ninguna otra versión.</span><span class="sxs-lookup"><span data-stu-id="e7057-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="e7057-146">Paquete redistribuible del Módulo URL Rewrite versión 2.0</span><span class="sxs-lookup"><span data-stu-id="e7057-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="e7057-147">Motor en tiempo de ejecución de Windows Media Format</span><span class="sxs-lookup"><span data-stu-id="e7057-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="e7057-148">Windows PowerShell versión 3,0</span><span class="sxs-lookup"><span data-stu-id="e7057-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="e7057-149">Complemento del explorador Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la última versión para el panel de control de Lync Server)</span><span class="sxs-lookup"><span data-stu-id="e7057-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="e7057-150">Herramientas de servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="e7057-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="e7057-151">Algunos de estos requisitos de software se aplican solamente a roles de servidor o componentes específicos.</span><span class="sxs-lookup"><span data-stu-id="e7057-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="e7057-152">Para obtener más información sobre estos requisitos de software, consulte [Additional software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="e7057-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

