---
title: Solicitud de certificado (devuelto)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'La página Estado de solicitud del certificado en línea muestra información importante que surge de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica al certificado de forma exclusiva. De forma predeterminada, la casilla Asignar este certificado a los usos de certificados de Skype Empresarial Server está activada. Si hace clic en Finalizar, el certificado se asignará automáticamente a Lync Server 2013 para los fines que haya definido durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los usos que se asignan al certificado son:'
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805150"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="0a551-107">Solicitud de certificados (devuelto)</span><span class="sxs-lookup"><span data-stu-id="0a551-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="0a551-108">La página **Estado de solicitud del certificado en línea** muestra información importante que surge de la creación correcta y la emisión de la solicitud de certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="0a551-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="0a551-109">Esta página proporciona la huella digital del certificado que identifica al certificado de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="0a551-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="0a551-110">De forma predeterminada, la casilla Asignar **este certificado a los usos** de certificados de Skype Empresarial Server está activada.</span><span class="sxs-lookup"><span data-stu-id="0a551-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="0a551-111">Si hace clic **en Finalizar,** el certificado se asignará automáticamente a Lync Server 2013 para los fines que haya definido durante los pasos de creación de la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="0a551-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="0a551-112">De forma predeterminada, los usos que se asignan al certificado son:</span><span class="sxs-lookup"><span data-stu-id="0a551-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="0a551-113">Valor predeterminado del servidor para seguridad de la capa de transporte mutua (MTLS): conexiones a clientes y otros servidores</span><span class="sxs-lookup"><span data-stu-id="0a551-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="0a551-114">Servicios web internos: conexiones de cliente y servidor en el sitio de servicios web internos para Seguridad de la capa de transporte/Capa de sockets seguros (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="0a551-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="0a551-115">Servicios web externos: conexiones de cliente y servidor en el sitio de servicios web externos para TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="0a551-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="0a551-116">Haga clic en **Ver detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado sean las que ha previsto y comprobar que el certificado esté listo para aplicarse y ponerse en uso en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0a551-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="0a551-117">Haga clic en **Finalizar** para completar el proceso de solicitud del certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="0a551-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="0a551-118">Si ha seleccionado la casilla Asignar este certificado a los usos de certificados de **Skype Empresarial Server,** el certificado se asignará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0a551-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="0a551-119">Si decide desactivar esta casilla, el certificado debe asignarse en un paso aparte.</span><span class="sxs-lookup"><span data-stu-id="0a551-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0a551-120">Si el certificado raíz de la entidad de certificación (CA) emisora no está en el almacén de entidades de certificación raíz de confianza del equipo, o si los certificados de CA intermedias no están en el almacén adecuado, verá el estado de resumen, como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="0a551-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="0a551-121">No dispone de la opción para asignar el certificado.</span><span class="sxs-lookup"><span data-stu-id="0a551-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="0a551-122">Para completar el proceso de asignación del certificado, debe importar el certificado raíz de la entidad de certificación que lo emite y todos los certificados de entidades de certificación intermedias; a continuación, debe asignar el certificado haciendo clic en **Asignar** en la página del Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="0a551-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

