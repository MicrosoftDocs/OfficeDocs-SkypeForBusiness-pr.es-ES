---
title: Lista de certificados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
ROBOTS: NOINDEX, NOFOLLOW
description: Para asignar un certificado, seleccione un certificado del almacén de certificados local. Haga clic en Siguiente para continuar.
ms.openlocfilehash: 0165afc7a90983855dab8f5a0a2d1c7e44385318
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808920"
---
# <a name="certificate-list"></a><span data-ttu-id="99377-104">Lista de certificados</span><span class="sxs-lookup"><span data-stu-id="99377-104">Certificate List</span></span>
 
<span data-ttu-id="99377-105">Para asignar un certificado, seleccione un certificado del almacén de certificados local.</span><span class="sxs-lookup"><span data-stu-id="99377-105">To assign a certificate, select a certificate from the local certificate store.</span></span> <span data-ttu-id="99377-106">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="99377-106">Click **Next** to continue.</span></span>
  
<span data-ttu-id="99377-p103">El certificado o los certificados que figuran en el panel **Seleccionar un certificado en el almacén de certificados local.** son certificados válidos que pueden asignarse al uso de certificados que necesita. Haga clic en el botón **Ver detalles del certificado** para confirmar que el certificado que selecciona sea el correcto. En la pestaña **Detalles** de los datos del certificado, puede ver el nombre del sujeto y los nombres alternativos del sujeto designados tal como se configuran en el certificado.</span><span class="sxs-lookup"><span data-stu-id="99377-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="99377-p104">Puede suceder que en el panel de selección no haya ningún certificado. En tal caso, el motivo habitual es que no hay instalados en el servidor de destino ningún certificado raíz de confianza ni de entidad de certificación intermedia para comprobar el certificado, por lo tanto, mantener la cadena de confianza creada por el certificado en la entidad de certificación. Para resolver el problema,  solicite e importe una cadena de confianza, que en general incluye el certificado de la entidad de certificación raíz y los certificados de todas las entidades de certificación intermedias y de emisión de certificados.</span><span class="sxs-lookup"><span data-stu-id="99377-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

