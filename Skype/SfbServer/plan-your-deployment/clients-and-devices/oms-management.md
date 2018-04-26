---
title: Planificar la administración de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: " En este tema se tratan las consideraciones de planificación para usar Operations Management Suite para administrar los dispositivos de Sistemas de salas de Skype v2 en su implementación de Skype Empresarial Server 2015."
ms.openlocfilehash: b117b243b638c9e06b21901f14515b51d6931d23
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>Planificar la administración de Sistemas de salas de Skype v2 con OMS
 
  En este tema se tratan las consideraciones de planificación para usar Operations Management Suite para administrar los dispositivos de Sistemas de salas de Skype v2 en su implementación de Skype Empresarial Server 2015.
  
[Operations Management Suite](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview) (OMS) es un conjunto de servicios de administración que se diseñaron en la nube desde el principio. En lugar de implementar y administrar los recursos locales, componentes OMS se alojan completamente en Azure. Configuración es mínima, y estará a pleno literalmente en cuestión de minutos. Con algunas tareas de personalización, puede ayudar en la administración de sistemas de conferencia de sistemas de salas de Skype v2 al proporcionar notificaciones en tiempo real de fallas o estado del sistema para sistemas de las salas individuales y potencialmente puede escalar para administrar miles de sistemas de salas de Skype salas de conferencia v2.
  
Este artículo proporciona una descripción de los requisitos, diseño y arquitectura y mejores prácticas de implementación necesarias para implementar la administración de la OMS de dispositivos de sistemas de salas de Skype v2 conferencia y proporciona vínculos a artículos detallados sobre la implementación de OMS administración de sistemas de salas de Skype v2 e información de referencia esenciales para la administración continua de OMS de salas de sistemas de salas de Skype v2. 
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de administración de SRS con OMS](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación de sistemas de salas de Skype v2 en el dispositivo de consola escribe sucesos en el registro de sucesos de Windows. Una vez que hay un agente OMS instalado, pasa la información a OMS. 
  
Una vez configurado correctamente, analiza OMS la carga JSON incrustado en el evento para describir el funcionamiento de cada sistema de sistemas de salas de Skype v2 y se detectan los errores. 
  
Un administrador usar OMS puede obtener notificaciones de los sistemas de salas de Skype v2 sistemas que estén desconectados o está experimentando errores de hardware, conectividad o de la aplicación así como saber si un sistema necesita que se reinicie. El estado de cada sistema se actualiza cada cinco minutos, por lo que estas notificaciones se comportan prácticamente como actualizaciones en tiempo real.
  
## <a name="oms-requirements"></a>Requisitos de OMS

Debe tener una suscripción válida para que OMS pueda usar esta característica. Consulte [Introducción a un área de trabajo de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) para crear una suscripción para su organización.
  
Debe conocer bien cómo funciona el diseñador de vistas de OMS. Ver [vistas en soluciones de administración de Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views) para los detalles.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a OMS, crear personalizado campos (como se describe en [Asignar campos personalizados](../../deploy/deploy-clients/with-oms.md#Custom_fields)) necesarios para analizar la información que se enviará desde consolas de sistemas de salas de Skype v2. Esto incluye comprender el esquema JSON documentado en [comprender las entradas del registro](../../manage/skype-room-systems-v2/oms.md#Telemetry).
    
2. Desarrollar una vista de administración de sistemas de salas de Skype v2 de OMS. Puede [crear un escritorio digital v2 de sistemas de salas de Skype utilizando el método de importación](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) o [crear un panel de sistemas de salas de Skype v2 manualmente](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Requisitos de la consola individuales sistemas de salas de Skype v2

Cada consola v2 de sistemas de salas de Skype es una aplicación que se ejecuta en un dispositivo de superficie 4 en modo de pantalla completa (normalmente, está configurado para que sea la única aplicación que puede ejecutar en el dispositivo). Al igual que con cualquier aplicación de Windows, la aplicación de sistemas de salas de Skype v2 escribe eventos como fallas de hardware y de inicio en el registro de sucesos de Windows. Agregar a un agente OMS en el dispositivo de los sistemas de salas de Skype v2 permite estos eventos ser recopilados por OMS. (Consulte [equipos Windows conecte con el servicio de análisis de registro en Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents) para más detalles).
  
## <a name="ongoing-management"></a>Administración continua

Mientras utiliza OMS para administrar los dispositivos de sistemas de salas de Skype v2 conferencia, debe comprender la información contenida en los registros de eventos utilizados por OMS. Para obtener detalles acerca de estos mensajes de estado, consulte [comprender las entradas del registro](../../manage/skype-room-systems-v2/oms.md#Telemetry) .
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por los sistemas de salas de Skype v2 y cómo resolverlos (vea la sección [comprender las entradas del registro](../../manage/skype-room-systems-v2/oms.md#Telemetry))
    
## <a name="see-also"></a>Vea también

#### 

[Implementar la administración de sistemas de salas de Skype v2 con OMS](../../deploy/deploy-clients/with-oms.md)
  
[Administrar dispositivos de sistemas de salas de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md)

