---
title: Solicitud de certificado (devuelto)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'La página de estado de la solicitud de certificado en línea presenta información importante que resulta de la creación y la emisión satisfactoria de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica de forma única el certificado. De forma predeterminada, la casilla asignar este certificado a los usos de certificados de Skype empresarial Server está seleccionada. Si hace clic en finalizar, el certificado se asignará automáticamente a Skype empresarial Server para los propósitos que definió durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los propósitos en los que se asignará el certificado son los siguientes:'
ms.openlocfilehash: 1fce25992e6509fe10715f80f4121e08c6734be2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794299"
---
# <a name="certificate-request-returned"></a>Solicitud de certificado (devuelto)
 
La página de estado de la **solicitud de certificado en línea** presenta información importante que resulta de la creación y la emisión satisfactoria de la solicitud de certificado en línea. Esta página proporciona la huella digital del certificado que identifica de forma única el certificado. De forma predeterminada, la casilla **asignar este certificado a los usos de certificados de Skype empresarial Server** está seleccionada. Si hace clic en **Finalizar**, el certificado se asignará automáticamente a Skype empresarial Server para los propósitos que definió durante los pasos de creación de la solicitud de certificado. De forma predeterminada, los propósitos en los que se asignará el certificado son los siguientes:
  
- Valor predeterminado del servidor para la seguridad de la capa de transporte mutuo (MTLS): conexiones a clientes y otros servidores
    
- Servicios Web internos: conexiones de cliente y servidor en el sitio de servicios Web interno para seguridad de la capa de transporte/capa de sockets seguros (TLS/SSL)
    
- Servicios web externa: conexiones de cliente y servidor en el sitio de servicios Web externo para TLS/SSL
    
Haga clic en **Ver detalles** del certificado para ver el certificado para confirmar que las propiedades del certificado son las previstas y que el certificado está listo para aplicarse y usarse en el servidor.
  
Haga clic en **Finalizar** para completar el proceso de solicitud de certificado en línea. Si seleccionó la casilla de verificación **asignar este certificado a los usos del certificado de Skype empresarial Server**, el certificado se asignará automáticamente. Si opta por desactivar esta casilla, debe asignar el certificado en un paso independiente. 
  
> [!IMPORTANT]
> Si el certificado raíz de la entidad de certificación (CA) de emisión no se encuentra en el almacén de entidades de certificación raíz de confianza del equipo o si no se encuentran en el almacén adecuado, verá el estado de Resumen, tal y como se muestra en la siguiente imagen. No tiene la opción de asignar el certificado. Para completar el proceso de asignación de certificados, debe importar el certificado raíz de la CA emisora y los certificados de la entidad emisora intermedia y, después, asignar el certificado haciendo clic en **asignar** en la Página principal del Asistente para certificados.
  

