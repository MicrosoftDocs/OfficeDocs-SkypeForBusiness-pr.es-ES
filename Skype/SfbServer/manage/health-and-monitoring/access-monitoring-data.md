---
title: Acceso a datos de supervisión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumen: Obtenga información sobre los datos de supervisión usados en Skype empresarial Server.'
ms.openlocfilehash: b4eca36a09c4aa56b7216b476e0f0c5fa06d7a45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818191"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Acceso a datos de supervisión en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre los datos de supervisión usados en Skype empresarial Server.
  
Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos del registro detallado y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para obtener acceso y analizar los datos de SQL Server.
  
Una de las herramientas que debe considerar para acceder y analizar los datos de supervisión son los informes de supervisión de Skype empresarial Server. Son un conjunto de informes estándares que son publicados por el servicio de informes del servidor de Microsoft SQL. Estos informes, a los que se puede obtener acceso con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE. Los informes de supervisión se incluyen con Skype empresarial Server y se pueden instalar desde el Asistente para la implementación de Skype empresarial Server una vez que se ha instalado Skype empresarial Server y se ha configurado la supervisión.
  
Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.
  
Para obtener más información, vea el tema sobre cómo [instalar informes de supervisión en Skype empresarial Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

