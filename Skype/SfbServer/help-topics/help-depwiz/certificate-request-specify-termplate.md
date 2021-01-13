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
# <a name="certificate-request-specify-termplate"></a>Solicitud de certificados (especificar plantilla)
 
La página **Especificar plantilla de certificado alternativa** permite definir una plantilla de certificado distinta de la plantilla de certificado WebServer que se usa de forma predeterminada. Seleccione la casilla de verificación **Usar plantilla de certificado alternativa para entidad de certificación seleccionada**; a continuación, en el cuadro de texto **Nombre de plantilla de certificado** defina el nombre de la plantilla de certificado alternativa Debe usar el mismo nombre de la plantilla que esté definida en la entidad de certificación. Haga clic en **Atrás** para retroceder a la página anterior. Haga clic en **Cancelar** para finalizar el proceso de solicitud de certificado.
  
> [!CAUTION]
> Es conveniente usar esta opción solo si la entidad de certificación pública le indica que debe emplear una determinada plantilla que está definida en su sistema para la emisión de certificados. En el certificado que emite la entidad de certificación interna, el administrador de certificados debe indicarle el nombre que debe usar para la plantilla de certificado alternativa. Esta opción es sumamente útil cuando la organización haya definido una nueva plantilla de WebServer y haya deshabilitado la plantilla predeterminada de WebServer. 
  

