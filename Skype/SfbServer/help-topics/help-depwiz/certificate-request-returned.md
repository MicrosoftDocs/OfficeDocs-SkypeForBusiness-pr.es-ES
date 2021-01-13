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
# <a name="certificate-request-returned"></a>Solicitud de certificados (devuelto)
 
La página **Estado de solicitud del certificado en línea** muestra información importante que surge de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica al certificado de forma exclusiva. De forma predeterminada, la casilla Asignar **este certificado a los usos** de certificados de Skype Empresarial Server está activada. Si hace clic **en Finalizar,** el certificado se asignará automáticamente a Lync Server 2013 para los fines que haya definido durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los usos que se asignan al certificado son:
  
- Valor predeterminado del servidor para seguridad de la capa de transporte mutua (MTLS): conexiones a clientes y otros servidores
    
- Servicios web internos: conexiones de cliente y servidor en el sitio de servicios web internos para Seguridad de la capa de transporte/Capa de sockets seguros (TLS/SSL)
    
- Servicios web externos: conexiones de cliente y servidor en el sitio de servicios web externos para TLS/SSL
    
Haga clic en **Ver detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado sean las que ha previsto y comprobar que el certificado esté listo para aplicarse y ponerse en uso en el servidor.
  
Haga clic en **Finalizar** para completar el proceso de solicitud del certificado en línea. Si ha seleccionado la casilla Asignar este certificado a los usos de certificados de **Skype Empresarial Server,** el certificado se asignará automáticamente. Si decide desactivar esta casilla, el certificado debe asignarse en un paso aparte. 
  
> [!IMPORTANT]
> Si el certificado raíz de la entidad de certificación (CA) emisora no está en el almacén de entidades de certificación raíz de confianza del equipo, o si los certificados de CA intermedias no están en el almacén adecuado, verá el estado de resumen, como se muestra en la imagen siguiente. No dispone de la opción para asignar el certificado. Para completar el proceso de asignación del certificado, debe importar el certificado raíz de la entidad de certificación que lo emite y todos los certificados de entidades de certificación intermedias; a continuación, debe asignar el certificado haciendo clic en **Asignar** en la página del Asistente para certificados.
  

