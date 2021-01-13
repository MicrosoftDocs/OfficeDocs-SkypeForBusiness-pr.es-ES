---
title: Solicitud certificado (especificar plantilla)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
description: La página Especificar plantilla de certificado alternativa permite definir una plantilla de certificado que no sea la plantilla de certificado WebServer que se usa de forma predeterminada. Active la casilla Usar plantilla de certificado alternativa para la entidad de certificación seleccionada y, a continuación, defina el nombre de la plantilla de certificado alternativa en el cuadro de texto Nombre de plantilla de certificado. Debe usar el nombre de la plantilla tal como se define en la entidad de certificación (CA). Haga clic en Atrás para volver a la página anterior. Haga clic en Cancelar para finalizar el proceso de solicitud de certificado.
ms.openlocfilehash: 18617077c6e8633db5e6a05b214c922985d14898
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805130"
---
# <a name="certificate-request-specify-termplate"></a><span data-ttu-id="cc68f-107">Solicitud de certificados (especificar plantilla)</span><span class="sxs-lookup"><span data-stu-id="cc68f-107">Certificate Request (Specify Termplate)</span></span>
 
<span data-ttu-id="cc68f-p102">La página **Especificar plantilla de certificado alternativa** permite definir una plantilla de certificado distinta de la plantilla de certificado WebServer que se usa de forma predeterminada. Seleccione la casilla de verificación **Usar plantilla de certificado alternativa para entidad de certificación seleccionada**; a continuación, en el cuadro de texto **Nombre de plantilla de certificado** defina el nombre de la plantilla de certificado alternativa Debe usar el mismo nombre de la plantilla que esté definida en la entidad de certificación. Haga clic en **Atrás** para retroceder a la página anterior. Haga clic en **Cancelar** para finalizar el proceso de solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="cc68f-p102">The **Specify Alternate Certificate Template** page enables you to define a certificate template other than the WebServer certificate template that is used by default. Select the check box **Use alternate certificate template for selected certification authority**, and then define the name of the alternate certificate template in the text box **Certificate template name**. You must use the name of the template as it is defined in the certification authority (CA). Click **Back** to go back to the previous page. Click **Cancel** to end the certificate request process.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="cc68f-p103">Es conveniente usar esta opción solo si la entidad de certificación pública le indica que debe emplear una determinada plantilla que está definida en su sistema para la emisión de certificados. En el certificado que emite la entidad de certificación interna, el administrador de certificados debe indicarle el nombre que debe usar para la plantilla de certificado alternativa. Esta opción es sumamente útil cuando la organización haya definido una nueva plantilla de WebServer y haya deshabilitado la plantilla predeterminada de WebServer.</span><span class="sxs-lookup"><span data-stu-id="cc68f-p103">You should use this option only if you are advised by your public CA that you should use a specific template that is defined on their system for issuing certificates. If the certificate is being issued by your internal CA, your CA administrator should advise you what name to use for the alternate certificate template. This option is extremely valuable in cases where your organization has defined a new WebServer template and has disabled the default WebServer template.</span></span> 
  

