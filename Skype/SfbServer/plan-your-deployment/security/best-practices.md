---
title: Procedimientos recomendados para su infraestructura básica en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Es probable que ya haya tomado las medidas para diseñar la tolerancia a errores en el sistema, con prácticas tales como garantizar la redundancia de hardware, protegerse contra la pérdida de energía, instalar de forma rutinaria actualizaciones de seguridad y medidas antivirus, y supervisar la actividad del servidor. Estas prácticas no solo benefician su infraestructura de servidor de Skype empresarial, sino también de toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype empresarial Server.
ms.openlocfilehash: c1f6a6ebe31276b8dbcd9037fa373baffc055fde
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296969"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedimientos recomendados para su infraestructura básica en Skype empresarial Server
 
Es probable que ya haya tomado las medidas para diseñar la tolerancia a errores en el sistema, con prácticas tales como garantizar la redundancia de hardware, protegerse contra la pérdida de energía, instalar de forma rutinaria actualizaciones de seguridad y medidas antivirus, y supervisar la actividad del servidor. Estas prácticas no solo benefician su infraestructura de servidor de Skype empresarial, sino también de toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype empresarial Server.
  
Para ayudar a proteger los servidores de su implementación de Skype empresarial Server de daños accidentales o intencionados que puedan dar lugar a un tiempo de inactividad, tome las siguientes precauciones:
  
- Mantenga sus servidores al día con las actualizaciones de seguridad. Suscribirse al servicio de notificaciones de seguridad de Microsoft le ayuda a recibir notificaciones inmediatas de versiones de boletines de seguridad para cualquier producto de Microsoft. Para suscribirse, vaya al [sitio web de notificaciones de seguridad técnica de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Asegúrese de que los derechos de acceso están configurados correctamente.
    
- Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que el software antivirus adecuado esté instalado en todos los servidores. Mantenga el software actualizado con los últimos archivos de firma de virus. Use la característica de actualización automática de su aplicación antivirus para mantener actualizadas las firmas de virus.
    
- Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos en los que instala Skype empresarial Server.
    
- Cifre los sistemas operativos y las unidades de disco en los que los datos se almacenan con un sistema de cifrado de volumen completo, a menos que pueda garantizar un control completo y constante de los servidores, el aislamiento físico total y la retirada correcta y segura de disco reemplazado o fallido discos.
    
- Deshabilite todos los puertos de acceso directo a memoria (DMA) externos del servidor, a menos que pueda garantizar un control muy estricto sobre el acceso físico a los servidores. Los ataques basados en DMA, que se pueden iniciar con bastante facilidad, pueden exponer información muy confidencial, como las claves de cifrado privadas.
    

