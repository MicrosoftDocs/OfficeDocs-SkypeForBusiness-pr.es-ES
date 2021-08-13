---
title: Obtener acceso a datos de supervisión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumen: obtenga información sobre los datos de supervisión usados en Skype Empresarial Server.'
ms.openlocfilehash: 56b27a372eaef71ee02569a418721e9d2e4b28859a99c20489713a859439217a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336650"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Obtener acceso a datos de supervisión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los datos de supervisión usados en Skype Empresarial Server.
  
Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos de registro de detalles y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para acceder y analizar los datos de SQL Server.
  
Una herramienta que debe tener en cuenta para obtener acceso y analizar los datos de supervisión es Skype Empresarial Server de supervisión. Los Informes de supervisión son un conjunto de informes estándar que son publicados por el servicio de informes del servidor de Microsoft SQL. Estos informes, a los que se puede acceder con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE. Los informes de supervisión se Skype Empresarial Server y se pueden instalar desde el Asistente para la implementación de Skype Empresarial Server después de Skype Empresarial Server se haya instalado y se haya configurado la supervisión.
  
Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.
  
Para obtener más información, vea el tema Instalar informes [de supervisión en Skype Empresarial Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

