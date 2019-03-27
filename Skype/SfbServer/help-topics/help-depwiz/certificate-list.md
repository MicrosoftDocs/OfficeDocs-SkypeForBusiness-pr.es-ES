---
title: Lista de certificados
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: Para asignar un certificado, seleccione uno en el almacén de certificados local. Haga clic en Siguiente para continuar.
ms.openlocfilehash: 3b8f18c84bbd0b7efba201430255f057556268cf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883738"
---
# <a name="certificate-list"></a><span data-ttu-id="a3613-104">Lista de certificados</span><span class="sxs-lookup"><span data-stu-id="a3613-104">Certificate List</span></span>
 
<span data-ttu-id="a3613-p102">Para asignar un certificado, seleccione uno en el almacén de certificados local. Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="a3613-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="a3613-p103">El certificado o los certificados que figuran en el panel **Seleccionar un certificado en el almacén de certificados local** son certificados válidos que pueden asignarse al uso de certificados que necesita. Haga clic en el botón **Ver detalles del certificado** para confirmar que el certificado que selecciona sea el correcto. En la pestaña **Detalles** de los datos del certificado, puede ver el nombre del sujeto y los nombres alternativos del sujeto designados tal como se configuran en el certificado.</span><span class="sxs-lookup"><span data-stu-id="a3613-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3613-p104">Puede suceder que en el panel de selección no haya ningún certificado. En tal caso, el motivo habitual es que no hay instalado en el servidor de destino ningún certificado raíz de confianza ni de entidad de certificación intermedia para comprobar el certificado, por lo tanto, mantener la cadena de confianza creada por el certificado en la entidad de certificación. Para resolver el problema,  solicite e importe una cadena de confianza, que en general incluye el certificado de la entidad de certificación raíz y los certificados de todas las entidades de certificación intermedias y de emisión de certificados.</span><span class="sxs-lookup"><span data-stu-id="a3613-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

