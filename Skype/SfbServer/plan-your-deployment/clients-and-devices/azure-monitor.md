---
title: Planeación de la administración de salas de equipos de Microsoft con el Monitor de Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: En este artículo se describe las consideraciones de planeación para usar el Monitor de Azure para administrar dispositivos de salas de equipos de Microsoft en su Skype para profesionales o los equipos de la implementación.
ms.openlocfilehash: dfa65435da63eb9783422e1e7ee10e66ba33b891
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214578"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planeación de la administración de salas de equipos de Microsoft con el Monitor de Azure
 
 En este artículo se describe las consideraciones de planeación para usar el Monitor de Azure para administrar dispositivos de salas de equipos de Microsoft en su Skype para la implementación de Business Server.
  
[Monitor de Azure](https://docs.microsoft.com/azure/azure-monitor/overview) es una colección de servicios de administración que se diseñaron en la nube desde el principio. En lugar de implementar y administrar los recursos locales, los componentes del Monitor de Azure totalmente se hospedan en Azure. Configuración es mínima, y puede ser funcionamiento literalmente en cuestión de minutos. Con algunas tareas de personalización, puede ayudar a en la administración de sistemas de conferencia de salas de equipos de Microsoft por proporcionar notificaciones en tiempo real del estado del sistema o errores para sistemas de las salas individuales y potencialmente puede escalar a la administración de miles de Microsoft Teams Salas de conferencias de salas.
  
En este artículo se proporciona una explicación de los requisitos, diseño y arquitectura y procedimientos recomendados de implementación necesarios para implementar la administración de Monitor de Azure en función de los dispositivos de conferencia de salas de equipos de Microsoft y proporciona vínculos a artículos detallados sobre implementación de Monitor de Azure para salas de equipos de Microsoft y la información de referencia crítico para la supervisión continua de salones de salas de equipos de Microsoft. 
  
## <a name="functional-overview"></a>Descripción del funcionamiento

![diagrama de la administración de salas de equipos de Microsoft con el Monitor de Azure](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
La aplicación de salas de equipos de Microsoft en el dispositivo de consola escribe eventos en su registro de sucesos de Windows. Un agente de Microsoft Monitoring, una vez instalado, pasa la información al servicio de Monitor de Azure. 
  
Una vez configurado correctamente, analiza de análisis de registro la carga JSON en el evento incrustado descripciones para describir cómo funciona cada sistema de salas de equipos de Microsoft y se detectan los errores. 
  
Un administrador usar el Monitor de Azure puede obtener las notificaciones de los sistemas de salas de equipos de Microsoft que están sin conexión o se experimentar con la aplicación, la conectividad o errores de hardware así como saber si un sistema debe reiniciarse. Cada estado del sistema se actualiza con frecuencia, por lo que estas notificaciones son cerrar a actualizaciones en tiempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Monitor de Azure

Debe tener una suscripción de Azure válida para el Monitor de Azure para usar la característica de análisis de registro. Consulte [empezar a trabajar con un área de trabajo de análisis de registro](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para crear una suscripción para su organización.
  
Debe familiarizarse según sea necesario sobre cómo usar el Diseñador de vistas de análisis de registro. Vea [las vistas de análisis de registro](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para esos detalles.
  
### <a name="related-tasks"></a>Tareas relacionadas

1. Una vez suscrito a análisis de registro del Monitor de Azure, crear personalizado campos (tal como se describe en [Asignar campos personalizados](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) necesitan para analizar la información que se van a enviar desde consolas de salas de equipos de Microsoft. Esto incluye la descripción del esquema de JSON que se documentaron en [comprender las entradas del registro](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).
    
2. Desarrollar una vista de administración de salas de equipos de Microsoft en análisis de registro. Puede [crear un panel de salas de equipos de Microsoft mediante el método de importación](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) o [crear un panel de salas de equipos de Microsoft de forma manual](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos individuales de consola de salas de equipos de Microsoft

Cada consola salones de los equipos de Microsoft es una aplicación que se ejecuta en un dispositivo Surface Pro en modo de pantalla completa (normalmente, se configura para que sea la única aplicación que puede ejecutar en el dispositivo). Al igual que con cualquier aplicación de Windows, la aplicación de salas de equipos de Microsoft escribe eventos tales como errores de hardware y de inicio para el registro de eventos de Windows. Adición de un agente de Monitor de Microsoft en su dispositivo de salas de equipos de Microsoft permite estos eventos que se recopilan. (Para obtener más información, vea [equipos Windows conectarse con el servicio de registro de análisis en Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) ).
  
## <a name="ongoing-management"></a>Administración continua

Al usar el Monitor de Azure para administrar los dispositivos de salas de equipos de Microsoft, debe comprender la información contenida en los registros de eventos utilizados por el Monitor de Azure. Para obtener información detallada sobre estos mensajes de estado, vea [Descripción de las entradas del registro](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Tareas relacionadas

- Comprender las alertas generadas por los salones de los equipos de Microsoft y cómo resolverlos (vea la sección titulada [comprender las entradas del registro](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))
    
## <a name="see-also"></a>Vea también

[Implementar la administración de salas de equipos de Microsoft con el Monitor de Azure](../../deploy/deploy-clients/azure-monitor.md)
  
[Administrar dispositivos de salas de equipos de Microsoft con el Monitor de Azure](../../manage/skype-room-systems-v2/azure-monitor.md)