---
title: Solicitud de certificado (devuelto)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'La página de estado de la solicitud de certificado en línea presenta información importante que resulta de la correcta creación y emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica el certificado. De forma predeterminada, se selecciona la casilla de verificación asignar este certificado a Skype para usos de certificado del servidor de empresa. Si hace clic en Finalizar, el certificado se asignará automáticamente a Lync Server 2013 los fines definidos durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los propósitos que se asignará el certificado son:'
ms.openlocfilehash: 392fbdf4cae860152a5ed96e9e347a0c51aa6f70
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-returned"></a><span data-ttu-id="4aec5-107">Solicitud de certificado (devuelto)</span><span class="sxs-lookup"><span data-stu-id="4aec5-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="4aec5-108">La página de **Estado de la solicitud de certificado en línea** presenta información importante que resulta de la correcta creación y emisión de la solicitud de certificado en línea.</span><span class="sxs-lookup"><span data-stu-id="4aec5-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="4aec5-109">Esta página proporciona la huella digital del certificado que identifica el certificado.</span><span class="sxs-lookup"><span data-stu-id="4aec5-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="4aec5-110">De forma predeterminada, se selecciona la casilla de verificación **asignar este certificado a Skype para usos de certificado del servidor de empresa** .</span><span class="sxs-lookup"><span data-stu-id="4aec5-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="4aec5-111">Si hace clic en **Finalizar**, el certificado se asignará automáticamente a Lync Server 2013 los fines definidos durante los pasos de creación de la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="4aec5-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="4aec5-112">De forma predeterminada, los propósitos que se asignará el certificado son:</span><span class="sxs-lookup"><span data-stu-id="4aec5-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="4aec5-113">Servidor predeterminado para mutuo transporte capa de seguridad (MTLS) - conexiones con clientes y otros servidores</span><span class="sxs-lookup"><span data-stu-id="4aec5-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="4aec5-114">Servicios Web internos - conexiones de cliente y servidor en el Web interno sitio servicios de Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="4aec5-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="4aec5-115">Servicios Web externos - conexiones de cliente y servidor en el Web externo sitio servicios de TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="4aec5-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="4aec5-116">Haga clic en la **Vista Detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado son las previstas, y que el certificado está listo para ser aplicado y puesto en uso en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4aec5-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="4aec5-117">Haga clic en **Finalizar** para completar el proceso de solicitud de certificados en línea.</span><span class="sxs-lookup"><span data-stu-id="4aec5-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="4aec5-118">Si ha seleccionado la casilla de verificación **asignar este certificado a Skype para usos de certificado del servidor de empresa**, se asignará automáticamente el certificado.</span><span class="sxs-lookup"><span data-stu-id="4aec5-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="4aec5-119">Si opta por desactivar esta casilla de verificación, debe asignar el certificado en un paso independiente.</span><span class="sxs-lookup"><span data-stu-id="4aec5-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4aec5-120">Si el emisor certificados de raíz de entidad emisora (CA) no está en el almacén del equipo autoridad de certificación raíz de confianza, o si los certificados de CA intermedios no están en el almacén correcto, verá el estado del resumen, tal como se ilustra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="4aec5-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="4aec5-121">No tiene la opción de asignar el certificado.</span><span class="sxs-lookup"><span data-stu-id="4aec5-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="4aec5-122">Para completar el proceso de asignación de certificados, debe importar el certificado raíz de CA emisora y los certificados de CA intermedios y, a continuación, asignar el certificado, haga clic en **asignar** en la página principal del Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="4aec5-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

