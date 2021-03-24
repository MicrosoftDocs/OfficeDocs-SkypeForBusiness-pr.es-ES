---
title: Publicar página CMS de selección de topología
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publique la topología que haya configurado mediante el Generador de topologías. Se le pedirá que seleccione de una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096886"
---
# <a name="publish-topology-select-cms-page"></a>Publicar página CMS de selección de topología
 
Publique la topología que haya configurado mediante el Generador de topologías. Se le pedirá que seleccione de una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado. 
  
### <a name="about-the-central-management-server"></a>Acerca del servidor de administración central
El servidor de administración central es un único sistema de réplica principal o múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación. La base de datos local recibe actualizaciones de réplicas a través del agente replicador de réplicas de Lync Server que se ejecuta como servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está hecho de los archivos xds.mdf y xds.ldf. Se hace referencia a la ubicación de la base de datos maestra mediante un punto de control de servicio (SCP) en Servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan scp para buscar el almacén de administración central.
  
## <a name="see-also"></a>Ver también

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)