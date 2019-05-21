---
title: Migrar los servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de aplicaciones para el usuario. Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo de pruebas de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298200"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar los servidores de archivado y supervisión

Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de aplicaciones para el usuario. Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo de pruebas de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración. 
  
Si desea mantener la funcionalidad de archivado y supervisión durante el proceso de migración, tenga en cuenta las siguientes consideraciones:
  
- Los datos de archivado y supervisión no se mueven a la implementación de Skype empresarial Server 2019. Los datos que respaldas antes de dar de baja el entorno heredado serán tu historial de actividad en el entorno heredado.
    
- La versión heredada del servidor de archivado y del servidor de supervisión solo se puede asociar con un grupo de servidores front-end heredado. En Skype empresarial Server 2019, el archivado y la supervisión ya no tienen roles de servidor, pero los servicios se integran en el grupo front-end de Skype empresarial Server 2019.
    
- En el momento en que coexistan las implementaciones heredada de Skype empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en grupos heredados. Archivado y supervisión en Skype empresarial Server 2019 recopilar datos para los usuarios alojados en los grupos de servidores de Skype empresarial 2019.
    
    > [!NOTE]
    > Durante la fase de migración, cuando aún usa el servidor perimetral heredado con el nuevo grupo piloto de Skype empresarial Server 2019, la versión heredada del servidor de archivado continúa recopilando datos para los usuarios alojados en grupos heredados y archivado en Skype empresarial. El servidor 2019 reúne datos para usuarios alojados en grupos de servidores de Skype empresarial 2019. 
  
- Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Skype empresarial Server 2019, póngase en relación con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Skype empresarial Server 2019.
    

