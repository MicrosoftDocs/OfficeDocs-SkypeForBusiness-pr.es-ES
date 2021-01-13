---
title: Procedimientos recomendados para su infraestructura principal en Skype Empresarial Server
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
description: Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no solo la infraestructura de Skype Empresarial Server, sino también toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype Empresarial Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832250"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedimientos recomendados para su infraestructura principal en Skype Empresarial Server
 
Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no solo la infraestructura de Skype Empresarial Server, sino también toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype Empresarial Server.
  
To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:
  
- Mantenga los servidores actualizados con las actualizaciones de seguridad. Al suscribirse al Servicio de notificación de seguridad de Microsoft (Microsoft Security Notification Service), se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft. Para suscribirse, vaya al sitio web de notificaciones [de seguridad técnica de Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=145202)
    
- Asegúrese de que los derechos de acceso estén correctamente configurados.
    
- Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.
    
- Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos donde instale Skype Empresarial Server.
    
- Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.
    
- Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores. Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información muy confidencial, como es el caso de las claves de cifrado privadas.
    

