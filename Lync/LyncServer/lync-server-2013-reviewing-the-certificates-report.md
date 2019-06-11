---
title: 'Lync Server 2013: revisar el informe certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="63a4a-102">Revisar el informe de certificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63a4a-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63a4a-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="63a4a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="63a4a-104">El informe certificados contiene todos los certificados necesarios en la implementación recomendada de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63a4a-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="63a4a-105">La herramienta de planeación cuenta con los nombres de asunto y los nombres alternativos de asunto que se escriben.</span><span class="sxs-lookup"><span data-stu-id="63a4a-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="63a4a-106">El texto predeterminado que se deja sin editar puede representar un posible desafío para el equipo responsable de solicitar y emitir los certificados.</span><span class="sxs-lookup"><span data-stu-id="63a4a-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="63a4a-107">La información del certificado también contiene datos sobre el origen desde el cual puede emitirse normalmente el certificado.</span><span class="sxs-lookup"><span data-stu-id="63a4a-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="63a4a-108">Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público.</span><span class="sxs-lookup"><span data-stu-id="63a4a-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="63a4a-109">Los campos “Uso mejorado de clave (EKU)” y “Asignar a” del informe son muy útiles para comprender el objetivo y la ubicación de cada certificado.</span><span class="sxs-lookup"><span data-stu-id="63a4a-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="63a4a-110">![Informe de administración de certificados] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Informe de administración de certificados")</span><span class="sxs-lookup"><span data-stu-id="63a4a-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="63a4a-111">Revise con atención y comprenda completamente el uso y el propósito de cada certificado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="63a4a-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="63a4a-112">Si tiene alguna pregunta acerca de la función de un certificado, determine los elementos con los que se comunica un servidor o servicio.</span><span class="sxs-lookup"><span data-stu-id="63a4a-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="63a4a-113">Los certificados de Lync Server 2013 se usan para dos propósitos principales:</span><span class="sxs-lookup"><span data-stu-id="63a4a-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="63a4a-p103">Seguridad de la capa de transporte mutua (MTLS): los equipos que participan en la comunicación presentan un certificado que prueba su identidad al otro equipo; esto se conoce como autenticación del servidor. La comunicación no puede comenzar hasta que ambos equipos confíen mutuamente en la identidad del otro.</span><span class="sxs-lookup"><span data-stu-id="63a4a-p103">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer. This is known as server authentication. Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="63a4a-117">Cifrado: el cifrado (Capa de sockets seguros, o SSL, y Seguridad de la capa de transporte, o TLS) es un medio fundamental para proteger las comunicaciones y la privacidad, así como para crear comunicaciones de confianza y un sistema de colaboración.</span><span class="sxs-lookup"><span data-stu-id="63a4a-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="63a4a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="63a4a-118">See Also</span></span>


[<span data-ttu-id="63a4a-119">Revisión de los informes del administrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63a4a-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

