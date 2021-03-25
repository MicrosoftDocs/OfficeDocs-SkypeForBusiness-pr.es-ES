---
title: Planear la administración de salas de Microsoft Teams con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: En este artículo se debata sobre las consideraciones de planeación para usar Azure Monitor para administrar dispositivos de Salas de Microsoft Teams en su implementación de Skype Empresarial o Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117588"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planear la administración de salas de Microsoft Teams con Azure Monitor
 
 En este artículo se debata sobre las consideraciones de planeación para usar Azure Monitor para administrar dispositivos de Salas de Microsoft Teams en la implementación de Microsoft Teams o Skype Empresarial.
  
[Azure Monitor](/azure/azure-monitor/overview) es una colección de servicios de administración que se diseñaron en la nube desde el principio. En lugar de implementar y administrar recursos locales, los componentes de Azure Monitor se hospedan por completo en Azure. La configuración es mínima y puede estar funcionando literalmente en cuestión de minutos. Con algunos trabajos de personalización, puede ayudar a administrar los sistemas de conferencias de salas de Microsoft Teams proporcionando notificaciones en tiempo real del estado del sistema o errores de sistemas de salas individuales, y puede escalar potencialmente hasta administrar miles de salas de conferencias de Salas de Microsoft Teams.
  
En este artículo se describe los requisitos, el diseño y la arquitectura y los procedimientos recomendados de implementación necesarios para implementar la administración basada en Azure Monitor de los dispositivos de conferencia de Salas de Microsoft Teams y se proporcionan vínculos a artículos detallados sobre la implementación de Azure Monitor para salas de Microsoft Teams e información de referencia crítica para la supervisión continua de salas de Salas de Microsoft Teams. 
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de administración de salas de Microsoft Teams con Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación Salas de Microsoft Teams en el dispositivo de consola escribe eventos en su registro de eventos de Windows. Una vez instalado, un agente de Supervisión de Microsoft pasa la información al servicio Azure Monitor. 
  
Una vez configurado correctamente, Log Analytics analiza la carga JSON incrustada en las descripciones del evento para describir cómo funciona cada sistema de Salas de Microsoft Teams y qué errores se detectan. 
  
Un administrador que usa Azure Monitor puede recibir notificaciones de sistemas de Salas de Microsoft Teams que están sin conexión o que están experimentando errores de hardware, conectividad o aplicaciones, así como saber si es necesario reiniciar un sistema. Cada estado del sistema se actualiza con frecuencia, por lo que estas notificaciones están cerca de las actualizaciones en tiempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Azure Monitor

Debe tener una suscripción válida de Azure para Azure Monitor para usar la característica Log Analytics. Vea [Introducción a un área de trabajo de Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) para crear una suscripción para su organización.
  
Debe familiarizarse según sea necesario sobre cómo usar el Diseñador de vistas de Log Analytics. Para [obtener más información,](/azure/azure-monitor/platform/view-designer) vea Vistas en Análisis de registros.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a Azure Monitor Log Analytics, [](azure-monitor-deploy.md#Custom_fields)cree campos personalizados (como se describe en Asignar campos personalizados) necesarios para analizar la información que se enviará desde las consolas de Salas de Microsoft Teams. Esto incluye comprender el esquema JSON documentado en [Comprender las entradas de registro.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Desarrolle una vista de administración de salas de Microsoft Teams en Log Analytics. Puede crear un [panel de Salas de Microsoft Teams mediante](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) el método de importación o crear manualmente un panel salas de Microsoft [Teams.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos individuales de la consola salas de Microsoft Teams

Cada consola de Salas de Microsoft Teams es una aplicación que se ejecuta en un dispositivo Surface Pro en modo quiosco (normalmente, está configurada para ser la única aplicación que se puede ejecutar en el dispositivo). Al igual que con cualquier aplicación de Windows, la aplicación Salas de Microsoft Teams escribe eventos como errores de inicio y hardware en el registro de eventos de Windows. Agregar un agente de Microsoft Monitor en el dispositivo Salas de Microsoft Teams permite recopilar estos eventos. (Vea [Conectar equipos Windows al servicio Log Analytics en Azure](/azure/azure-monitor/platform/agent-windows) para obtener más información).
  
## <a name="ongoing-management"></a>Administración continua

Al usar Azure Monitor para administrar los dispositivos de Salas de Microsoft Teams, deberá comprender la información contenida en los registros de eventos usados por Azure Monitor. Vea [Comprender las entradas de registro](azure-monitor-manage.md#understand-the-log-entries) para obtener más información sobre estos mensajes de estado.
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por salas de Microsoft Teams y cómo resolverlas (vea la sección Titulada [Comprender las entradas de registro)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Vea también

[Implementar la administración de salas de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
  
[Administrar dispositivos de Salas de Microsoft Teams con Azure Monitor](azure-monitor-manage.md)