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
description: Si implementó el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype Empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar archivado y supervisión a su grupo piloto de Skype Empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752672"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar los servidores de archivado y supervisión

Si implementó el servidor de archivado y el servidor de supervisión en su entorno heredado, puede implementar estos servidores en su entorno de Skype Empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar archivado y supervisión a su grupo piloto de Skype Empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración. 
  
Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:
  
- Los datos de archivado y los datos de supervisión no se mueven a la implementación de Skype Empresarial Server 2019. Los datos de los que se hace una copia de seguridad antes de retirar el entorno heredado serán su historial de actividad en el entorno heredado.
    
- La versión heredada del servidor de archivado y del servidor de supervisión solo se puede asociar a un grupo de servidores front-end heredado. En Skype Empresarial Server 2019, el archivado y la supervisión ya no son roles de servidor, sino servicios integrados en el grupo de servidores front-end de Skype Empresarial Server 2019.
    
- Durante el tiempo en que coexisten las implementaciones heredadas y de Skype Empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios que están en grupos heredados. El archivado y la supervisión en Skype Empresarial Server 2019 recopilan datos para los usuarios que están en grupos de Skype Empresarial Server 2019.
    
    > [!NOTE]
    > Durante la fase de migración cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Skype Empresarial Server 2019, la versión heredada del servidor de archivado sigue recopilando datos para los usuarios que se encuentran en grupos heredados y el archivado en Skype Empresarial Server 2019 recopila datos para los usuarios que están en grupos de Skype Empresarial Server 2019. 
  
- If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.
    

