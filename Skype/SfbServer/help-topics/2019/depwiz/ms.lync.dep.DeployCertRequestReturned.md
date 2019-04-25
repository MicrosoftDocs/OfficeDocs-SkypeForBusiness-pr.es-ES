---
title: Solicitud de certificado (devuelto)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'La página de estado de solicitud de certificado en línea presenta información importante que da como resultado de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica de forma exclusiva el certificado. De forma predeterminada, se selecciona la casilla de verificación asignar este certificado a Skype para usos de certificados de servidor empresarial. Si hace clic en Finalizar, el certificado se asignará automáticamente a Skype para Business Server con el fin de que ha definido en los pasos de creación de la solicitud de certificado. De forma predeterminada, con el fin de que se asignará el certificado es:'
ms.openlocfilehash: 70868129dc759e19960d2f6d9e3a9a1dc3d2f941
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216371"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="b48bf-107">Solicitud de certificado (devuelto)</span><span class="sxs-lookup"><span data-stu-id="b48bf-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="b48bf-108">La página de **Estado de solicitud de certificado en línea** presenta información importante que da como resultado de la creación correcta y la emisión de la solicitud de certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="b48bf-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="b48bf-109">Esta página proporciona la huella digital del certificado que identifica de forma exclusiva el certificado.</span><span class="sxs-lookup"><span data-stu-id="b48bf-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="b48bf-110">De forma predeterminada, se selecciona la casilla de verificación **asignar este certificado a Skype para usos de certificados de servidor empresarial** .</span><span class="sxs-lookup"><span data-stu-id="b48bf-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="b48bf-111">Si hace clic en **Finalizar**, el certificado se asignará automáticamente a Skype para Business Server con el fin de que ha definido en los pasos de creación de la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="b48bf-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="b48bf-112">De forma predeterminada, con el fin de que se asignará el certificado es:</span><span class="sxs-lookup"><span data-stu-id="b48bf-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="b48bf-113">Servidor predeterminado para Mutual Transport capa de seguridad (MTLS) - conexiones a clientes y otros servidores</span><span class="sxs-lookup"><span data-stu-id="b48bf-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="b48bf-114">Servicios Web internos - conexiones de cliente y servidor en el sitio Web interno sitio de servicios de Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="b48bf-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="b48bf-115">Servicios Web externos - conexiones de cliente y servidor en el sitio Web externo sitio de servicios de TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="b48bf-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="b48bf-116">Haga clic en la **Vista de detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado son lo que pretende y que el certificado está listo para ser aplicado y poner en uso en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b48bf-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="b48bf-117">Haga clic en **Finalizar** para completar el proceso de solicitud de certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="b48bf-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="b48bf-118">Si ha seleccionado la casilla de verificación **asignar este certificado a Skype para usos de certificados de servidor empresarial**, se asignará automáticamente el certificado.</span><span class="sxs-lookup"><span data-stu-id="b48bf-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="b48bf-119">Si opta por desactive esta casilla de verificación, debe asignar el certificado en un paso independiente.</span><span class="sxs-lookup"><span data-stu-id="b48bf-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b48bf-120">Si el certificado de raíz de entidad de certificación (CA) de certificación emisora no está en el almacén del equipo entidad de certificación raíz de confianza, o si los certificados de CA intermedios no están en el almacén correcto, verá el estado del resumen, tal como se ilustra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="b48bf-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="b48bf-121">No tiene la opción para asignar el certificado.</span><span class="sxs-lookup"><span data-stu-id="b48bf-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="b48bf-122">Para completar el proceso de asignación de certificados, debe importar el certificado raíz de entidad de certificación emisora y los certificados de CA intermedios y, a continuación, asignar el certificado, haga clic en **asignar** en la página principal del Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="b48bf-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

