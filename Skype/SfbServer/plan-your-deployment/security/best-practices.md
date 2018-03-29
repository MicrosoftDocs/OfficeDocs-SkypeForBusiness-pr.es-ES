---
title: Procedimientos recomendados para la infraestructura básica en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no sólo su Skype para infraestructura de servidores empresariales, sino también a toda la red. Si no ha implementado estas prácticas, se recomienda que lo haga antes de implementar Skype para Business Server.
ms.openlocfilehash: 9d79f98ebc66807f21f8d1eef468efc400dd5fbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server-2015"></a>Procedimientos recomendados para la infraestructura básica en Skype Empresarial Server 2015
 
Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no sólo su Skype para infraestructura de servidores empresariales, sino también a toda la red. Si no ha implementado estas prácticas, se recomienda que lo haga antes de implementar Skype para Business Server.
  
Para ayudar a proteger los servidores de su Skype para la implementación de Business Server frente a daños accidentales o intencionados que podrían producir en el tiempo de inactividad, tome las siguientes precauciones:
  
- Mantenga actualizados los servidores con las actualizaciones de seguridad. Al suscribirse al Servicio de notificación de seguridad de Microsoft, se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft. Para suscribirse, visite el [sitio Web de Microsoft Technical Security Notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Asegúrese de que los derechos de acceso estén correctamente configurados.
    
- Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.
    
- Recomendamos que deshabilite los servicios del sistema operativo Windows Server que no sean necesarios en los equipos donde instale Skype para Business Server.
    
- Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.
    
- Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores. Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información confidencial muy delicada, como es el caso de las claves de cifrado privadas.
    

