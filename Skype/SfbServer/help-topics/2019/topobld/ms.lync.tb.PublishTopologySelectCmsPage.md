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
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publique la topología que haya configurado mediante el Generador de topologías. Se le pedirá que seleccione de una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.
ms.openlocfilehash: 91dd8d9c5fc6bc0fa34d76a77ee487393310e3e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629842"
---
# <a name="publish-topology-select-cms-page"></a>Publicar página CMS de selección de topología
 
Publique la topología que haya configurado mediante el Generador de topologías. Se le pedirá que seleccione de una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado. 
  
### <a name="about-the-central-management-server"></a>Acerca del servidor de administración central
El servidor de administración central es un único sistema de réplica principal o múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación. La base de datos local recibe actualizaciones de réplicas a través del agente replicador de réplicas de Lync Server que se ejecuta como servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está hecho de los archivos xds.mdf y xds.ldf. Se hace referencia a la ubicación de la base de datos maestra mediante un punto de control de servicio (SCP) en Servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan scp para buscar el almacén de administración central.
  
## <a name="see-also"></a>Consulte también

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)