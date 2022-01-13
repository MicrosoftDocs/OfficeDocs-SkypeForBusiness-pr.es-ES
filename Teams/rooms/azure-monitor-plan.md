---
title: Planear Salas de Microsoft Teams supervisión con Azure Monitor
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
description: En este artículo se debata sobre las consideraciones de planeación para usar Azure Monitor para supervisar Salas de Microsoft Teams en su Skype Empresarial o Teams implementación.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13c16234773792f9dc394723521224123c5e2141
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015210"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planear Salas de Microsoft Teams supervisión con Azure Monitor
 
 En este artículo se debata sobre las consideraciones de planeación para usar Azure Monitor para administrar Salas de Microsoft Teams dispositivos en su Microsoft Teams o Skype Empresarial implementación.

> [!NOTE]
> También puede configurar [la supervisión del estado de Salas de Teams](../alerts/device-health-status.md) con Teams de administración.

[Azure Monitor](/azure/azure-monitor/overview) es una colección de servicios de supervisión que se diseñaron en la nube desde el principio. En lugar de implementar y administrar recursos locales, los componentes de Azure Monitor se hospedan por completo en Azure. La configuración es mínima y puede estar en funcionamiento en cuestión de minutos. Con algunos trabajos de personalización, puede ayudar a supervisar Salas de Microsoft Teams proporcionando notificaciones del estado del sistema o errores de sistemas de sala individuales, y puede escalar hasta administrar miles de Salas de Microsoft Teams.
  
En este artículo se ofrece una discusión sobre los requisitos, el diseño/arquitectura y los procedimientos recomendados de implementación necesarios para implementar la supervisión basada en Azure Monitor de Salas de Microsoft Teams. También proporciona vínculos a artículos detallados sobre la implementación de Azure Monitor para Salas de Microsoft Teams información crítica de referencia para la supervisión continua de Salas de Microsoft Teams salas.
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de Salas de Microsoft Teams con Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La Salas de Microsoft Teams de eventos escribe eventos en el Windows de eventos. Una vez instalado, un agente de Supervisión de Microsoft pasa la información al servicio Azure Monitor.
  
Una vez configurado correctamente, Log Analytics analiza la carga JSON incrustada en las descripciones del evento para describir cómo funciona Salas de Microsoft Teams y qué errores se detectan.
  
Un administrador que usa Azure Monitor puede recibir notificaciones de Salas de Microsoft Teams que están sin conexión o están experimentando errores de aplicación, conectividad o hardware, así como saber si es necesario reiniciar un sistema. Cada estado del sistema se actualiza con frecuencia, por lo que estas notificaciones están cerca de las actualizaciones en tiempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Azure Monitor

Debe tener una suscripción válida de Azure para Azure Monitor para usar las características de Log Analytics. Vea [Introducción a un área de trabajo de Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) para crear una suscripción para su organización.
  
Debe familiarizarse con el uso del Diseñador de vistas de Log Analytics. Para [obtener más información,](/azure/azure-monitor/platform/view-designer) vea Vistas en Análisis de registros.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a Azure Monitor Log Analytics, [](azure-monitor-deploy.md#Custom_fields)cree campos personalizados (como se describe en Asignar campos personalizados) necesarios para analizar la información que se enviará desde Salas de Microsoft Teams. Esto incluye comprender el esquema JSON documentado en [Comprender las entradas de registro.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Desarrolle una vista Salas de Microsoft Teams administración en Log Analytics. Puede crear [un panel de Salas de Microsoft Teams manualmente.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Requisitos Salas de Microsoft Teams individuales

Salas de Microsoft Teams es una aplicación que se ejecuta en un dispositivo informático en modo de quiosco. Al igual que con cualquier Windows, la aplicación Salas de Microsoft Teams escribe eventos como errores de inicio y hardware en el Windows de eventos. Agregar un agente de Microsoft Monitor en Salas de Microsoft Teams permite recopilar estos eventos. (Vea [Conectar Windows equipos al servicio Log Analytics en Azure](/azure/azure-monitor/platform/agent-windows) para obtener más información).
  
## <a name="ongoing-management"></a>Administración continua

Al usar Azure Monitor para supervisar su Salas de Microsoft Teams, deberá comprender la información contenida en los registros de eventos usados por Azure Monitor. Vea [Comprender las entradas de registro](azure-monitor-manage.md#understand-the-log-entries) para obtener más información sobre estos mensajes de estado.
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por Salas de Microsoft Teams y cómo resolverlas (vea la sección titulada [Comprender las entradas de registro)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Vea también

[Implementar Salas de Microsoft Teams de administración con Azure Monitor](azure-monitor-deploy.md)
  
[Administrar Salas de Microsoft Teams dispositivos con Azure Monitor](azure-monitor-manage.md)
