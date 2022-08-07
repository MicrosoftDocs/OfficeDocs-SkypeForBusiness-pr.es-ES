---
title: Planear la supervisión de Salas de Microsoft Teams con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: En este artículo se describen consideraciones de planeación para usar Azure Monitor para supervisar Salas de Microsoft Teams en la implementación de Skype for Business o Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac3ac3af4e4f162238af0e9bf38c45569302fdfb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269575"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planear la supervisión de Salas de Microsoft Teams con Azure Monitor
 
 En este artículo se describen consideraciones de planeación para usar Azure Monitor para administrar dispositivos Salas de Microsoft Teams en Microsoft Teams o Skype for Business implementación.

> [!NOTE]
> También puede [configurar la supervisión del estado de Salas de Teams](../alerts/device-health-status.md) mediante el Centro de administración de Teams.

[Azure Monitor](/azure/azure-monitor/overview) es una colección de servicios de supervisión que se diseñaron en la nube desde el principio. En lugar de implementar y administrar recursos locales, los componentes de Azure Monitor se hospedan por completo en Azure. La configuración es mínima y puede ponerse en marcha en cuestión de minutos. Con algunos trabajos de personalización, puede ayudar a supervisar Salas de Microsoft Teams proporcionando notificaciones del estado del sistema o los errores de los sistemas de salas individuales, y puede escalar hasta administrar miles de Salas de Microsoft Teams.
  
En este artículo se proporciona una explicación de los requisitos, el diseño o la arquitectura y los procedimientos recomendados de implementación necesarios para implementar la supervisión basada en Azure Monitor de Salas de Microsoft Teams. También proporciona vínculos a artículos detallados sobre la implementación de Azure Monitor para Salas de Microsoft Teams e información de referencia crítica para la supervisión continua de los salones de Salas de Microsoft Teams.
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de administración de Salas de Microsoft Teams con Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación Salas de Microsoft Teams escribe eventos en el registro de eventos de Windows. Una vez instalado, un agente de Microsoft Monitoring pasa la información al servicio Azure Monitor.
  
Una vez configurado correctamente, Log Analytics analiza la carga de JSON incrustada en las descripciones de eventos para describir cómo funciona Salas de Microsoft Teams y qué errores se detectan.
  
Un administrador que use Azure Monitor puede recibir notificaciones de Salas de Microsoft Teams que estén sin conexión o que experimenten errores de hardware, conectividad o aplicación, así como saber si es necesario reiniciar un sistema. Cada estado del sistema se actualiza con frecuencia, por lo que estas notificaciones se acercan a las actualizaciones en tiempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Azure Monitor

Debe tener una suscripción de Azure válida para que Azure Monitor use las características de Log Analytics. Consulte [Introducción a un área de trabajo de Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) para crear una suscripción para su organización.
  
Debería familiarizarse con cómo usar el Diseñador de vistas de Log Analytics. Consulte [Vistas en Log Analytics](/azure/azure-monitor/platform/view-designer) para obtener esos detalles.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a Azure Monitor Log Analytics, cree campos personalizados (como se describe en [Asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)) necesarios para analizar la información que se enviará desde Salas de Microsoft Teams. Esto incluye la comprensión del esquema JSON documentado en [Comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries).
    
2. Desarrolle una vista de administración de Salas de Microsoft Teams en Log Analytics. Puede [Crear un panel de Salas de Microsoft Teams manualmente](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Requisitos de Salas de Microsoft Teams individuales

Salas de Microsoft Teams es una aplicación que se ejecuta en un dispositivo informático en modo de pantalla completa. Al igual que con cualquier aplicación de Windows, la aplicación de Salas de Microsoft Teams escribe eventos como errores de inicio y hardware en el registro de eventos de Windows. Agregar un agente de Microsoft Monitor en Salas de Microsoft Teams permite recopilar estos eventos. (Consulta [Conectar equipos Windows al servicio Log Analytics en Azure](/azure/azure-monitor/platform/agent-windows) para obtener más información).
  
## <a name="ongoing-management"></a>Administración continua

Mientras usa Azure Monitor para supervisar el Salas de Microsoft Teams, tendrá que comprender la información contenida en los registros de eventos que usa Azure Monitor. Consulte [Comprender las entradas de registro](azure-monitor-manage.md#understand-the-log-entries) para obtener más información sobre estos mensajes de estado.
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por Salas de Microsoft Teams y cómo resolverlas (consulte la sección titulada [Comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Vea también

[Implementar la administración de Salas de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
  
[Administrar dispositivos Salas de Microsoft Teams con Azure Monitor](azure-monitor-manage.md)
