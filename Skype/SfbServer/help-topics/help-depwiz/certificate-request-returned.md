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
# <a name="certificate-request-returned"></a>Solicitud de certificado (devuelto)
 
La página de **Estado de la solicitud de certificado en línea** presenta información importante que resulta de la correcta creación y emisión de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica el certificado. De forma predeterminada, se selecciona la casilla de verificación **asignar este certificado a Skype para usos de certificado del servidor de empresa** . Si hace clic en **Finalizar**, el certificado se asignará automáticamente a Lync Server 2013 los fines definidos durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los propósitos que se asignará el certificado son:
  
- Servidor predeterminado para mutuo transporte capa de seguridad (MTLS) - conexiones con clientes y otros servidores
    
- Servicios Web internos - conexiones de cliente y servidor en el Web interno sitio servicios de Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Servicios Web externos - conexiones de cliente y servidor en el Web externo sitio servicios de TLS/SSL
    
Haga clic en la **Vista Detalles del certificado** para ver el certificado para confirmar que las propiedades del certificado son las previstas, y que el certificado está listo para ser aplicado y puesto en uso en el servidor.
  
Haga clic en **Finalizar** para completar el proceso de solicitud de certificados en línea. Si ha seleccionado la casilla de verificación **asignar este certificado a Skype para usos de certificado del servidor de empresa**, se asignará automáticamente el certificado. Si opta por desactivar esta casilla de verificación, debe asignar el certificado en un paso independiente. 
  
> [!IMPORTANT]
> Si el emisor certificados de raíz de entidad emisora (CA) no está en el almacén del equipo autoridad de certificación raíz de confianza, o si los certificados de CA intermedios no están en el almacén correcto, verá el estado del resumen, tal como se ilustra en la siguiente imagen. No tiene la opción de asignar el certificado. Para completar el proceso de asignación de certificados, debe importar el certificado raíz de CA emisora y los certificados de CA intermedios y, a continuación, asignar el certificado, haga clic en **asignar** en la página principal del Asistente para certificados.
  

