---
title: Obtener acceso a los datos de supervisión en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumen: Conozca los datos de supervisión utilizados en Skype para Business Server 2015.'
ms.openlocfilehash: 908ebbff4e88985cdba606098dc5a5ace271e30d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a>Obtener acceso a los datos de supervisión en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre los datos de supervisión utilizados en Skype para Business Server 2015.
  
Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos del registro detallado y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para obtener acceso y analizar los datos de SQL Server.
  
Una herramienta que se debe tener en cuenta para el acceso y análisis de datos de supervisión es el Skype para informes de supervisión de servidor de negocios. Son un conjunto de informes estándares que son publicados por el servicio de informes del servidor de Microsoft SQL. Estos informes, a los que se puede obtener acceso con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE. Informes de supervisión incluyen en Skype para Business Server 2015 y pueden instalarse desde el Skype para el Asistente para implementación de Business Server después de Skype para Business Server se ha instalado y se ha configurado la supervisión.
  
Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.
  
Para obtener más información, vea el tema [Instalar informes de supervisión en Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) en el Skype para la Guía de implementación de Business Server 2015.
  

