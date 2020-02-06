---
title: Lista de certificados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: Para asignar un certificado, seleccione uno en el almacén de certificados local. Haga clic en Siguiente para continuar.
ms.openlocfilehash: ea7b17b3632fe91f67eeed214c866fbc1df57a3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823934"
---
# <a name="certificate-list"></a>Lista de certificados
 
Para asignar un certificado, seleccione uno en el almacén de certificados local. Haga clic en **Siguiente** para continuar.
  
El certificado o los certificados que figuran en el panel **Seleccionar un certificado en el almacén de certificados local** son certificados válidos que pueden asignarse al uso de certificados que necesita. Haga clic en el botón **Ver detalles del certificado** para confirmar que el certificado que selecciona sea el correcto. En la pestaña **Detalles** de los datos del certificado, puede ver el nombre del sujeto y los nombres alternativos del sujeto designados tal como se configuran en el certificado.
  
> [!IMPORTANT]
> Puede suceder que en el panel de selección no haya ningún certificado. En tal caso, el motivo habitual es que no hay instalado en el servidor de destino ningún certificado raíz de confianza ni de entidad de certificación intermedia para comprobar el certificado, por lo tanto, mantener la cadena de confianza creada por el certificado en la entidad de certificación. Para resolver el problema,  solicite e importe una cadena de confianza, que en general incluye el certificado de la entidad de certificación raíz y los certificados de todas las entidades de certificación intermedias y de emisión de certificados. 
  

