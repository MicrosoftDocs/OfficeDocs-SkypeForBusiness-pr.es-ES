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
description: 'La página Estado de solicitud del certificado en línea muestra información importante que surge de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica al certificado de forma exclusiva. De forma predeterminada, se selecciona la casilla Asignar este certificado Skype Empresarial Server usos de certificados. Si hace clic en Finalizar, el certificado se asignará automáticamente a Lync Server 2013 para los fines que haya definido durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los usos que se asignan al certificado son:'
ms.openlocfilehash: bf3dfc7e37d81a85e66fa428504b48096f3da6f4c0cffcb22685f19d0146a7d7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301756"
---
# <a name="certificate-request-returned"></a>Solicitud de certificados (devuelto)
 
La página **Estado de solicitud del certificado en línea** muestra información importante que surge de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica al certificado de forma exclusiva. De forma predeterminada, se selecciona la casilla Asignar **este certificado Skype Empresarial Server usos de** certificados. Si hace clic **en Finalizar,** el certificado se asignará automáticamente a Lync Server 2013 para los fines que definió durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los usos que se asignan al certificado son:
  
- Server Default for Mutual Transport Layer Security (MTLS): conexiones a clientes y otros servidores
    
- Servicios web internos: conexiones de cliente y servidor en el sitio de servicios web internos para la capa de transporte Seguridad/Capa de sockets seguros (TLS/SSL)
    
- Servicios web externos: conexiones de cliente y servidor en el sitio de servicios web externos para TLS/SSL
    
Haga clic en **Ver detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado sean las que ha previsto y comprobar que el certificado esté listo para aplicarse y ponerse en uso en el servidor.
  
Haga clic en **Finalizar** para completar el proceso de solicitud del certificado en línea. Si ha seleccionado la casilla Asignar este certificado Skype Empresarial Server **usos** de certificados, el certificado se asignará automáticamente. Si decide desactivar esta casilla, el certificado debe asignarse en un paso aparte. 
  
> [!IMPORTANT]
> Si el certificado raíz de la entidad emisora de certificados (CA) no está en el almacén de entidades de certificación raíz de confianza del equipo o si los certificados de ca intermedios no están en el almacén adecuado, verá el estado de resumen, como se muestra en la siguiente imagen. No dispone de la opción para asignar el certificado. Para completar el proceso de asignación del certificado, debe importar el certificado raíz de la entidad de certificación que lo emite y todos los certificados de entidades de certificación intermedias; a continuación, debe asignar el certificado haciendo clic en **Asignar** en la página del Asistente para certificados.
  

