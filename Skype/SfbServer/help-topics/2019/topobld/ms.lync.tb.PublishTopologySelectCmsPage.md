---
title: Publicar página CMS de selección de topología
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publique la topología que ha configurado con el generador de topología. Se le pedirá que seleccione de una lista en la que el servidor front-end o el grupo de servidores front-end asumirán la función de mantener el almacén de administración central. Solo un servidor front-end o un grupo de servidores front-end pueden mantener este rol en un momento dado.
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277884"
---
# <a name="publish-topology-select-cms-page"></a>Publicar página CMS de selección de topología
 
Publique la topología que ha configurado con el generador de topología. Se le pedirá que seleccione de una lista en la que el servidor front-end o el grupo de servidores front-end asumirán la función de mantener el almacén de administración central. Solo un servidor front-end o un grupo de servidores front-end pueden mantener este rol en un momento dado. 
  
### <a name="about-the-central-management-server"></a>Acerca del servidor de administración central
El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos es retenida por el servidor front-end que contiene el servidor de administración central. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén central de administración en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y implementación. La base de datos local recibe actualizaciones de réplica por medio del agente replicador de réplicas de Lync Server que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está compuesto de los archivos XDS. MDF y XDS. ldf. Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan el SCP para localizar el almacén de administración central.
  
## <a name="see-also"></a>Vea también

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
