---
title: Solicitud de certificado (devuelto)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'La página de estado de la solicitud de certificado en línea presenta información importante que resulta de la creación y la emisión satisfactoria de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica de forma única el certificado. De forma predeterminada, la casilla asignar este certificado a los usos de certificados de Skype empresarial Server está seleccionada. Si hace clic en finalizar, el certificado se asignará automáticamente a Skype empresarial Server para los propósitos que definió durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los propósitos en los que se asignará el certificado son los siguientes:'
ms.openlocfilehash: 02d114ff55360f3e88a866485759510ce5f107c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278024"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="4b3a1-107">Solicitud de certificado (devuelto)</span><span class="sxs-lookup"><span data-stu-id="4b3a1-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="4b3a1-108">La página de estado de la **solicitud de certificado en línea** presenta información importante que resulta de la creación y la emisión satisfactoria de la solicitud de certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="4b3a1-109">Esta página proporciona la huella digital del certificado que identifica de forma única el certificado.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="4b3a1-110">De forma predeterminada, la casilla **asignar este certificado a los usos de certificados de Skype empresarial Server** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="4b3a1-111">Si hace clic en **Finalizar**, el certificado se asignará automáticamente a Skype empresarial Server para los propósitos que definió durante los pasos de creación de la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="4b3a1-112">De forma predeterminada, los propósitos en los que se asignará el certificado son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b3a1-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="4b3a1-113">Valor predeterminado del servidor para la seguridad de la capa de transporte mutuo (MTLS): conexiones a clientes y otros servidores</span><span class="sxs-lookup"><span data-stu-id="4b3a1-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="4b3a1-114">Servicios Web internos: conexiones de cliente y servidor en el sitio de servicios Web interno para seguridad de la capa de transporte/capa de sockets seguros (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="4b3a1-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="4b3a1-115">Servicios web externa: conexiones de cliente y servidor en el sitio de servicios Web externo para TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="4b3a1-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="4b3a1-116">Haga clic en **Ver detalles** del certificado para ver el certificado para confirmar que las propiedades del certificado son las previstas y que el certificado está listo para aplicarse y usarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="4b3a1-117">Haga clic en **Finalizar** para completar el proceso de solicitud de certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="4b3a1-118">Si seleccionó la casilla de verificación **asignar este certificado a los usos del certificado de Skype empresarial Server**, el certificado se asignará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="4b3a1-119">Si opta por desactivar esta casilla, debe asignar el certificado en un paso independiente.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4b3a1-120">Si el certificado raíz de la entidad de certificación (CA) de emisión no se encuentra en el almacén de entidades de certificación raíz de confianza del equipo o si no se encuentran en el almacén adecuado, verá el estado de Resumen, tal y como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="4b3a1-121">No tiene la opción de asignar el certificado.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="4b3a1-122">Para completar el proceso de asignación de certificados, debe importar el certificado raíz de la CA emisora y los certificados de la entidad emisora intermedia y, después, asignar el certificado haciendo clic en **asignar** en la Página principal del Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

