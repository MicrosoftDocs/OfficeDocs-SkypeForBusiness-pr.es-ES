---
title: Acceso a datos en Skype de supervisión para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumen: Obtenga información sobre los datos de supervisión usados en Skype para Business Server.'
ms.openlocfilehash: 4bd7d7c55f2d041d1bd3d80cf056544cd5bf5ee1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986589"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Acceso a datos en Skype de supervisión para Business Server
 
**Resumen:** Obtenga información sobre los datos de supervisión usados en Skype para Business Server.
  
Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos del registro detallado y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para obtener acceso y analizar los datos de SQL Server.
  
Una herramienta que se debe tener en cuenta para obtener acceso y analizar los datos de supervisión es el Skype para informes de supervisión del servidor de negocio. Son un conjunto de informes estándares que son publicados por el servicio de informes del servidor de Microsoft SQL. Estos informes, a los que se puede obtener acceso con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE. Informes de supervisión se suministran con Skype para Business Server y pueden instalarse desde el Skype para el Asistente para la implementación de Business Server después de Skype para Business Server se ha instalado y se ha configurado la supervisión.
  
Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.
  
Para obtener más información, vea el tema [Instalación de informes de supervisión en Skype para Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

