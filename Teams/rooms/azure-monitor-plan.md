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
description: Este artículo explica consideraciones de planificación para usar Azure Monitor para administrar dispositivos de Salas de Microsoft Teams en su implementación de Skype Empresarial o Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137610"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planear la administración de salas de Microsoft Teams con Azure Monitor
 
 Este artículo explica consideraciones de planificación para usar Azure Monitor para administrar dispositivos de Salas de Microsoft Teams en su implementación de Microsoft Teams o Skype Empresarial.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) es una colección de servicios de administración que se diseñaron en la nube desde el principio. En lugar de implementar y administrar recursos locales, los componentes de Azure Monitor se hospedan por completo en Azure. La configuración es mínima y puede estar en funcionamiento literalmente en cuestión de minutos. Con algunos trabajos de personalización, puede ayudar a administrar los sistemas de conferencias de salas de Microsoft Teams al proporcionar notificaciones en tiempo real del estado del sistema o fallos del sistema para sistemas de salas individuales, y puede llegar a escalar hasta administrar miles de salas de conferencias de Microsoft Teams.
  
Este artículo ofrece una explicación de los requisitos, el diseño/arquitectura y los procedimientos recomendados de implementación necesarios para implementar la administración basada en Azure Monitor de los dispositivos de conferencia de salas de Microsoft Teams, y proporciona vínculos a artículos detallados sobre la implementación de Azure Monitor para salas de Microsoft Teams e información de referencia crítica para un seguimiento continuo de las salas de Microsoft Teams. 
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![Diagrama de administración de salas de Microsoft Teams con Monitor de Azure](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación Salas de Microsoft Teams del dispositivo de consola escribe eventos en su registro de eventos de Windows. Un agente de supervisión de Microsoft, una vez instalado, pasa la información al servicio Azure Monitor. 
  
Una vez configurada correctamente, Log Analytics analiza la carga JSON incrustada en las descripciones del evento para describir cómo funciona cada sistema de salones de Microsoft Teams y qué errores se detectan. 
  
Un administrador que use el Monitor de Azure puede recibir notificaciones de sistemas de salas de Microsoft Teams que están desconectados o están experimentando errores de hardware, conectividad o aplicaciones, así como saber si es necesario reiniciar un sistema. Cada estado del sistema se actualiza con frecuencia, por lo que estas notificaciones se acercan a las actualizaciones en tiempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Azure Monitor

Debe tener una suscripción válida de Azure Monitor para usar la característica de análisis de registro. Vea [Introducción a un área de trabajo de Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para crear una suscripción para su organización.
  
Debería familiarizarse según sea necesario sobre cómo usar el Diseñador de vistas de Log Analytics. Consulte [las vistas de Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para obtener esos detalles.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a Análisis de registro de [](azure-monitor-deploy.md#Custom_fields)Azure Monitor, cree campos personalizados (como se describe en Asignar campos personalizados) necesarios para analizar la información que se enviará desde las consolas de salones de Microsoft Teams. Esto incluye la comprensión del esquema JSON documentado en [Comprender las entradas de registro.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Desarrolle una vista de administración de salas de Microsoft Teams en Log Analytics. Puede crear un [panel de salas de Microsoft Teams mediante](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) el método de importación o crear manualmente un panel de salas de Microsoft [Teams.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos individuales de la consola de salas de Microsoft Teams

Cada consola de Salas de Microsoft Teams es una aplicación que se ejecuta en un dispositivo Surface Pro en modo quiosco (normalmente, está configurada para que sea la única aplicación que se pueda ejecutar en el dispositivo). Al igual que con cualquier aplicación de Windows, la aplicación Salas de Microsoft Teams escribe eventos como errores de hardware y inicio en el registro de eventos de Windows. Agregar un agente de Microsoft Monitor en el dispositivo de Microsoft Teams Rooms permite recopilar estos eventos. (Consulte [Conectar equipos Windows al servicio Log Analytics de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) para obtener más información).
  
## <a name="ongoing-management"></a>Administración continua

Al usar Azure Monitor para administrar los dispositivos de salas de Microsoft Teams, tendrá que comprender la información contenida en los registros de eventos usados por Azure Monitor. Consulte [Comprender las entradas de registro](azure-monitor-manage.md#understand-the-log-entries) para obtener más información sobre estos mensajes de estado.
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por salas de Microsoft Teams y cómo resolverlas (vea la sección Titulada Comprender [las entradas de registro)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Consulte también

[Implementar la administración de salas de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
  
[Administrar dispositivos de Salas de Microsoft Teams con Monitor de Azure](azure-monitor-manage.md)