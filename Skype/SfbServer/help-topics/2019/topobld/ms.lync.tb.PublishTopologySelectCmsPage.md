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
description: La topología que ha configurado se publica con topology Builder. Se le pedirá que seleccione en una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822190"
---
# <a name="publish-topology-select-cms-page"></a>Publicar página CMS de selección de topología
 
La topología que ha configurado se publica con topology Builder. Se le pedirá que seleccione en una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado. 
  
### <a name="about-the-central-management-server"></a>Acerca del servidor de administración central
El servidor de administración central es un único sistema maestro/réplica múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación. La base de datos local recibe actualizaciones de réplicas mediante el agente de replicador de réplicas de Lync Server que se ejecuta como servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que se incluye en los archivos xds.mdf y xds.ldf. Un punto de control de servicio (SCP) de los Servicios de dominio de Active Directory hace referencia a la ubicación de la base de datos maestra. Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan el SCP para ubicar el almacén de administración central.
  
## <a name="see-also"></a>Vea también

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
