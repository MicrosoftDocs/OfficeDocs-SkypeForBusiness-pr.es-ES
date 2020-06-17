---
title: Migrar los servidores de archivado y supervisión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar el archivado y la supervisión al grupo piloto de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752672"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar los servidores de archivado y supervisión

Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar el archivado y la supervisión al grupo piloto de Skype empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración. 
  
Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:
  
- Los datos de archivado y supervisión no se mueven a la implementación de Skype empresarial Server 2019. Los datos que realices en la copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en el entorno heredado.
    
- La versión heredada del servidor de archivado y el servidor de supervisión solo se pueden asociar a un grupo de servidores front-end heredado. En Skype empresarial Server 2019, el archivado y la supervisión ya no tienen roles de servidor, sino que se integran en el grupo de servidores front-end de la 2019 de Skype empresarial Server.
    
- Durante el tiempo que coexisten las implementaciones heredadas y de Skype empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios hospedados en grupos de servidores heredados. Archivado y supervisión en Skype empresarial Server 2019 recopilar datos para los usuarios hospedados en grupos de servidores de Skype empresarial 2019.
    
    > [!NOTE]
    > Durante la fase de migración, cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Skype empresarial Server 2019, la versión heredada del servidor de archivado continúa recopilando datos para los usuarios alojados en grupos de servidores heredados y el archivado en Skype empresarial Server 2019 recopila datos para los usuarios alojados en grupos de Skype empresarial Server 2019. 
  
- Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Skype empresarial Server 2019, consulte al proveedor Cuándo y cómo debe integrar la solución de terceros con Skype empresarial Server 2019.
    

