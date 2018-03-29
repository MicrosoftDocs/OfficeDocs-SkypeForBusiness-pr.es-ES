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
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a><span data-ttu-id="95623-103">Obtener acceso a los datos de supervisión en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="95623-103">Access monitoring data in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95623-104">**Resumen:** Obtenga información sobre los datos de supervisión utilizados en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95623-104">**Summary:** Learn about the monitoring data used in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="95623-p101">Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos del registro detallado y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para obtener acceso y analizar los datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95623-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="95623-107">Una herramienta que se debe tener en cuenta para el acceso y análisis de datos de supervisión es el Skype para informes de supervisión de servidor de negocios.</span><span class="sxs-lookup"><span data-stu-id="95623-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="95623-108">Son un conjunto de informes estándares que son publicados por el servicio de informes del servidor de Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="95623-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="95623-109">Estos informes, a los que se puede obtener acceso con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE.</span><span class="sxs-lookup"><span data-stu-id="95623-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="95623-110">Informes de supervisión incluyen en Skype para Business Server 2015 y pueden instalarse desde el Skype para el Asistente para implementación de Business Server después de Skype para Business Server se ha instalado y se ha configurado la supervisión.</span><span class="sxs-lookup"><span data-stu-id="95623-110">Monitoring Reports ship with Skype for Business Server 2015 and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="95623-p103">Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.</span><span class="sxs-lookup"><span data-stu-id="95623-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="95623-113">Para obtener más información, vea el tema [Instalar informes de supervisión en Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) en el Skype para la Guía de implementación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95623-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) in the Skype for Business Server 2015 deployment guide.</span></span>
  

