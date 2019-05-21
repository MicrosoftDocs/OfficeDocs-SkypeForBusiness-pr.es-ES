---
title: Planear la administración de salas de Microsoft Teams con Azure monitor
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: En este artículo se describen las consideraciones de planeación para usar Azure monitor para administrar los dispositivos de salas de Microsoft Teams en su implementación de Skype empresarial o de Teams.
ms.openlocfilehash: 98b4ebb61f4f287b94967f0cfd80b6f0ca9caeaf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306553"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planear la administración de salas de Microsoft Teams con Azure monitor
 
 En este artículo se describen las consideraciones de planeación para usar Azure monitor para administrar los dispositivos de salas de Microsoft Teams en su implementación de Microsoft Teams o Skype empresarial.
  
El [monitor de Azure](https://docs.microsoft.com/azure/azure-monitor/overview) es una colección de servicios de administración diseñados en la nube desde el inicio. En lugar de implementar y administrar los recursos locales, los componentes de Azure monitor se hospedan por completo en Azure. La configuración es mínima, y puede estar en marcha en cuestión de minutos. Con algún trabajo de personalización, puede ayudar a administrar salas de conferencia de Microsoft Teams, proporcionando notificaciones en tiempo real de errores o de estado del sistema para sistemas de salas individuales, y puede escalar hasta la administración de miles de equipos de Microsoft Salas de conferencias.
  
En este artículo se proporciona una explicación de los requisitos, el diseño, la arquitectura y los procedimientos recomendados de implementación necesarios para implementar la administración basada en Azure monitor de los dispositivos de conferencia de salas de Microsoft Teams, y se proporcionan vínculos a los artículos detallados en implementación de Azure monitor para salas de Microsoft Teams e información de referencia crítica para la supervisión continuada de salas de salas de Microsoft Teams. 
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de administración de salas de Microsoft Teams con Azure monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación salas de Microsoft Teams del dispositivo de consola escribe eventos en el registro de eventos de Windows. Un agente de supervisión de Microsoft, una vez instalado, pasa la información al servicio de supervisión de Azure. 
  
Una vez que se ha configurado correctamente, el análisis de registros analiza la carga de JSON incrustada en las descripciones de evento para describir cómo funciona cada sistema de las salas de Microsoft Teams y qué errores se detectan. 
  
Un administrador que use Azure monitor puede obtener notificaciones de sistemas de salas de Microsoft teams que están desconectados o experimentan errores de aplicación, conectividad o hardware, así como saber si un sistema necesita reiniciarse. Cada estado del sistema se actualiza con frecuencia, por lo que estas notificaciones estarán cerca de las actualizaciones en tiempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Azure monitor

Para usar la característica de análisis de registros, debe tener una suscripción válida de Azure monitor de Azure. Consulte [Introducción a un área de trabajo de análisis de registros](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para crear una suscripción para su organización.
  
Debe familiarizarse según sea necesario para usar el diseñador de vistas de análisis de registros. Vea las [vistas de análisis de registros](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para obtener información detallada.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez que se haya suscrito a análisis de registros de Azure monitor, cree campos personalizados (según se describe en [asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)) necesarios para analizar la información que se enviará desde las consolas de salas de Microsoft Teams. Esto incluye comprender el esquema JSON documentado en [comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries).
    
2. Desarrolle una vista de administración de salas de Microsoft Teams en análisis de registros. Puede [crear un panel de Microsoft Teams Rooms con el método de importación](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) o [crear un panel de Microsoft Teams Rooms de forma manual](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos individuales de la consola de salas de Microsoft Teams

Cada consola de Microsoft Team Rooms es una aplicación que se ejecuta en un dispositivo Surface Pro en el modo de pantalla completa (normalmente está configurada para que sea la única aplicación que se puede ejecutar en el dispositivo). Al igual que con cualquier aplicación de Windows, la aplicación de salas de Microsoft Teams graba eventos como el inicio y los errores de hardware en el registro de eventos de Windows. Agregar un agente de Microsoft monitor en el dispositivo de salas de Microsoft Teams permite recopilar estos eventos. (Consulte [conectar equipos Windows con el servicio de análisis de registros en Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) para obtener más información).
  
## <a name="ongoing-management"></a>Administración continua

Mientras use Azure monitor para administrar sus dispositivos de salas de Microsoft Teams, tendrá que comprender la información contenida en los registros de eventos usados por Azure monitor. Consulte [comprender las entradas de registro](azure-monitor-manage.md#understand-the-log-entries) para obtener más información sobre estos mensajes de estado.
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por salas de Microsoft Teams y cómo resolverlas (consulte la sección titulada [comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries)).
    
## <a name="see-also"></a>Vea también

[Implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md)
  
[Administrar dispositivos de salas de Microsoft Teams con Azure monitor](azure-monitor-manage.md)