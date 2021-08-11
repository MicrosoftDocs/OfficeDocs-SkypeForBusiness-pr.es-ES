---
title: Procedimientos recomendados para la infraestructura principal en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no solo a Skype Empresarial Server infraestructura, sino también a toda la red. Si no ha implementado estos procedimientos, se recomienda hacerlo antes de implementar Skype Empresarial Server.
ms.openlocfilehash: 21173b6fe924938ebabfecc0c36b3abdce092b4c9e902284530ec47d2c1ca8bf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318706"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedimientos recomendados para la infraestructura principal en Skype Empresarial Server
 
Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no solo a Skype Empresarial Server infraestructura, sino también a toda la red. Si no ha implementado estos procedimientos, se recomienda hacerlo antes de implementar Skype Empresarial Server.
  
To help protect the servers in your Skype Empresarial Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:
  
- Mantenga los servidores actualizados con las actualizaciones de seguridad. Al suscribirse al Servicio de notificación de seguridad de Microsoft (Microsoft Security Notification Service), se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft. Para suscribirse, vaya al sitio web notificaciones de seguridad técnica [de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Asegúrese de que los derechos de acceso estén correctamente configurados.
    
- Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.
    
- Se recomienda deshabilitar los servicios del sistema operativo Windows Server que no son necesarios en los equipos donde se instala Skype Empresarial Server.
    
- Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.
    
- Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores. Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información muy confidencial, como es el caso de las claves de cifrado privadas.
    

