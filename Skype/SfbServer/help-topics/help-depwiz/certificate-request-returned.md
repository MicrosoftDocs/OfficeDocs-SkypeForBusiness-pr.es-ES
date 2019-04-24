---
title: Solicitud de certificado (devuelto)
ms.reviewer: ''
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
description: 'La página de estado de solicitud de certificado en línea presenta información importante que da como resultado de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica de forma exclusiva el certificado. De forma predeterminada, se selecciona la casilla de verificación asignar este certificado a Skype para usos de certificados de servidor empresarial. Si hace clic en Finalizar, el certificado se asignará automáticamente a Lync Server 2013 para los fines que ha definido en los pasos de creación de la solicitud de certificado. De forma predeterminada, con el fin de que se asignará el certificado es:'
ms.openlocfilehash: 61e62216cd582a07b95a51d05033482699ca2f3d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201356"
---
# <a name="certificate-request-returned"></a>Solicitud de certificado (devuelto)
 
La página de **Estado de solicitud de certificado en línea** presenta información importante que da como resultado de la creación correcta y la emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica de forma exclusiva el certificado. De forma predeterminada, se selecciona la casilla de verificación **asignar este certificado a Skype para usos de certificados de servidor empresarial** . Si hace clic en **Finalizar**, el certificado se asignará automáticamente a Lync Server 2013 para los fines que ha definido en los pasos de creación de la solicitud de certificado. De forma predeterminada, con el fin de que se asignará el certificado es:
  
- Servidor predeterminado para Mutual Transport capa de seguridad (MTLS) - conexiones a clientes y otros servidores
    
- Servicios Web internos - conexiones de cliente y servidor en el sitio Web interno sitio de servicios de Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Servicios Web externos - conexiones de cliente y servidor en el sitio Web externo sitio de servicios de TLS/SSL
    
Haga clic en la **Vista de detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado son lo que pretende y que el certificado está listo para ser aplicado y poner en uso en el servidor.
  
Haga clic en **Finalizar** para completar el proceso de solicitud de certificado en línea. Si ha seleccionado la casilla de verificación **asignar este certificado a Skype para usos de certificados de servidor empresarial**, se asignará automáticamente el certificado. Si opta por desactive esta casilla de verificación, debe asignar el certificado en un paso independiente. 
  
> [!IMPORTANT]
> Si el certificado de raíz de entidad de certificación (CA) de certificación emisora no está en el almacén del equipo entidad de certificación raíz de confianza, o si los certificados de CA intermedios no están en el almacén correcto, verá el estado del resumen, tal como se ilustra en la siguiente imagen. No tiene la opción para asignar el certificado. Para completar el proceso de asignación de certificados, debe importar el certificado raíz de entidad de certificación emisora y los certificados de CA intermedios y, a continuación, asignar el certificado, haga clic en **asignar** en la página principal del Asistente para certificados.
  

