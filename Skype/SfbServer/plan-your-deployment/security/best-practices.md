---
title: Procedimientos recomendados para la infraestructura básica de Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no sólo de su Skype para la infraestructura del servidor empresarial, sino también de toda la red. Si no se han implementado estas prácticas, se recomienda hacerlo antes de implementar Skype para Business Server.
ms.openlocfilehash: f88461e7563d28dce145d01a9b47a0176ef0d97f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996597"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedimientos recomendados para la infraestructura básica de Skype para Business Server
 
Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no sólo de su Skype para la infraestructura del servidor empresarial, sino también de toda la red. Si no se han implementado estas prácticas, se recomienda hacerlo antes de implementar Skype para Business Server.
  
Para ayudar a proteger los servidores en su Skype para la implementación de servidor empresarial de daños accidentales o intencionados que pudieran provocar tiempos de inactividad, adopte las precauciones siguientes:
  
- Mantenga actualizados los servidores con las actualizaciones de seguridad. Al suscribirse al Servicio de notificación de seguridad de Microsoft, se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft. Para suscribirse, visite el [sitio Web de notificaciones de seguridad técnica de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Asegúrese de que los derechos de acceso estén correctamente configurados.
    
- Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.
    
- Se recomienda que deshabilite los servicios del sistema operativo Windows Server que no sean necesarios en los equipos donde instale Skype para Business Server.
    
- Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.
    
- Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores. Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información confidencial muy delicada, como es el caso de las claves de cifrado privadas.
    

