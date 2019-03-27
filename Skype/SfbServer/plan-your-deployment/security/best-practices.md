---
title: Procedimientos recomendados para la infraestructura básica de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Probablemente ya ha dado los pasos para diseñar tolerancia a errores en el sistema, utilizando recomendados, que garantiza la redundancia de hardware, como la protección contra la pérdida de energía, rutinariamente instalar actualizaciones de seguridad y medidas antivirus y la actividad del servidor de supervisión. Estas prácticas benefician no sólo de su Skype para la infraestructura del servidor empresarial, sino también de toda la red. Si no se han implementado estas prácticas, se recomienda hacerlo antes de implementar Skype para Business Server.
ms.openlocfilehash: 86d18e1d9d34b5f65f4cb938e13a9829af1646bb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885809"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedimientos recomendados para la infraestructura básica de Skype para Business Server
 
Probablemente ya ha dado los pasos para diseñar tolerancia a errores en el sistema, utilizando recomendados, que garantiza la redundancia de hardware, como la protección contra la pérdida de energía, rutinariamente instalar actualizaciones de seguridad y medidas antivirus y la actividad del servidor de supervisión. Estas prácticas benefician no sólo de su Skype para la infraestructura del servidor empresarial, sino también de toda la red. Si no se han implementado estas prácticas, se recomienda hacerlo antes de implementar Skype para Business Server.
  
Para ayudar a proteger los servidores en su Skype para la implementación de servidor empresarial de daños accidentales o intencionados que pudieran provocar tiempos de inactividad, adopte las precauciones siguientes:
  
- Mantenga los servidores actualizados con las actualizaciones de seguridad. Suscribirse a Microsoft Security Notification Service ayuda a garantizar que recibirá notificación inmediata de boletines de seguridad para los productos de Microsoft. Para suscribirse, visite el [sitio Web de notificaciones de seguridad técnica de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Asegúrese de que los derechos de acceso estén configurados correctamente.
    
- Mantenga los servidores en un entorno físico que impida el acceso no autorizado. Asegúrese de que esté instalado un software antivirus adecuado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilizar la característica de actualización automática de la aplicación antivirus para mantener los firmas del antivirus actual.
    
- Se recomienda que deshabilite los servicios del sistema operativo Windows Server que no sean necesarios en los equipos donde instale Skype para Business Server.
    
- Cifrar sistemas operativos y unidades de disco donde se almacenan los datos con un sistema de cifrado de volumen completo, a menos que se puede garantizar una constante y completado el control de los servidores, el aislamiento físico total y retirar correcto y seguro de reemplazan o error de disco unidades de disco.
    
- Deshabilitar todos los puertos externos de acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto sobre el acceso a los servidores físico. Los ataques basados en DMA, que pueden iniciarse bastante fácilmente, podrían exponer información muy confidencial, como claves privadas de cifrado.
    

