---
title: Publicar página CMS de selección de topología
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publicar la topología que se ha configurado mediante el generador de topología. Le pedirá que seleccione en la lista que el grupo de servidores Front-End o de servidor Front-End asumirá la función de mantener el almacén de Administración Central. Un solo grupo de servidores Front-End o de servidor Front-End puede contener esta función en cualquier momento dado.
ms.openlocfilehash: e649629650bfa1fe168698984e3e8b0aaa5d2df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888761"
---
# <a name="publish-topology-select-cms-page"></a>Publicar página CMS de selección de topología
 
Publicar la topología que se ha configurado mediante el generador de topología. Le pedirá que seleccione en la lista que el grupo de servidores Front-End o de servidor Front-End asumirá la función de mantener el almacén de Administración Central. Un solo grupo de servidores Front-End o de servidor Front-End puede contener esta función en cualquier momento dado. 
  
### <a name="about-the-central-management-server"></a>Acerca del servidor de Administración Central
El servidor de Administración Central es un sistema de única réplica maestro o varios, donde se mantiene la copia de lectura y escritura de la base de datos por el servidor Front-End que contiene el servidor de Administración Central. Cada equipo en la topología, incluido el servidor Front-End que contiene el servidor de Administración Central, tiene una copia de solo lectura de los datos del almacén de Administración Central en la base de datos de SQL (denominado RTCLOCAL de forma predeterminada) instalado en el equipo durante el programa de instalación y despliegue. La base de datos local recibe actualizaciones de réplica mediante el agente de Replicador de Lync Server réplica que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el servidor de Administración Central y la réplica local es XDS, que se compone de los archivos xds.mdf y xds.ldf. Un punto de control de servicio (SCP) en servicios de dominio de Active Directory al que hace referencia la ubicación de la base de datos maestra. Todas las herramientas que use el servidor de Administración Central para administrar y configurar Lync Server usa la SCP para encontrar el almacén de Administración Central.
  
## <a name="see-also"></a>Vea también

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
