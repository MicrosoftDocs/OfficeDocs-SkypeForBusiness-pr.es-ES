---
title: 'Lync Server 2013: revisión del informe de certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a584f331deaf702305367042c6c40679ffb7099f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="1bc01-102">Revisión del informe de certificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bc01-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bc01-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1bc01-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1bc01-104">El informe de certificados contiene todos los certificados necesarios en la implementación de Lync Server 2013 recomendada.</span><span class="sxs-lookup"><span data-stu-id="1bc01-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="1bc01-105">La herramienta de planeación cuenta con los nombres de sujeto y los nombres alternativos de sujeto que se han especificado.</span><span class="sxs-lookup"><span data-stu-id="1bc01-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="1bc01-106">El texto predeterminado que queda sin editar puede representar un desafío potencial para el equipo responsable de solicitar y emitir los certificados.</span><span class="sxs-lookup"><span data-stu-id="1bc01-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="1bc01-107">La información de certificados contiene también información sobre dónde puede emitirse normalmente el certificado.</span><span class="sxs-lookup"><span data-stu-id="1bc01-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="1bc01-108">Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público.</span><span class="sxs-lookup"><span data-stu-id="1bc01-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="1bc01-109">Los campos Uso mejorado de clave (EKU) y Asignar a del informe son muy útiles para comprender el objetivo y la ubicación en la que debe estar cada certificado.</span><span class="sxs-lookup"><span data-stu-id="1bc01-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="1bc01-110">![Informe de administración de certificados](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Informe de administración de certificados")</span><span class="sxs-lookup"><span data-stu-id="1bc01-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="1bc01-111">Revise atentamente y asegúrese de comprender el uso y el propósito de cada certificado en la implementación.</span><span class="sxs-lookup"><span data-stu-id="1bc01-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="1bc01-112">Si hay una pregunta sobre lo que hace un certificado, determine qué servidor o servicio está hablando con qué.</span><span class="sxs-lookup"><span data-stu-id="1bc01-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="1bc01-113">Los certificados en Lync Server 2013 se usan para dos propósitos principales:</span><span class="sxs-lookup"><span data-stu-id="1bc01-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="1bc01-114">Seguridad de la capa de transporte mutua (MTLS): los equipos que participan en la comunicación cada uno presentan un certificado que prueba su identidad en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="1bc01-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="1bc01-115">Esto se conoce como autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="1bc01-115">This is known as server authentication.</span></span> <span data-ttu-id="1bc01-116">La comunicación no puede comenzar hasta que cada equipo confíe en la identidad del otro equipo.</span><span class="sxs-lookup"><span data-stu-id="1bc01-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="1bc01-117">Cifrado: el cifrado (Capa de sockets seguros, o SSL, y Seguridad de la capa de transporte, o TLS) es un medio fundamental para proteger las comunicaciones y la privacidad, así como para crear comunicaciones de confianza y un sistema de colaboración.</span><span class="sxs-lookup"><span data-stu-id="1bc01-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1bc01-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bc01-118">See Also</span></span>


[<span data-ttu-id="1bc01-119">Revisión de los informes del administrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bc01-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

