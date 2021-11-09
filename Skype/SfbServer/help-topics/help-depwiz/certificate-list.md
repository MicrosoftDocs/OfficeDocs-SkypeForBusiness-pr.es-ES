---
title: Lista de certificados
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: Para asignar un certificado, seleccione un certificado en el almacén de certificados local. Haga clic en Siguiente para continuar.
ms.openlocfilehash: 3abba1092a4f7a0d7898c3ab1924e69eb2a62a60
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854664"
---
# <a name="certificate-list"></a>Lista de certificados
 
Para asignar un certificado, seleccione un certificado en el almacén de certificados local. Haga clic en **Siguiente** para continuar.
  
El certificado o los certificados que figuran en el panel **Seleccionar un certificado en el almacén de certificados local.** son certificados válidos que pueden asignarse al uso de certificados que necesita. Haga clic en el botón **Ver detalles del certificado** para confirmar que el certificado que selecciona sea el correcto. En la pestaña **Detalles** de los datos del certificado, puede ver el nombre del sujeto y los nombres alternativos del sujeto designados tal como se configuran en el certificado.
  
> [!IMPORTANT]
> Puede suceder que en el panel de selección no haya ningún certificado. En tal caso, el motivo habitual es que no hay instalados en el servidor de destino ningún certificado raíz de confianza ni de entidad de certificación intermedia para comprobar el certificado, por lo tanto, mantener la cadena de confianza creada por el certificado en la entidad de certificación. Para resolver el problema,  solicite e importe una cadena de confianza, que en general incluye el certificado de la entidad de certificación raíz y los certificados de todas las entidades de certificación intermedias y de emisión de certificados. 
  

