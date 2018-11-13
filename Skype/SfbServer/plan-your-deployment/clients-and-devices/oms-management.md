---
title: Planificar la administración de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: En este artículo se describe las consideraciones de planeación para el uso conjunto de aplicaciones de administración de operaciones para administrar dispositivos de v2 de sistemas de salón de Skype en su Skype para la implementación de Business Server.
ms.openlocfilehash: 14f6ba95e5b2bcf7619002bb2dbc1e9ae3eb474a
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295629"
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>Planificar la administración de Sistemas de salas de Skype v2 con OMS
 
 En este artículo se describe las consideraciones de planeación para el uso conjunto de aplicaciones de administración de operaciones para administrar dispositivos de v2 de sistemas de salón de Skype en su Skype para la implementación de Business Server.
  
[Conjunto de aplicaciones de administración de operaciones](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview) (OMS) es una colección de servicios de administración que se diseñaron en la nube desde el principio. En lugar de implementar y administrar los recursos locales, los componentes OMS totalmente se hospedan en Azure. Configuración es mínima, y puede ser funcionamiento literalmente en cuestión de minutos. Con algunas tareas de personalización, puede ayudar a en la administración de sistemas de conferencia de sistemas de salón de Skype v2 al proporcionar notificaciones en tiempo real del estado del sistema o errores para sistemas de las salas individuales y potencialmente puede escalar a la administración de miles de sistemas de salón de Skype salas de conferencias v2.
  
En este artículo se proporciona una explicación de los requisitos, diseño y arquitectura y procedimientos recomendados de implementación necesarios para implementar la administración de OMS de dispositivos de conferencia de sistemas de salón de Skype v2 y proporcionan vínculos a artículos detallados sobre la implementación de OMS administración de sistemas de salón de Skype v2 y crítico información de referencia para la administración continua de OMS de salones de sistemas de salón de Skype v2. 
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de administración de SRS con OMS](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación de v2 de sistemas de salón de Skype en el dispositivo de consola escribe eventos en su registro de sucesos de Windows. Una vez que hay un agente OMS instalado, pasa la información a OMS. 
  
Una vez configurado correctamente, analiza OMS la carga JSON en el evento incrustado descripciones para describir cómo funciona cada sistema v2 de sistemas de salón de Skype y qué errores se detectan. 
  
Un administrador con OMS puede obtener las notificaciones de sistemas de salón de Skype v2 sistemas que están sin conexión o se experimentar con la aplicación, la conectividad o errores de hardware así como saber si un sistema debe reiniciarse. El estado de cada sistema se actualiza cada cinco minutos, por lo que estas notificaciones se comportan prácticamente como actualizaciones en tiempo real.
  
## <a name="oms-requirements"></a>Requisitos de OMS

Debe tener una suscripción válida para que OMS pueda usar esta característica. Consulte [Introducción a un área de trabajo de Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) para crear una suscripción para su organización.
  
Debe conocer bien cómo funciona el diseñador de vistas de OMS. Consulte [Vistas de las soluciones de administración en Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views) para ver más detalles.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a OMS, crear personalizado campos (tal como se describe en [Asignar campos personalizados](../../deploy/deploy-clients/with-oms.md#Custom_fields)) necesitan para analizar la información que se van a enviar desde consolas de sistemas de salón de Skype v2. Esto incluye la descripción del esquema de JSON que se documentaron en [comprender las entradas del registro](../../manage/skype-room-systems-v2/oms.md#Telemetry).
    
2. Desarrollar una vista de administración de sistemas de salón de Skype v2 de OMS. Puede [crear un panel de v2 de Skype salón de sistemas mediante el método de importación](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) o [crear un panel de v2 de Skype salón de sistemas de forma manual](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Requisitos de la consola de v2 de Skype salón sistemas individuales

Cada consola v2 de sistemas de salón de Skype es una aplicación que se ejecuta en un dispositivo de superficie 4 en modo de pantalla completa (normalmente, se configura para que sea la única aplicación que puede ejecutar en el dispositivo). Al igual que con cualquier aplicación de Windows, la aplicación de sistemas de salón de Skype v2 escribe eventos tales como errores de hardware y de inicio para el registro de eventos de Windows. Adición de un agente OMS en su dispositivo v2 de sistemas de salón de Skype permite estos eventos a ser archivados por OMS. (Para obtener más información, vea [equipos Windows conectarse con el servicio de registro de análisis en Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents) ).
  
## <a name="ongoing-management"></a>Administración continua

Durante el uso de OMS para administrar los dispositivos de conferencia de sistemas de salón de Skype v2, debe comprender la información contenida en los registros de eventos utilizados por OMS. Para obtener información detallada sobre estos mensajes de estado, vea [Descripción de las entradas del registro](../../manage/skype-room-systems-v2/oms.md#Telemetry) .
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por los sistemas de la sala de Skype v2 y cómo resolverlos (vea la sección titulada [comprender las entradas del registro](../../manage/skype-room-systems-v2/oms.md#Telemetry))
    
## <a name="see-also"></a>Vea también

[Implementar la administración de Sistemas de salas de Skype v2 con OMS](../../deploy/deploy-clients/with-oms.md)
  
[Administración de los dispositivos de Sistemas de salas de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md)